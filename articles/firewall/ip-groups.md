---
title: Groupes IP dans Pare-feu Azure
description: Les groupes IP vous permettent de regrouper et de gérer des adresses IP pour les règles de Pare-feu Azure.
services: firewall
author: vhorne
ms.service: firewall
ms.topic: conceptual
ms.date: 07/30/2020
ms.author: victorh
ms.openlocfilehash: c56298d68bddd326ed2b32215f30a9057fa51e85
ms.sourcegitcommit: 8e7316bd4c4991de62ea485adca30065e5b86c67
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94653111"
---
# <a name="ip-groups-in-azure-firewall"></a>Groupes IP dans Pare-feu Azure

Les groupes IP vous permettent de regrouper et de gérer des adresses IP pour les règles de Pare-feu Azure de l’une des manières suivantes :

- En tant qu’adresse source dans les règles DNAT
- En tant qu’adresse source ou de destination dans les règles de réseau
- En tant qu’adresse source dans les règles d’application


Un groupe IP peut avoir une seule adresse IP, plusieurs adresses IP ou une ou plusieurs plages d’adresses IP.

Les groupes IP peuvent être réutilisés dans les règles DNAT, de réseau et d’application de Pare-feu Azure pour plusieurs pare-feu dans différentes régions et différents abonnements dans Azure. Les noms de groupes doivent être uniques. Vous pouvez configurer un groupe IP dans le Portail Azure, Azure CLI ou l’API REST. Un exemple de modèle est fourni pour vous aider à démarrer.

## <a name="sample-format"></a>Format d’échantillonnage

Les exemples de format d’adresse IPv4 suivants sont valides pour une utilisation dans les groupes IP :

- Adresse unique : 10.0.0.0
- Notation CIDR : 10.1.0.0/32
- Plage d’adresses : 10.2.0.0-10.2.0.31

## <a name="create-an-ip-group"></a>Créer un groupe IP

Un groupe IP peut être créé à l’aide du Portail Azure, d’Azure CLI ou de l’API REST. Pour plus d’informations, consultez [Créer un groupe IP](create-ip-group.md).

## <a name="browse-ip-groups"></a>Parcourir les groupes IP
1. Dans la barre de recherche du Portail Azure, saisissez **Groupes IP** et sélectionnez le résultat. Vous pouvez voir la liste des groupes IP, ou vous pouvez sélectionner **Ajouter** pour créer un groupe IP.
2. Sélectionnez un groupe IP pour ouvrir la page de présentation. Vous pouvez modifier, ajouter ou supprimer des adresses IP ou des groupes IP.

   ![Présentation des groupes IP](media/ip-groups/overview.png)

## <a name="manage-an-ip-group"></a>Gérer un groupe IP

Vous pouvez voir toutes les adresses IP dans le groupe IP et les règles ou les ressources qui y sont associées. Pour supprimer un groupe IP, vous devez d’abord dissocier le groupe IP de la ressource qui l’utilise.

1. Pour afficher ou modifier les adresses IP, sélectionnez **Adresses IP** sous **Paramètres** dans le volet gauche.
2. Pour ajouter une ou plusieurs adresses IP, sélectionnez **Ajouter des adresses IP**. Cela ouvre la page **Faire glisser ou parcourir** pour un chargement, ou vous pouvez entrer l’adresse manuellement.
3.    Sélectionnez les points de suspension ( **…** ) à droite pour modifier ou supprimer des adresses IP. Pour modifier ou supprimer plusieurs adresses IP, activez les cases à cocher **Modifier** ou **Supprimer** en haut.
4. Enfin, vous pouvez exporter le fichier au format de fichier CSV.

> [!NOTE]
> Si vous supprimez toutes les adresses IP d’un groupe IP alors qu’il est toujours utilisé dans une règle, cette règle sera ignorée.


## <a name="use-an-ip-group"></a>Utiliser un groupe IP

Vous pouvez maintenant sélectionner **Groupe IP** comme **Type source** ou **Type de destination** pour les adresses IP lorsque vous créez des règles de DNAT, d’application ou de réseau de Pare-feu Azure.

![Groupes IP dans Pare-feu](media/ip-groups/fw-ipgroup.png)

## <a name="region-availability"></a>Disponibilité des régions

Les groupes IP sont disponibles dans toutes les régions de cloud public.

## <a name="ip-address-limits"></a>Limites d'adresses IP

Vous pouvez avoir un maximum de 100 groupes d’adresses IP par pare-feu avec un maximum de 5 000 adresses IP ou préfixes IP individuels par groupe d’adresses IP.

## <a name="related-azure-powershell-cmdlets"></a>Cmdlets Azure PowerShell connexes

Vous pouvez utiliser les cmdlets Azure PowerShell suivantes pour créer et gérer des groupes IP :

- [New-AzIpGroup](/powershell/module/az.network/new-azipgroup?view=azps-3.4.0)
- [Remove-AzIPGroup](/powershell/module/az.network/remove-azipgroup?view=azps-3.4.0)
- [Get-AzIpGroup](/powershell/module/az.network/get-azipgroup?view=azps-3.4.0)
- [Set-AzIpGroup](/powershell/module/az.network/set-azipgroup?view=azps-3.4.0)
- [New-AzFirewallNetworkRule](/powershell/module/az.network/new-azfirewallnetworkrule?view=azps-3.4.0)
- [New-AzFirewallApplicationRule](/powershell/module/az.network/new-azfirewallapplicationrule?view=azps-3.4.0)
- [New-AzFirewallNatRule](/powershell/module/az.network/new-azfirewallnatrule?view=azps-3.4.0)

## <a name="next-steps"></a>Étapes suivantes

- Découvrez comment [déployer et configurer un Pare-feu Azure](tutorial-firewall-deploy-portal.md).