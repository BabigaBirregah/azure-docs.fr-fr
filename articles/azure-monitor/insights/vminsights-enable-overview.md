---
title: Vue d’ensemble de l’activation d’Azure Monitor pour machines virtuelles
description: Découvrez comment déployer et configurer Azure Monitor pour des machines virtuelles. Découvrez la configuration système requise.
ms.subservice: ''
ms.topic: conceptual
author: bwren
ms.author: bwren
ms.date: 12/22/2020
ms.custom: references_regions
ms.openlocfilehash: ce90ab160696e2c38d917a391eecb0d51a31282f
ms.sourcegitcommit: 44844a49afe8ed824a6812346f5bad8bc5455030
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/23/2020
ms.locfileid: "97740587"
---
# <a name="enable-azure-monitor-for-vms-overview"></a>Vue d’ensemble de l’activation d’Azure Monitor pour machines virtuelles

Cet article fournit une vue d’ensemble des options disponibles pour activer Azure Monitor pour machines virtuelles afin de superviser l’intégrité et les performances des éléments suivants :

- Machines virtuelles Azure 
- Groupes de machines virtuelles identiques Azure
- Machines virtuelles hybrides connectées avec Azure Arc
- Machines virtuelles locales
- Machines virtuelles hébergées dans un autre environnement cloud.  

Pour configurer Azure Monitor pour des machines virtuelles :

* Activez une seule machine virtuelle Azure, un seul groupe de machines virtuelles identiques Azure ou une seule machine Azure Arc en sélectionnant **Insights** directement à partir du menu correspondant dans le portail Azure.
* Activez plusieurs machines virtuelles Azure, plusieurs groupes de machines virtuelles identiques Azure ou plusieurs machines Azure Arc à l’aide d’Azure Policy. Cette méthode vérifie que, sur des machines virtuelles et des groupes identiques Azure, les dépendances requises sont installées et correctement configurées. Les machines virtuelles et les groupes identiques non conformes sont signalés pour vous permettre de décider si vous souhaitez les activer et les corriger.
* Activez plusieurs machines virtuelles Azure, plusieurs machines virtuelles Azure Arc, plusieurs groupes de machines virtuelles identiques Azure ou plusieurs machines Azure Arc sur un abonnement ou un groupe de ressources spécifique à l’aide de PowerShell.
* Activez Azure Monitor pour machines virtuelles afin de surveiller les machines virtuelles ou ordinateurs physiques hébergés dans votre réseau d’entreprise ou un autre environnement cloud.

## <a name="supported-machines"></a>Machines prises en charge
Azure Monitor pour machines virtuelles prend en charge les machines suivantes :

- Machine virtuelle Azure
- Groupe de machines virtuelles identiques Azure
- Machine virtuelle hybride connectée avec Azure Arc


## <a name="supported-azure-arc-machines"></a>Machines Azure Arc prises en charge
Azure Monitor pour machines virtuelles est disponible pour les serveurs Azure Arc dans les régions où le service d’extension Arc est disponible. Vous devez exécuter la version 0.9 ou une version supérieure de l’agent Arc.

| Source connectée | Prise en charge | Description |
|:--|:--|:--|
| Agents Windows | Oui | Outre l’agent [Log Analytics pour Windows](../platform/log-analytics-agent.md), les agents Windows ont besoin du Dependency Agent. Pour plus d’informations, voir [Systèmes d’exploitation pris en charge](../platform/agents-overview.md#supported-operating-systems). |
| Agents Linux | Oui | Outre l’agent [Log Analytics pour Linux](../platform/log-analytics-agent.md), les agents Linux ont besoin du Dependency Agent. Pour plus d’informations, voir [Systèmes d’exploitation pris en charge](#supported-operating-systems). |
| Groupe d’administration Microsoft System Center Operations Manager | Non | |

## <a name="supported-operating-systems"></a>Systèmes d’exploitation pris en charge

Azure Monitor pour machines virtuelles prend en charge tout système d’exploitation prenant en charge l’agent Log Analytics et l’agent Dependency. Pour une liste complète, consultez [Vue d’ensemble des agents Azure Monitor](../platform/agents-overview.md#supported-operating-systems).

Consultez la liste suivante de considérations sur la prise en charge par Linux de l’agent Dependency qui prend en charge Azure Monitor pour machines virtuelles :

- Seules les versions du noyau SMP Linux et par défaut sont prises en charge.
- Les versions non standard du noyau, par exemple Physical Address Extension (PAE) et Xen, ne sont prises en charge par aucune distribution Linux. Par exemple, un système avec la chaîne de version *2.6.16.21-0.8-xen* n’est pas pris en charge.
- Les noyaux personnalisés, y compris les recompilations de noyaux standard, ne sont pas pris en charge.
- Pour les distributions Debian autres que la version 9.4, la fonctionnalité de mappage n’est pas prise en charge et la fonctionnalité Performances n’est disponible qu’à partir du menu Azure Monitor. Elle n’est pas directement accessible à partir du volet gauche de la machine virtuelle Azure.
- Le noyau CentOSPlus est pris en charge.
- Le noyau Linux doit être corrigé pour la vulnérabilité Spectre. Pour plus d’informations, consultez le fournisseur de votre distribution Linux.
## <a name="log-analytics-workspace"></a>Espace de travail Log Analytics
Azure Monitor pour machines virtuelles nécessite un espace de travail Log Analytics. Pour plus d’informations sur la configuration de cet espace de travail, consultez [Configurer l’espace de travail Log Analytics d’Azure Monitor pour machines virtuelles](vminsights-configure-workspace.md).
## <a name="agents"></a>Agents
Azure Monitor pour machines virtuelles nécessite l’installation des deux agents suivants sur chaque machine virtuelle ou groupe de machines virtuelles identiques à surveiller. L’installation de ces agents et leur connexion à l’espace de travail est la seule condition requise pour l’intégration de la ressource.

- [Agent Log Analytics](../platform/log-analytics-agent.md). Collecte les événements et les données de performances de la machine virtuelle ou du groupe de machines virtuelles identiques et les livre à l’espace de travail Log Analytics. Les méthodes de déploiement de l’agent Log Analytics sur les ressources Azure utilisent l’extension de machine virtuelle pour [Windows](../../virtual-machines/extensions/oms-windows.md) et [Linux](../../virtual-machines/extensions/oms-linux.md).
- Agent de dépendances. Collecte les données découvertes concernant les processus exécutés sur la machine virtuelle et les dépendances de processus externes, qui sont utilisées par la [fonctionnalité de mappage dans Azure Monitor pour machines virtuelles](vminsights-maps.md). Il s’appuie sur l’agent Log Analytics pour remettre ses données à Azure Monitor. Les méthodes de déploiement de l’agent Dependency Agent sur les ressources Azure utilisent l’extension de machine virtuelle pour [Windows](../../virtual-machines/extensions/agent-dependency-windows.md) et [Linux](../../virtual-machines/extensions/agent-dependency-linux.md).

> [!NOTE]
> L’agent Log Analytics est le même agent que celui utilisé par Operations Manager. Azure Monitor pour machines virtuelles peut surveiller les agents qui sont également surveillés par Operations Manager s’ils sont connectés directement, et que vous y installez l’agent de dépendances. Les agents connectés à Azure Monitor via une [connexion de groupe d’administration](../tform/../platform/om-agents.md) ne peuvent pas être surveillés par Azure Monitor pour machines virtuelles.

Voici plusieurs méthodes pour déployer ces agents. 

| Méthode | Description |
|:---|:---|
| [Azure portal](./vminsights-enable-portal.md) | Installez les deux agents sur une seule machine virtuelle, des machines virtuelles hybrides ou un groupe de machines virtuelles identiques connectés à Azure Arc. |
| [Modèles Microsoft Azure Resource Manager](vminsights-enable-resource-manager.md) | Installez les deux agents à l’aide de l’une des méthodes prises en charge pour déployer un modèle Resource Manager, notamment l’interface CLI et PowerShell. |
| [Azure Policy](./vminsights-enable-policy.md) | Attribuez une initiative Azure Policy pour installer automatiquement les agents lors de la création d’une machine virtuelle ou d’un groupe de machines virtuelles identiques. |
| [Installation manuelle](./vminsights-enable-hybrid.md) | Installez les agents dans le système d’exploitation invité sur les ordinateurs hébergés en dehors d’Azure, notamment dans votre centre de centres ou dans d’autres environnements clouds. |




## <a name="management-packs"></a>Packs d’administration
Lorsqu’un espace de travail Log Analytics est configuré pour Azure Monitor pour machines virtuelles, deux packs d’administration sont transférés à tous les ordinateurs Windows connectés à cet espace de travail. Les packs d’administration se nomment *Microsoft.IntelligencePacks.ApplicationDependencyMonitor* et *Microsoft.IntelligencePacks.VMInsights*, et sont écrits dans *%Programfiles%\Microsoft Monitoring Agent\Agent\Health Service State\Management Packs*. 

La source de données utilisée par le pack d’administration *ApplicationDependencyMonitor* est * *%Program files%\Microsoft Monitoring Agent\Agent\Health Service State\Resources\<AutoGeneratedID>\Microsoft.EnterpriseManagement.Advisor.ApplicationDependencyMonitorDataSource.dll*. La source de données utilisée par le pack d’administration *VMInsights* est *%Program files%\Microsoft Monitoring Agent\Agent\Health Service State\Resources\<AutoGeneratedID>\ Microsoft.VirtualMachineMonitoringModule.dll*.

## <a name="diagnostic-and-usage-data"></a>Données relatives aux diagnostics et à l’utilisation

Microsoft collecte automatiquement les données sur l’utilisation et les performances via votre utilisation du service Azure Monitor. Microsoft utilise ces données pour fournir et améliorer la qualité, la sécurité et l’intégrité du service. 

Pour fournir des capacités de dépannage précises et efficaces, la fonctionnalité Map inclut des données sur la configuration de votre logiciel. Les données fournissent des informations telles que le système d’exploitation et sa version, l’adresse IP, le nom DNS et nom de la station de travail. Microsoft ne collecte pas de nom, d’adresse ou d’autres coordonnées.

Pour plus d’informations sur l’utilisation et la collecte de données, voir la [Déclaration de confidentialité des Services en ligne de Microsoft](https://go.microsoft.com/fwlink/?LinkId=512132).

[!INCLUDE [GDPR-related guidance](../../../includes/gdpr-dsr-and-stp-note.md)]

## <a name="next-steps"></a>Étapes suivantes

Pour savoir comment utiliser la fonctionnalité d’analyse des performances, consultez [Afficher les performances d’Azure Monitor pour machines virtuelles](vminsights-performance.md). Pour afficher les dépendances des applications détectées, consultez [Utilisation de la fonctionnalité Map d’Azure Monitor pour machines virtuelles dans le but de comprendre les composants d’application](vminsights-maps.md).
