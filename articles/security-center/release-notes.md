---
title: Notes de publication pour Azure Security Center
description: Description des nouveautés et modifications apportées à Azure Security Center.
services: security-center
documentationcenter: na
author: memildin
manager: rkarlin
ms.service: security-center
ms.devlang: na
ms.topic: overview
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/07/2021
ms.author: memildin
ms.openlocfilehash: 4e4ee8690822c6caf4a7c5bd69387ea00d6d00a8
ms.sourcegitcommit: 19ffdad48bc4caca8f93c3b067d1cf29234fef47
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97955448"
---
# <a name="whats-new-in-azure-security-center"></a>Nouveautés d’Azure Security Center

Le Centre de sécurité fait l’objet d’un développement actif et bénéficie d’améliorations en permanence. Pour vous tenir au courant des développements les plus récents, cette page fournit des informations sur les nouvelles fonctionnalités, les correctifs de bogues et les fonctionnalités déconseillées.

Cette page étant mise à jour fréquemment, nous vous invitons donc à la consulter souvent. 

Pour en savoir plus sur les changements *planifiés* qui seront bientôt disponibles dans Security Center, consultez [Changements importants à venir dans Azure Security Center](upcoming-changes.md). 

> [!TIP]
> Si vous recherchez des éléments datant de plus de six mois, vous les trouverez dans l’[Archive des nouveautés d’Azure Security Center](release-notes-archive.md).


## <a name="january-2021"></a>Janvier 2021

### <a name="vulnerability-assessment-for-on-premise-and-multi-cloud-machines-is-generally-available"></a>L’évaluation des vulnérabilités pour les machines locales et multicloud est en disponibilité générale

En octobre, nous avions annoncé la préversion de l’analyse des serveurs Azure Arc à l’aide de l’analyseur d’évaluation des vulnérabilités intégré à [Azure Defender pour les serveurs](defender-for-servers-introduction.md) (avec Qualys).

Celle-ci est désormais en disponibilité générale. 

Une fois que vous avez activé Azure Arc sur vos machines non-Azure, Security Center propose de déployer l’analyseur de vulnérabilité intégré dessus, manuellement et à grande échelle.

Avec cette mise à jour, vous pouvez libérer la puissance d’**Azure Defender pour les serveurs** afin de consolider votre programme de gestion des vulnérabilités dans l’ensemble de vos ressources Azure et non-Azure.

Principales fonctionnalités :

- Supervision de l’état de provisionnement de l’analyseur d’évaluation des vulnérabilités sur les machines Azure Arc
- Provisionnement de l’agent d’évaluation des vulnérabilités intégré sur des machines Windows Azure Arc Windows et Linux non protégées (manuellement et à grande échelle)
- Réception et analyse des vulnérabilités détectées par les agents déployés (manuellement et à grande échelle)
- Expérience unifiée pour les machines virtuelles Azure et Azure Arc

[Découvrez-en plus sur le déploiement de l’analyseur de vulnérabilité intégré sur vos machines hybrides](deploy-vulnerability-assessment-vm.md#deploy-the-integrated-scanner-to-your-azure-and-hybrid-machines).

[Découvrez-en plus sur les serveurs avec Azure Arc](../azure-arc/servers/index.yml).


## <a name="december-2020"></a>Décembre 2020

Les mises à jour en décembre sont les suivantes :

- [Azure Defender pour les serveurs SQL sur les machines est en disponibilité générale](#azure-defender-for-sql-servers-on-machines-is-generally-available)
- [La prise en charge par Azure Defender pour SQL de pool SQL dédié Azure Synapse Analytics est en disponibilité générale](#azure-defender-for-sql-support-for-azure-synapse-analytics-dedicated-sql-pool-is-generally-available)
- [Les administrateurs généraux peuvent désormais s’accorder des autorisations de niveau locataire](#global-administrators-can-now-grant-themselves-tenant-level-permissions)
- [Deux nouveaux plans Azure Defender : Azure Defender pour DNS et Azure Defender pour Resource Manager (en préversion)](#two-new-azure-defender-plans-azure-defender-for-dns-and-azure-defender-for-resource-manager-in-preview)
- [Nouvelle page des alertes de sécurité dans le portail Azure (préversion)](#new-security-alerts-page-in-the-azure-portal-preview)
- [Expérience Security Center relancée dans Azure SQL Database et SQL Managed Instance](#revitalized-security-center-experience-in-azure-sql-database--sql-managed-instance)
- [Outils et filtres d’inventaire des ressources mis à jour](#asset-inventory-tools-and-filters-updated)
- [Recommandation sur les applications web demandant des certificats SSL ne faisant plus partie du degré de sécurisation](#recommendation-about-web-apps-requesting-ssl-certificates-no-longer-part-of-secure-score)
- [La page Recommandations contient de nouveaux filtres pour l’environnement, la gravité et les réponses disponibles](#recommendations-page-has-new-filters-for-environment-severity-and-available-responses)
- [L’exportation continue permet d’obtenir de nouveaux types de données et des stratégies deployifnotexist améliorées](#continuous-export-gets-new-data-types-and-improved-deployifnotexist-policies)


### <a name="azure-defender-for-sql-servers-on-machines-is-generally-available"></a>Azure Defender pour les serveurs SQL sur les machines est en disponibilité générale

Azure Security Center propose deux plans Azure Defender pour les serveurs SQL :

- **Azure Defender pour serveurs de base de données Azure SQL** : défend vos serveurs Azure SQL natifs 
- **Azure Defender pour serveurs SQL sur des machines** : étend les mêmes protections à vos serveurs SQL dans des environnements hybrides, multiclouds et locaux.

Avec cette annonce, **Azure Defender pour SQL** protège désormais vos bases de données et leurs données où qu’elles se trouvent.

Azure Defender pour SQL comprend les fonctionnalités d’évaluation des vulnérabilités. L’outil d’évaluation des vulnérabilités comprend les fonctionnalités avancées suivantes :

- **Configuration de base de référence** (nouveau) pour affiner intelligemment les résultats des analyses de vulnérabilité à ceux susceptibles de représenter des problèmes de sécurité réels. Une fois que vous avez établi votre état de sécurité de base de référence, l’outil d’évaluation des vulnérabilités signale uniquement les écarts par rapport à cet état de base de référence. Les résultats correspondant à la base de référence sont considérés comme corrects lors des analyses ultérieures. Cela vous permet, à vous et à vos analystes, de concentrer votre attention sur ce qui est le plus important.
- **Informations de référence détaillées** pour vous aider à *comprendre* les résultats découverts et en quoi ils concernent vos ressources.
- **Scripts de correction** pour vous aider à atténuer les risques identifiés.

En savoir plus sur [Azure Defender pour SQL](defender-for-sql-introduction.md).


### <a name="azure-defender-for-sql-support-for-azure-synapse-analytics-dedicated-sql-pool-is-generally-available"></a>La prise en charge par Azure Defender pour SQL de pool SQL dédié Azure Synapse Analytics est en disponibilité générale

Azure Synapse Analytics (anciennement SQL DW) est un service d’analytique qui combine l’entreposage des données d’entreprise et l’analytique de Big Data. Les pools SQL dédiés sont les fonctionnalités d’entreposage de données d’entreprise d’Azure Synapse. Apprenez-en davantage dans [Qu’est-ce qu’Azure Synapse Analytics (anciennement SQL DW) ?](../synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is.md).

Azure Defender pour SQL protège vos pools SQL dédiés avec :

- **Protection avancée contre les menaces** pour détecter les menaces et les attaques 
- **Fonctionnalités d’évaluation des vulnérabilités** pour identifier et corriger les problèmes de configuration de la sécurité

La prise en charge par Azure Defender pour SQL des pools SQL dédiés Azure Synapse Analytics est ajoutée automatiquement au bundle de bases de données Azure SQL dans Azure Security Center. Vous trouverez un nouvel onglet « Azure Defender pour SQL » dans la page de votre espace de travail Synapse dans le portail Azure.

En savoir plus sur [Azure Defender pour SQL](defender-for-sql-introduction.md).


### <a name="global-administrators-can-now-grant-themselves-tenant-level-permissions"></a>Les administrateurs généraux peuvent désormais s’accorder des autorisations de niveau locataire

Si un utilisateur ayant le rôle Azure Active Directory d’**Administrateur général** peut avoir des responsabilités à l’échelle du locataire, il peut ne pas disposer des autorisations Azure lui permettant de consulter les informations à l’échelle de l’organisation dans Azure Security Center. 

Pour vous attribuer des autorisations de niveau locataire, suivez les instructions fournies dans [S’accorder des autorisations à l’échelle du locataire](security-center-management-groups.md#grant-tenant-wide-permissions-to-yourself).


### <a name="two-new-azure-defender-plans-azure-defender-for-dns-and-azure-defender-for-resource-manager-in-preview"></a>Deux nouveaux plans Azure Defender : Azure Defender pour DNS et Azure Defender pour Resource Manager (en préversion)

Nous avons ajouté deux nouvelles fonctionnalités de protection étendue natives cloud contre les menaces pour votre environnement Azure.

Ces nouvelles protections améliorent nettement votre résilience face aux attaques des acteurs des menaces et accroissent considérablement le nombre de ressources Azure protégées par Azure Defender.

- **Azure Defender pour Ressource Manager** – Supervise automatiquement toutes les opérations de gestion de ressources effectuées dans votre organisation. Pour plus d'informations, consultez les pages suivantes :
    - [Présentation d’Azure Defender pour Resource Manager](defender-for-resource-manager-introduction.md)
    - [Répondre aux alertes Azure Defender pour Resource Manager](defender-for-resource-manager-usage.md)
    - [Liste des alertes fournies par Azure Defender pour Resource Manager](alerts-reference.md#alerts-resourcemanager)

- **Azure Defender pour DNS** – Supervise en continu toutes les requêtes DNS émanant de vos ressources Azure. Pour plus d'informations, consultez les pages suivantes :
    - [Présentation d’Azure Defender pour DNS](defender-for-dns-introduction.md)
    - [Répondre aux alertes Azure Defender pour DNS](defender-for-dns-usage.md)
    - [Liste des alertes fournies par Azure Defender pour DNS](alerts-reference.md#alerts-dns)


### <a name="new-security-alerts-page-in-the-azure-portal-preview"></a>Nouvelle page des alertes de sécurité dans le portail Azure (préversion)

La page des alertes de sécurité d’Azure Security Center a été repensée pour fournir les éléments suivants :

- **Expérience de triage améliorée des alertes** – favorise la réduction d’un trop grand nombre d’alertes et permet de se concentrer plus facilement sur les menaces les plus pertinentes. La liste comprend des filtres personnalisables et des options de regroupement.
- **Plus d’informations dans la liste des alertes** – telles que les tactiques MITRE ATT&ACK.
- **Bouton permettant de créer des exemples d’alertes** – pour évaluer les fonctionnalités Azure Defender et tester la configuration de vos alertes (pour l’intégration SIEM, les notifications par e-mail et les automatisations de workflow), vous pouvez créer des exemples d’alertes à partir de tous les plans Azure Defender.
- **Alignement avec l’expérience d’incident d’Azure Sentinel** – pour les clients qui utilisent les deux produits, le basculement entre eux est désormais une expérience plus simple et il est aisé d’apprendre l’un de l’autre.
- **Amélioration des performances** pour de grandes listes d’alertes.
- **Navigation au clavier** dans la liste des alertes.
- **Alertes à partir d’Azure Resource Graph** – vous pouvez effectuer des requêtes sur des alertes dans Azure Resource Graph, l’API de type Kusto pour toutes vos ressources. Cela est également utile si vous créez vos propres tableaux de bord d’alertes. [Apprenez-en davantage sur Azure Resource Graph](../governance/resource-graph/index.yml).

Pour accéder à la nouvelle expérience, utilisez le lien « Essayer maintenant » dans la bannière en haut de la page des alertes de sécurité.

:::image type="content" source="media/security-center-managing-and-responding-alerts/preview-alerts-experience-banner.png" alt-text="Bannière avec un lien vers la nouvelle expérience d’alertes en préversion":::

Pour créer des exemples d’alertes à partir de la nouvelle expérience Alertes, consultez [Générer des exemples d’alertes Azure Defender](security-center-alert-validation.md#generate-sample-azure-defender-alerts).


### <a name="revitalized-security-center-experience-in-azure-sql-database--sql-managed-instance"></a>Expérience Security Center relancée dans Azure SQL Database et SQL Managed Instance 

L’expérience Security Center dans SQL permet d’accéder aux fonctionnalités Security Center et Azure Defender pour SQL suivantes :

- **Recommandations de sécurité** Security Center analyse régulièrement l’état de sécurité de toutes les ressources Azure connectées pour identifier les erreurs de configuration de sécurité potentielles. Il fournit ensuite des recommandations sur la façon de corriger ces vulnérabilités et d’améliorer l’état de la sécurité des entreprises.
- **Alertes de sécurité** : service de détection qui supervise en continu les activités Azure SQL pour repérer les menaces telles que l’injection de code SQL, les attaques par force brute et l’abus de privilèges. Ce service déclenche des alertes de sécurité détaillées et orientées action dans Security Center et fournit des options pour poursuivre des investigations avec Azure Sentinel, la solution SIEM native Azure de Microsoft.
- **Résultats** : service d’évaluation des vulnérabilités qui supervise en continu les configurations Azure SQL et aide à corriger les vulnérabilités. Les analyses d’évaluation fournissent une vue d’ensemble des états de sécurité Azure SQL ainsi que des résultats de sécurité détaillés.     

:::image type="content" source="media/release-notes/azure-security-center-experience-in-sql.png" alt-text="Les fonctionnalités de sécurité d’Azure Security Center pour SQL sont disponibles à partir d’Azure SQL":::


### <a name="asset-inventory-tools-and-filters-updated"></a>Outils et filtres d’inventaire des ressources mis à jour

La page d’inventaire dans Azure Security Center a été actualisée avec les modifications suivantes :

- **Guides et commentaires** ajoutés à la barre d’outils. Un volet contenant des liens vers des informations et des outils connexes s’ouvre. 
- **Filtre des abonnements** ajouté aux filtres par défaut disponibles pour vos ressources.
- Lien **Ouvrir une requête** pour ouvrir les options du filtre actuel en tant que requête Azure Resource Graph (anciennement « Afficher dans l’Explorateur Resource Graph »).
- **Options des opérateurs** pour chaque filtre. Vous pouvez désormais choisir parmi des opérateurs logiques supplémentaires autres que « = ». Par exemple, vous souhaiterez peut-être rechercher toutes les ressources avec des recommandations actives dont les titres incluent la chaîne « chiffrer ». 

    :::image type="content" source="media/release-notes/inventory-filter-operators.png" alt-text="Contrôles de l’option d’opérateur dans les filtres de l’inventaire des ressources":::

Apprenez-en davantage sur l’inventaire dans [Explorer et gérer vos ressources avec l’inventaire des ressources](asset-inventory.md).


### <a name="recommendation-about-web-apps-requesting-ssl-certificates-no-longer-part-of-secure-score"></a>Recommandation sur les applications web demandant des certificats SSL ne faisant plus partie du degré de sécurisation

La recommandation « Les applications web doivent exiger un certificat SSL pour toutes les demandes entrantes » a été déplacée du contrôle de sécurité **Gérer l’accès et les autorisations** (valeur de 4 points au maximum) dans **Implémenter les bonnes pratiques de sécurité** (qui ne vaut aucun point). 

La garantie que vos applications web demandent un certificat renforce certainement leur sécurité. Toutefois, ce n’est pas pertinent pour les applications web publiques. si vous accédez à votre site sur HTTP et non HTTPS, vous ne recevez pas de certificat client. Ainsi, si votre application nécessite des certificats clients, vous ne devez pas autoriser les requêtes adressées à votre application via HTTP. Pour en savoir plus, consultez [Configurer l’authentification mutuelle TLS pour Azure App Service](../app-service/app-service-web-configure-tls-mutual-auth.md).

Avec ce changement, la recommandation est désormais une bonne pratique, sans impact sur votre score. 

Découvrez les recommandations de chaque contrôle de sécurité dans [Contrôles de sécurité et leurs recommandations](secure-score-security-controls.md#security-controls-and-their-recommendations).


### <a name="recommendations-page-has-new-filters-for-environment-severity-and-available-responses"></a>La page Recommandations contient de nouveaux filtres pour l’environnement, la gravité et les réponses disponibles

Azure Security Center supervise toutes les ressources connectées et génère des recommandations de sécurité. Utilisez ces recommandations pour renforcer l’état de votre cloud hybride et effectuer le suivi de la conformité aux stratégies et normes pertinentes pour vos organisation, secteur d’activité et pays.

Comme Security Center continue d’étendre sa couverture et de développer ses fonctionnalités, la liste des recommandations de sécurité augmente chaque mois. Par exemple, consultez [Ajout de 29 recommandations (préversion) pour mieux détailler le benchmark de sécurité Azure](#29-preview-recommendations-added-to-increase-coverage-of-azure-security-benchmark).

Avec cette liste qui ne cesse de s’allonger, vous devez être en mesure de filtrer les recommandations qui présentent le plus grand intérêt. En novembre, nous avons ajouté des filtres à la page Recommandations (consultez [La liste des recommandations comprend désormais des filtres](#recommendations-list-now-includes-filters)).

Les filtres ajoutés ce mois-ci fournissent des options pour affiner la liste des recommandations en fonction des éléments suivants :

- **Environnement** : affichez les recommandations pour vos ressources AWS, GCP ou Azure (ou n’importe quelle combinaison)
- **Gravité** : affichez les recommandations en fonction de la classification de gravité définie par Security Center
- **Actions de réponse** : affichez les recommandations en fonction de la disponibilité des options de réponse Security Center : Correctif rapide, Refuser et Appliquer

    > [!TIP]
    > Le filtre d’actions de réponse remplace le filtre **Correctif rapide disponible (Oui/Non)** . 
    > 
    > Apprenez-en davantage sur chacune de ces options de réponse :
    > - [Application d’un correctif rapide](security-center-remediate-recommendations.md#quick-fix-remediation)
    > - [Empêcher des configurations incorrectes à l’aide des recommandations Appliquer/Refuser](prevent-misconfigurations.md)

:::image type="content" source="./media/release-notes/added-recommendations-filters.png" alt-text="Recommandations regroupées par contrôle de sécurité" lightbox="./media/release-notes/added-recommendations-filters.png":::

### <a name="continuous-export-gets-new-data-types-and-improved-deployifnotexist-policies"></a>L’exportation continue permet d’obtenir de nouveaux types de données et des stratégies deployifnotexist améliorées

Les outils d’exportation continue d’Azure Security Center vous permettent d’exporter les recommandations et alertes de Security Center en vue de les utiliser avec d’autres outils de supervision dans votre environnement.

L’exportation continue vous permet de personnaliser entièrement ce qui sera exporté et où cela sera exporté. Pour plus d’informations, consultez [Exporter en continu des données Security Center](continuous-export.md).

Ces outils ont été améliorés et développés de différentes manières :

- **Amélioration des stratégies deployifnotexist de l’exportation continue**. À présent, les stratégies :

    - **Vérifient si la configuration est activée.** Si ce n’est pas le cas, la stratégie s’affiche comme non conforme et crée une ressource conforme. Apprenez-en davantage sur les modèles Azure Policy fournis sous l’onglet « Deploy at scale with Azure Policy tab » (Déployer à grande échelle avec Azure Policy) dans [Configurer une exportation continue](continuous-export.md#set-up-a-continuous-export).

    - **Prennent en charge l’exportation des résultats de sécurité.** Quand vous utilisez les modèles Azure Policy, vous pouvez configurer votre exportation continue pour inclure les résultats. Cela s’applique lorsque vous exportez des recommandations avec des « sous-recommandations », telles que les résultats des analyseurs d’évaluation des vulnérabilités ou des mises à jour système spécifiques pour la recommandation « parent », « Des mises à jour système doivent être installées sur vos machines ».
    
    - **Prennent en charge l’exportation des données du degré de sécurisation.**

- **Ajout de données d’évaluation de conformité réglementaire (en préversion).** Vous pouvez désormais exporter en continu des mises à jour pour des évaluations de conformité réglementaire, notamment pour des initiatives personnalisées, vers un espace de travail Log Analytics ou un hub d’événements. Cette fonctionnalité n’est pas disponible sur les clouds nationaux/souverains.

    :::image type="content" source="media/release-notes/continuous-export-regulatory-compliance-option.png" alt-text="Options permettant d’inclure des informations d’évaluation de conformité réglementaire avec vos données d’exportation continue.":::


## <a name="november-2020"></a>Novembre 2020

Les mises à jour en novembre sont les suivantes :

- [Ajout de 29 recommandations (préversion) pour mieux détailler le benchmark de sécurité Azure](#29-preview-recommendations-added-to-increase-coverage-of-azure-security-benchmark)
- [Ajout de NIST SP 800 171 R2 au tableau de bord de conformité réglementaire Security Center](#nist-sp-800-171-r2-added-to-security-centers-regulatory-compliance-dashboard)
- [La liste des recommandations comprend désormais des filtres](#recommendations-list-now-includes-filters)
- [Amélioration et développement de l’expérience de provisionnement automatique](#auto-provisioning-experience-improved-and-expanded)
- [Le score sécurisé est désormais disponible dans l’exportation continue (préversion)](#secure-score-is-now-available-in-continuous-export-preview)
- [La recommandation « Les mises à jour système doivent être installées sur vos machines » inclut désormais des sous-recommandations](#system-updates-should-be-installed-on-your-machines-recommendation-now-includes-sub-recommendations)
- [La page Gestion des stratégies du portail Azure affiche maintenant l’état des affectations de stratégie par défaut](#policy-management-page-in-the-azure-portal-now-shows-status-of-default-policy-assignments)

### <a name="29-preview-recommendations-added-to-increase-coverage-of-azure-security-benchmark"></a>Ajout de 29 recommandations (préversion) pour mieux détailler le benchmark de sécurité Azure

Le Benchmark de sécurité Azure est l’ensemble des directives propres à Azure et créées par Microsoft contenant les bonnes pratiques de sécurité et de conformité basées sur les infrastructures de conformité courantes. [En savoir plus sur le Benchmark de sécurité Azure](../security/benchmarks/introduction.md).

Les 29 recommandations suivantes (préversion) ont été ajoutées à Security Center pour mieux détailler ce benchmark.

Les recommandations en préversion ne rendent pas une ressource non saine et ne sont pas incluses dans les calculs de votre degré de sécurisation. Corrigez-les là où c’est possible, de sorte que quand la période de préversion se termine, elles soient prises en compte dans le calcul de votre degré de sécurisation. Découvrez comment répondre à ces recommandations dans [Corriger les recommandations dans Azure Security Center](security-center-remediate-recommendations.md).

| Contrôle de sécurité                     | Nouvelles recommandations                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Chiffrer les données en transit              | - L’application de la connexion SSL doit être activée pour les serveurs de base de données PostgreSQL<br>- L’application de la connexion SSL doit être activée pour les serveurs de base de données MySQL<br>- TLS doit être mis à jour vers la dernière version pour votre application API<br>- TLS doit être mis à jour vers la dernière version pour votre application de fonction<br>- TLS doit être mis à jour vers la dernière version pour votre application web<br>- FTPS doit être exigé dans votre application API<br>- FTPS doit être exigé dans votre application de fonction<br>- FTPS doit être exigé dans votre application web                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Gérer l’accès et les autorisations        | - Les applications web doivent exiger un certificat SSL pour toutes les demandes entrantes<br>- Une identité managée doit être utilisée dans votre application API<br>- Une identité managée doit être utilisée dans votre application de fonction<br>- Une identité managée doit être utilisée dans votre application web                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Restreindre l’accès réseau non autorisé | - Le point de terminaison privé doit être activé pour les serveurs PostgreSQL<br>- Le point de terminaison privé doit être activé pour les serveurs MariaDB<br>- Le point de terminaison privé doit être activé pour les serveurs MySQL                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Activer l’audit et la journalisation          | - Les journaux de diagnostic d’App Services doivent être activés                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Implémenter les bonnes pratiques de sécurité    | - La Sauvegarde Azure doit être activée pour les machines virtuelles<br>- La sauvegarde géoredondante doit être activée pour Azure Database for MariaDB<br>- La sauvegarde géoredondante doit être activée pour Azure Database pour MySQL<br>- La sauvegarde géoredondante doit être activée pour Azure Database pour PostgreSQL<br>- PHP doit être mis à jour vers la dernière version pour votre application API<br>- PHP doit être mis à jour vers la dernière version pour votre application web<br>- Java doit être mis à jour vers la dernière version pour votre application API<br>- Java doit être mis à jour vers la dernière version pour votre application de fonction<br>- Java doit être mis à jour vers la dernière version pour votre application web<br>- Python doit être mis à jour vers la dernière version pour votre application API<br>- Python doit être mis à jour vers la dernière version pour votre application de fonction<br>- Python doit être mis à jour vers la dernière version pour votre application web<br>- La conservation des audits pour les serveurs SQL Server doit être définie sur au moins 90 jours |
|                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

Liens connexes :

- [En savoir plus sur le Benchmark de sécurité Azure](../security/benchmarks/introduction.md)
- [En savoir plus sur les applications API Azure](../app-service/app-service-web-tutorial-rest-api.md)
- [En savoir plus sur les applications de fonction Azure](../azure-functions/functions-overview.md)
- [En savoir plus sur les applications web Azure](../app-service/overview.md)
- [En savoir plus sur Azure Database for MariaDB](../mariadb/overview.md)
- [En savoir plus sur Azure Database pour MySQL](../mysql/overview.md)
- [En savoir plus sur Azure Database pour PostgreSQL](../postgresql/overview.md)


### <a name="nist-sp-800-171-r2-added-to-security-centers-regulatory-compliance-dashboard"></a>Ajout de NIST SP 800 171 R2 au tableau de bord de conformité réglementaire Security Center

Le standard NIST SP 800-171 R2 est désormais disponible sous la forme d’une initiative intégrée à utiliser avec le tableau de bord de conformité réglementaire Azure Security Center. Les mappages des contrôles sont décrits dans [Détails de l’initiative intégrée de conformité réglementaire NIST SP 800-171 R2](../governance/policy/samples/nist-sp-800-171-r2.md). 

Pour appliquer le standard à vos abonnements et superviser votre état de conformité de façon continue, suivez les instructions fournies dans [Personnalisation de l’ensemble de normes du tableau de bord de conformité réglementaire](update-regulatory-compliance-packages.md).

:::image type="content" source="media/release-notes/nist-sp-800-171-r2-standard.png" alt-text="Standard NIST SP 800 171 R2 dans le tableau de bord de conformité réglementaire Security Center":::

Pour plus d’informations sur cette norme de conformité, consultez [NIST SP 800-171 R2](https://csrc.nist.gov/publications/detail/sp/800-171/rev-2/final).


### <a name="recommendations-list-now-includes-filters"></a>La liste des recommandations comprend désormais des filtres

Vous pouvez maintenant filtrer la liste des recommandations de sécurité en fonction d’une plage de critères. Dans l’exemple suivant, la liste des recommandations a été filtrée pour afficher celles qui :

- sont **généralement disponibles** (c’est-à-dire, pas en préversion)
- concernent les **comptes de stockage**
- prennent en charge la **correction rapide**

:::image type="content" source="media/release-notes/recommendations-filters.png" alt-text="Filtres pour la liste des recommandations":::


### <a name="auto-provisioning-experience-improved-and-expanded"></a>Amélioration et développement de l’expérience de provisionnement automatique

La fonctionnalité de provisionnement automatique permet de réduire la surcharge de gestion en installant les extensions requises sur les machines virtuelles Azure nouvelles et existantes, afin qu’elles puissent tirer parti des protections de Security Center. 

À mesure qu’Azure Security Center se développe, davantage d’extensions ont été développées et Security Center peut superviser une liste plus importante de types de ressources. Les outils de provisionnement automatique ont été développés pour prendre en charge d’autres extensions et types de ressources en tirant parti des fonctionnalités d’Azure Policy.

Vous pouvez maintenant configurer le provisionnement automatique des éléments suivants :

- Agent Log Analytics
- (Nouveau) Module complémentaire Azure Policy pour Kubernetes
- (Nouveau) Microsoft Dependency Agent

Pour en savoir plus, consultez [Provisionnement automatique d’agents et d’extensions à partir d’Azure Security Center](security-center-enable-data-collection.md).


### <a name="secure-score-is-now-available-in-continuous-export-preview"></a>Le score sécurisé est désormais disponible dans l’exportation continue (préversion)

Avec l’exportation continue du score sécurisé, vous pouvez diffuser en streaming les modifications apportées à votre score en temps réel vers Azure Event Hubs ou un espace de travail Log Analytics. Utilisez cette fonctionnalité pour :

- effectuer le suivi de votre score sécurisé au fur et à mesure avec des rapports dynamiques
- exporter les données de score sécurisé vers Azure Sentinel (ou tout autre système SIEM)
- intégrer ces données à tous les processus que vous utilisez peut-être déjà pour surveiller le score sécurisé dans votre organisation

Apprenez-en plus sur la façon d’[exporter en continu des données Security Center](continuous-export.md).


### <a name="system-updates-should-be-installed-on-your-machines-recommendation-now-includes-sub-recommendations"></a>La recommandation « Les mises à jour système doivent être installées sur vos machines » inclut désormais des sous-recommandations

La recommandation **Les mises à jour système doivent être installées sur vos machines** a été améliorée. La nouvelle version inclut des sous-recommandations pour chaque mise à jour manquante et apporte les améliorations suivantes :

- Une expérience repensée dans les pages Azure Security Center du portail Azure. La page Détails de la recommandation pour **Les mises à jour système doivent être installées sur vos machines** comprend la liste des résultats, comme illustré ci-dessous. Lorsque vous sélectionnez une recherche unique, le volet d’informations s’ouvre avec un lien vers des informations de correction et une liste de ressources affectées.

    :::image type="content" source="./media/upcoming-changes/system-updates-should-be-installed-subassessment.png" alt-text="Ouverture de l’une des sous-recommandations dans l’expérience du portail pour la recommandation mise à jour":::

- Des données enrichies pour la recommandation provenant d’Azure Resource Graph (ARG). ARG est un service Azure conçu pour fournir une exploration efficace des ressources. Vous pouvez utiliser ARG pour effectuer une requête à grande échelle sur un ensemble d’abonnements donné, et ainsi gérer de façon optimale votre environnement. 

    Pour Azure Security Center, vous pouvez utiliser ARG et le [langage de requête Kusto (KQL)](/azure/data-explorer/kusto/query/) pour interroger un large éventail de données relatives à la posture de sécurité.

    Avant, si vous interrogiez cette recommandation dans ARG, les seules informations disponibles étaient que la recommandation devait être corrigée sur une machine. La requête suivante de la version améliorée retournera toutes les mises à jour système manquantes, regroupées par machine.

    ```kusto
    securityresources
    | where type =~ "microsoft.security/assessments/subassessments"
    | where extract(@"(?i)providers/Microsoft.Security/assessments/([^/]*)", 1, id) == "4ab6e3c5-74dd-8b35-9ab9-f61b30875b27"
    | where properties.status.code == "Unhealthy"
    ```

### <a name="policy-management-page-in-the-azure-portal-now-shows-status-of-default-policy-assignments"></a>La page Gestion des stratégies du portail Azure affiche maintenant l’état des affectations de stratégie par défaut

Vous pouvez maintenant voir si la stratégie Security Center par défaut est affectée à vos abonnements, dans la page **Stratégie de sécurité** de Security Center du portail Azure.

:::image type="content" source="media/release-notes/policy-assignment-info-per-subscription.png" alt-text="Page Gestion des stratégies d’Azure Security Center présentant les affectations de stratégie par défaut":::

## <a name="october-2020"></a>Octobre 2020

Les mises à jour d’octobre sont les suivantes :
- [Évaluation des vulnérabilités pour les machines locales et multi-cloud (préversion)](#vulnerability-assessment-for-on-premise-and-multi-cloud-machines-preview)
- [Ajout d’une recommandation concernant le pare-feu Azure (préversion)](#azure-firewall-recommendation-added-preview)
- [Des plages d’adresses IP autorisées doivent être définies sur les services Kubernetes - Recommandation mise à jour avec correctif rapide](#authorized-ip-ranges-should-be-defined-on-kubernetes-services-recommendation-updated-with-quick-fix)
- [Le tableau de bord de conformité réglementaire comprend désormais une option de suppression des normes](#regulatory-compliance-dashboard-now-includes-option-to-remove-standards)
- [Suppression de la table Microsoft.Security/securityStatuses d’Azure Resource Graph (ARG)](#microsoftsecuritysecuritystatuses-table-removed-from-azure-resource-graph-arg)

### <a name="vulnerability-assessment-for-on-premise-and-multi-cloud-machines-preview"></a>Évaluation des vulnérabilités pour les machines locales et multi-cloud (préversion)

L’analyseur d’évaluation des vulnérabilités intégré d’[Azure Defender pour les serveurs](defender-for-servers-introduction.md) (fourni par Qualys) analyse désormais les serveurs avec Azure Arc.

Une fois que vous avez activé Azure Arc sur vos machines non-Azure, Security Center propose de déployer l’analyseur de vulnérabilité intégré dessus, manuellement et à grande échelle.

Avec cette mise à jour, vous pouvez libérer la puissance d’**Azure Defender pour les serveurs** afin de consolider votre programme de gestion des vulnérabilités dans l’ensemble de vos ressources Azure et non-Azure.

Principales fonctionnalités :

- Supervision de l’état de provisionnement de l’analyseur d’évaluation des vulnérabilités sur les machines Azure Arc
- Provisionnement de l’agent d’évaluation des vulnérabilités intégré sur des machines Windows Azure Arc Windows et Linux non protégées (manuellement et à grande échelle)
- Réception et analyse des vulnérabilités détectées par les agents déployés (manuellement et à grande échelle)
- Expérience unifiée pour les machines virtuelles Azure et Azure Arc

[Découvrez-en plus sur le déploiement de l’analyseur de vulnérabilité intégré sur vos machines hybrides](deploy-vulnerability-assessment-vm.md#deploy-the-integrated-scanner-to-your-azure-and-hybrid-machines).

[Découvrez-en plus sur les serveurs avec Azure Arc](../azure-arc/servers/index.yml).


### <a name="azure-firewall-recommendation-added-preview"></a>Ajout d’une recommandation concernant le pare-feu Azure (préversion)

Une nouvelle recommandation a été ajoutée pour protéger tous vos réseaux virtuels à l’aide du pare-feu Azure.

La recommandation **Les réseaux virtuels doivent être protégés par le pare-feu Azure** vous conseille de limiter l’accès à vos réseaux virtuels et d’éviter les menaces potentielles à l’aide du pare-feu Azure.

Découvrez le [Pare-feu Azure](https://azure.microsoft.com/services/azure-firewall/).


### <a name="authorized-ip-ranges-should-be-defined-on-kubernetes-services-recommendation-updated-with-quick-fix"></a>Des plages d’adresses IP autorisées doivent être définies sur les services Kubernetes - Recommandation mise à jour avec correctif rapide

La recommandation **Des plages d’adresses IP autorisées doivent être définies sur les services Kubernetes** a maintenant une option de correctif rapide.

Pour plus d’informations sur cette recommandation et toutes les autres recommandations Security Center, consultez [Recommandations de sécurité – Guide de référence](recommendations-reference.md).

:::image type="content" source="./media/release-notes/authorized-ip-ranges-recommendation.png" alt-text="Des plages d’adresses IP autorisées doivent être définies sur les services Kubernetes - Recommandation avec l’option de correctif rapide":::


### <a name="regulatory-compliance-dashboard-now-includes-option-to-remove-standards"></a>Le tableau de bord de conformité réglementaire comprend désormais une option de suppression des normes

Le tableau de bord de conformité réglementaire fournit des insights sur votre posture de conformité d’après la façon dont vous répondez à des exigences et contrôles de conformité spécifiques.

Le tableau de bord comprend un ensemble de normes réglementaires par défaut. Si certaines des normes fournies ne sont pas pertinentes pour votre organisation, vous pouvez maintenant les supprimer facilement de l’interface utilisateur pour un abonnement. Les normes ne peuvent être supprimées qu’au niveau de l’*abonnement*, et non à l’étendue du groupe d’administration.

Pour en savoir plus, consultez [Suppression d’une norme de votre tableau de bord](update-regulatory-compliance-packages.md#removing-a-standard-from-your-dashboard).


### <a name="microsoftsecuritysecuritystatuses-table-removed-from-azure-resource-graph-arg"></a>Suppression de la table Microsoft.Security/securityStatuses d’Azure Resource Graph (ARG)

Azure Resource Graph est un service d’Azure conçu pour fournir une exploration efficace des ressources avec la possibilité de lancer des requêtes à grande échelle sur un ensemble donné d’abonnements pour vous permettre d’optimiser la gestion de votre environnement. 

Pour Azure Security Center, vous pouvez utiliser ARG et le [langage de requête Kusto (KQL)](/azure/data-explorer/kusto/query/) pour interroger un large éventail de données relatives à la posture de sécurité. Par exemple :

- L’inventaire des ressources utilise Azure Resource Graph (ARG)
- Nous avons documenté un exemple de requête ARG pour savoir comment [identifier les comptes sans authentification multifacteur (MFA) activée](security-center-identity-access.md#identify-accounts-without-multi-factor-authentication-mfa-enabled)

Dans ARG, il existe des tables de données que vous pouvez utiliser dans vos requêtes.

:::image type="content" source="./media/release-notes/azure-resource-graph-tables.png" alt-text="Explorateur Azure Resource Graph et les tables disponibles":::

> [!TIP]
> La documentation ARG liste toutes les tables disponibles dans [Informations de référence sur les types de ressource et les tables Azure Resource Graph](../governance/resource-graph/reference/supported-tables-resources.md).

À compter de cette mise à jour, la table **Microsoft.Security/securityStatuses** a été supprimée. L’API securityStatuses est toujours disponible.

Le remplacement de données peut être utilisé par la table Microsoft.Security/Assessments.

La principale différence entre Microsoft.Security/securityStatuses et Microsoft.Security/Assessments est que la première montre l’agrégation des évaluations tandis que la deuxième contient un enregistrement unique pour chacune d’entre elles.

Par exemple, Microsoft. Microsoft.Security/securityStatuses retourne un résultat avec un tableau de deux valeurs policyAssessments :

```
{
id: "/subscriptions/449bcidd-3470-4804-ab56-2752595 felab/resourceGroups/mico-rg/providers/Microsoft.Network/virtualNetworks/mico-rg-vnet/providers/Microsoft.Security/securityStatuses/mico-rg-vnet",
name: "mico-rg-vnet",
type: "Microsoft.Security/securityStatuses",
properties:  {
    policyAssessments: [
        {assessmentKey: "e3deicce-f4dd-3b34-e496-8b5381bazd7e", category: "Networking", policyName: "Azure DDOS Protection Standard should be enabled",...},
        {assessmentKey: "sefac66a-1ec5-b063-a824-eb28671dc527", category: "Compute", policyName: "",...}
    ],
    securitystateByCategory: [{category: "Networking", securityState: "None" }, {category: "Compute",...],
    name: "GenericResourceHealthProperties",
    type: "VirtualNetwork",
    securitystate: "High"
}
```
Tandis que Microsoft.Security/Assessments contient un enregistrement pour chaque évaluation de stratégie de ce type, comme suit :

```
{
type: "Microsoft.Security/assessments",
id:  "/subscriptions/449bc1dd-3470-4804-ab56-2752595f01ab/resourceGroups/mico-rg/providers/Microsoft. Network/virtualNetworks/mico-rg-vnet/providers/Microsoft.Security/assessments/e3delcce-f4dd-3b34-e496-8b5381ba2d70",
name: "e3deicce-f4dd-3b34-e496-8b5381ba2d70",
properties:  {
    resourceDetails: {Source: "Azure", Id: "/subscriptions/449bc1dd-3470-4804-ab56-2752595f01ab/resourceGroups/mico-rg/providers/Microsoft.Network/virtualNetworks/mico-rg-vnet"...},
    displayName: "Azure DDOS Protection Standard should be enabled",
    status: (code: "NotApplicable", cause: "VnetHasNOAppGateways", description: "There are no Application Gateway resources attached to this Virtual Network"...}
}

{
type: "Microsoft.Security/assessments",
id:  "/subscriptions/449bc1dd-3470-4804-ab56-2752595f01ab/resourcegroups/mico-rg/providers/microsoft.network/virtualnetworks/mico-rg-vnet/providers/Microsoft.Security/assessments/80fac66a-1ec5-be63-a824-eb28671dc527",
name: "8efac66a-1ec5-be63-a824-eb28671dc527",
properties: {
    resourceDetails: (Source: "Azure", Id: "/subscriptions/449bc1dd-3470-4804-ab56-2752595f01ab/resourcegroups/mico-rg/providers/microsoft.network/virtualnetworks/mico-rg-vnet"...),
    displayName: "Audit diagnostic setting",
    status:  {code: "Unhealthy"}
}
```

**Exemple de conversion d’une requête ARG existante à l’aide de securityStatuses pour utiliser à présent la table des évaluations (Assessments) :**

Requête qui référence securityStatuses :

```kusto
SecurityResources 
| where type == 'microsoft.security/securitystatuses' and properties.type == 'virtualMachine'
| where name in ({vmnames}) 
| project name, resourceGroup, policyAssesments = properties.policyAssessments, resourceRegion = location, id, resourceDetails = properties.resourceDetails
```

Requête de remplacement pour la table Assessments :

```kusto
securityresources
| where type == "microsoft.security/assessments" and id contains "virtualMachine"
| extend resourceName = extract(@"(?i)/([^/]*)/providers/Microsoft.Security/assessments", 1, id)
| extend source = tostring(properties.resourceDetails.Source)
| extend resourceId = trim(" ", tolower(tostring(case(source =~ "azure", properties.resourceDetails.Id,
source =~ "aws", properties.additionalData.AzureResourceId,
source =~ "gcp", properties.additionalData.AzureResourceId,
extract("^(.+)/providers/Microsoft.Security/assessments/.+$",1,id)))))
| extend resourceGroup = tolower(tostring(split(resourceId, "/")[4]))
| where resourceName in ({vmnames}) 
| project resourceName, resourceGroup, resourceRegion = location, id, resourceDetails = properties.additionalData
```

Pour en savoir plus, consultez les liens suivants :
- [Procédure pour créer des requêtes avec l’Explorateur Azure Resource Graph](../governance/resource-graph/first-query-portal.md)
- [Langage de requête Kusto (KQL)](/azure/data-explorer/kusto/query/)


## <a name="september-2020"></a>Septembre 2020

Les mises à jour en septembre sont les suivantes :
- [Security Center fait peau neuve !](#security-center-gets-a-new-look)
- [Publication d’Azure Defender](#azure-defender-released)
- [Azure Defender pour Key Vault est mis à la disposition générale](#azure-defender-for-key-vault-is-generally-available)
- [Azure Defender pour la protection du stockage des fichiers et d’ADLS Gen2 est mis à la disposition générale](#azure-defender-for-storage-protection-for-files-and-adls-gen2-is-generally-available)
- [Les outils d’inventaire des ressources sont désormais mis à la disposition générale](#asset-inventory-tools-are-now-generally-available)
- [Désactiver le résultat d’une vulnérabilité précise pour les images de registres de conteneurs et les machines virtuelles](#disable-a-specific-vulnerability-finding-for-scans-of-container-registries-and-virtual-machines)
- [Exempter une ressource d’une recommandation](#exempt-a-resource-from-a-recommendation)
- [Les connecteurs AWS et GCP dans Security Center apportent une expérience multicloud](#aws-and-gcp-connectors-in-security-center-bring-a-multi-cloud-experience)
- [Bundle Kubernetes de recommandations sur la protection des charges de travail](#kubernetes-workload-protection-recommendation-bundle)
- [Les résultats de l’évaluation des vulnérabilités sont désormais disponibles dans l’exportation continue](#vulnerability-assessment-findings-are-now-available-in-continuous-export)
- [Empêcher les erreurs de configurations de sécurité en appliquant des recommandations lors de la création de nouvelles ressources](#prevent-security-misconfigurations-by-enforcing-recommendations-when-creating-new-resources)
- [Recommandations de groupe de sécurité réseau améliorées](#network-security-group-recommendations-improved)
- [Recommandation de la préversion AKS déconseillée : « Des stratégies de sécurité de pods doivent être définies sur les services Kubernetes »](#deprecated-preview-aks-recommendation-pod-security-policies-should-be-defined-on-kubernetes-services)
- [Notifications par e-mail améliorées dans Azure Security Center](#email-notifications-from-azure-security-center-improved)
- [Le degré de sécurisation n’inclut pas de recommandations sur la préversion](#secure-score-doesnt-include-preview-recommendations)
- [Les recommandations incluent désormais un indicateur de gravité et l’intervalle d’actualisation](#recommendations-now-include-a-severity-indicator-and-the-freshness-interval)


### <a name="security-center-gets-a-new-look"></a>Security Center fait peau neuve !

Nous avons publié une interface utilisateur actualisée pour les pages du portail de Security Center. Les nouvelles pages incluent une nouvelle page vue d’ensemble, ainsi que des tableaux de bord pour le degré de sécurisation, l’inventaire des ressources et Azure Defender.

La page vue d’ensemble repensée présente désormais une vignette permettant d’accéder aux tableaux de bord du degré de sécurisation, de l’inventaire des ressources et d’Azure Defender. Elle comporte également une vignette qui renvoie au tableau de bord de conformité réglementaire.

En savoir plus sur la [page vue d’ensemble](overview-page.md).


### <a name="azure-defender-released"></a>Publication d’Azure Defender

**Azure Defender** est une plate-forme de protection de la charge de travail Cloud (CWPP) intégrée à Security Center pour une protection intelligente et avancée de vos charges de travail Azure et hybrides. Elle remplace l’option de niveau tarifaire standard de Security Center. 

Lorsque vous activez Azure Defender à partir de la zone **Tarification et paramètres** d’Azure Security Center, les plans Defender suivants sont tous activés simultanément et fournissent des défenses complètes pour les couches de calcul, de données et de service de votre environnement :

- [Azure Defender pour les serveurs](defender-for-servers-introduction.md)
- [Azure Defender pour App Service](defender-for-app-service-introduction.md)
- [Azure Defender pour Stockage](defender-for-storage-introduction.md)
- [Azure Defender pour SQL](defender-for-sql-introduction.md)
- [Azure Defender pour Key Vault](defender-for-key-vault-introduction.md)
- [Azure Defender pour Kubernetes](defender-for-kubernetes-introduction.md)
- [Azure Defender pour les registres de conteneurs](defender-for-container-registries-introduction.md)

Chacun de ces plans est expliqué séparément dans la documentation relative à Security Center.

Avec ses tableaux de bord dédiés, Azure Defender propose des alertes de sécurité ainsi que la protection avancée contre les menaces pour les machines virtuelles, les bases de données SQL, les conteneurs, les applications web, votre réseau, et bien plus encore.

[En savoir plus sur Azure Defender](azure-defender.md)

### <a name="azure-defender-for-key-vault-is-generally-available"></a>Azure Defender pour Key Vault est mis à la disposition générale

Azure Key Vault est un service cloud qui protège les clés et secrets de chiffrement comme les certificats, chaînes de connexion et mots de passe. 

**Azure Defender pour Key Vault** fournit une protection native Azure avancée contre les menaces pour Azure Key Vault, apportant une couche supplémentaire de renseignements de sécurité. Par extension, Azure Defender pour Key Vault protège de nombreuses ressources dépendantes de vos comptes de Key Vault.

Le plan facultatif est désormais en disponibilité générale. Dans la préversion, cette fonctionnalité s’appelait « protection avancée contre les menaces pour Azure Key Vault ».

En outre, les pages de Key Vault dans le portail Azure comprennent désormais une page dédiée à la **Sécurité** pour gérer les recommandations et les alertes de **Security Center**.

Consultez [Azure Defender pour Key Vault](defender-for-key-vault-introduction.md) pour en savoir plus.


### <a name="azure-defender-for-storage-protection-for-files-and-adls-gen2-is-generally-available"></a>Azure Defender pour la protection du stockage des fichiers et d’ADLS Gen2 est mis à la disposition générale 

**Azure Defender pour Stockage** détecte les activités potentiellement dangereuses sur vos comptes de stockage Azure. Vos données peuvent être protégées, qu’elles soient stockées en tant que conteneurs blob, de partages de fichiers ou de lacs de données.

Le support d’[Azure Files](../storage/files/storage-files-introduction.md) et d’[Azure Data Lake Storage Gen2](../storage/blobs/data-lake-storage-introduction.md) est désormais mis à la disposition générale.

À partir du 1er octobre 2020, nous commencerons à facturer la protection des ressources sur ces services.

Consultez [Azure Defender pour Stockage](defender-for-storage-introduction.md) pour en savoir plus.


### <a name="asset-inventory-tools-are-now-generally-available"></a>Les outils d’inventaire des ressources sont désormais mis à la disposition générale

La page d’inventaire des ressources d’Azure Security Center fournit une page unique pour visualiser la posture de sécurité des ressources que vous avez connectées à Security Center.

Security Center analyse périodiquement l’état de sécurité de vos ressources Azure pour identifier les vulnérabilités de sécurité potentielles. Il fournit ensuite des recommandations sur la façon de corriger ces vulnérabilités.

Lorsqu’une ressource contient des recommandations en suspens, celles-ci apparaissent dans l’inventaire.

Pour en savoir plus, consultez [Explorer et gérer vos ressources avec l’inventaire des ressources](asset-inventory.md).



### <a name="disable-a-specific-vulnerability-finding-for-scans-of-container-registries-and-virtual-machines"></a>Désactiver le résultat d’une vulnérabilité précise pour les images de registres de conteneurs et les machines virtuelles

Azure Defender comprend des analyseurs de vulnérabilités pour examiner les images dans votre Azure Container Registry et vos machines virtuelles.

Si votre organisation préfère ignorer un résultat, plutôt que de le corriger, vous pouvez éventuellement désactiver cette fonction. Les résultats désactivés n’ont pas d’impact sur votre Niveau de sécurité ni ne génèrent de bruit indésirable.

Lorsqu’un résultat correspondra aux critères que vous avez définis dans vos règles de désactivation, il n’apparaîtra plus dans la liste des résultats.

Cette option est disponible dans les pages « Détails des recommandations » pour :

- **Les vulnérabilités dans les images Azure Container Registry doivent être corrigées**
- **Les vulnérabilités de vos machines virtuelles doivent être corrigées**

Pour plus d’informations, consultez [Désactiver des résultats spécifiques pour vos images de conteneur](defender-for-container-registries-usage.md#disable-specific-findings-preview) et [Désactiver des résultats spécifiques pour vos machines virtuelles](remediate-vulnerability-findings-vm.md#disable-specific-findings-preview).


### <a name="exempt-a-resource-from-a-recommendation"></a>Exempter une ressource d’une recommandation

Il peut arriver qu’une ressource soit signalée comme non saine en ce qui concerne une recommandation spécifique (faisant baisser par conséquent le degré de sécurisation), même si vous estimez qu’elle ne devrait pas l’être. Elle a peut-être été corrigée par un processus non suivi par Security Center. Ou bien votre organisation a décidé d’accepter le risque pour cette ressource spécifique. 

Dans ce cas, vous pouvez créer une règle d’exemption et veiller à ce que la ressource ne figure plus parmi les ressources non saines à l’avenir. Ces règles peuvent contenir des justifications documentées comme décrit ci-dessous.

Pour plus d’informations, consultez [Exempter une ressource des recommandations et du degré de sécurisation](exempt-resource.md).


### <a name="aws-and-gcp-connectors-in-security-center-bring-a-multi-cloud-experience"></a>Les connecteurs AWS et GCP dans Security Center apportent une expérience multicloud

Les charges de travail cloud couvrant généralement plusieurs plates-formes cloud, les services de sécurité cloud se doivent d’en faire de même.

Azure Security Center protège désormais les charges de travail dans Azure, Amazon Web Services (AWS) et Google Cloud Platform (GCP).

L’intégration de vos comptes AWS et GCP dans Security Center intègre Azure Security Hub, GCP Security Command et Azure Security Center. 

Pour plus d’informations, consultez [Connecter vos comptes AWS à Azure Security Center](quickstart-onboard-aws.md) et [Connecter vos comptes GCP à Azure Security Center](quickstart-onboard-gcp.md).


### <a name="kubernetes-workload-protection-recommendation-bundle"></a>Bundle Kubernetes de recommandations sur la protection des charges de travail

Pour vous assurer que les charges de travail Kubernetes sont sécurisées par défaut, Security Center ajoute des recommandations de renforcement au niveau de Kubernetes, y compris des options de mise en œuvre avec le contrôle d’admission Kubernetes.

Lorsque vous avez installé le module complémentaire Azure Policy pour Kubernetes sur votre cluster AKS, toutes les requêtes adressées au serveur d’API Kubernetes sont analysées par rapport à l’ensemble prédéfini de meilleures pratiques avant d’être conservées sur le cluster. Vous pouvez ensuite configurer la mise en œuvre des meilleures pratiques et les imposer aux charges de travail futures.

Par exemple, vous pouvez interdire la création de conteneurs privilégiés, et faire en sorte que toutes les demandes ultérieures soient bloquées.

Consultez [Meilleures pratiques de protection de charge de travail à l’aide du contrôle d’admission Kubernetes](container-security.md#workload-protection-best-practices-using-kubernetes-admission-control) pour en savoir plus.


### <a name="vulnerability-assessment-findings-are-now-available-in-continuous-export"></a>Les résultats de l’évaluation des vulnérabilités sont désormais disponibles dans l’exportation continue

Utilisez l’exportation continue pour diffuser vos alertes et vos recommandations en temps réel vers Azure Event Hubs, les espaces de travail Log Analytics ou Azure Monitor. À partir de là, vous pouvez intégrer ces données à des informations de sécurité et gestion d’événements (par exemple, Azure Sentinel, Power BI, Azure Data Explorer et bien plus.)

Les outils d’évaluation des vulnérabilités intégrés à Security Center renvoient des résultats sur vos ressources comme recommandations exploitables dans le cadre d’une recommandation « parent », telle que « les vulnérabilités de vos machines virtuelles doivent être corrigées ». 

Les résultats de sécurité sont désormais disponibles pour l’exportation via l’exportation continue lorsque vous sélectionnez recommandations et activez l’option **Inclure les résultats de sécurité**.

:::image type="content" source="./media/continuous-export/include-security-findings-toggle.png" alt-text="Intégrer les résultats de sécurité dans la configuration de l’exportation continue" :::

Pages connexes :

- [Solution intégrée d’évaluation des vulnérabilités de Security Center pour les machines virtuelles Azure](deploy-vulnerability-assessment-vm.md)
- [Solution d’évaluation des vulnérabilités intégrée à Security Center pour les images Azure Container Registry](defender-for-container-registries-usage.md)
- [Exportation continue](continuous-export.md)

### <a name="prevent-security-misconfigurations-by-enforcing-recommendations-when-creating-new-resources"></a>Empêcher les erreurs de configurations de sécurité en appliquant des recommandations lors de la création de nouvelles ressources

Les erreurs de configuration de la sécurité sont à l’origine de la plupart des incidents. Security Center vous permet désormais de *prévenir* les erreurs de configuration des nouvelles ressources en ce qui concerne les recommandations spécifiques. 

Cette fonctionnalité peut vous aider à sécuriser vos charges de travail et à stabiliser votre degré de sécurisation.

La mise en œuvre d’une configuration sécurisée, basée sur une recommandation spécifique, est proposée en deux modes :

- En utilisant l’effet **Refuser** d’Azure Policy, vous pouvez empêcher la création de ressources non saines

- À l’aide de l’option **Appliquer** , vous pouvez tirer parti de l’effet **DeployIfNotExist** de la stratégie Azure et corriger automatiquement les ressources non saines lors de leur création
 
Cette option est disponible pour les recommandations de sécurité sélectionnées et se trouve en haut de la page Détails de la ressource.

Pour plus d’informations, consultez [Empêcher des configurations incorrectes à l’aide des recommandations Appliquer/Refuser](prevent-misconfigurations.md).

###  <a name="network-security-group-recommendations-improved"></a>Recommandations de groupe de sécurité réseau améliorées

Les recommandations de sécurité suivantes relatives aux groupes de sécurité réseau ont été améliorées pour réduire certaines instances de faux positifs.

- Tous les ports réseau doivent être limités sur le groupe de sécurité réseau associé à votre machine virtuelle
- Les ports de gestion doivent être fermés sur vos machines virtuelles
- Les machines virtuelles accessibles à partir d’Internet doivent être protégées avec des groupes de sécurité réseau
- Les sous-réseaux doivent être associés à un groupe de sécurité réseau


### <a name="deprecated-preview-aks-recommendation-pod-security-policies-should-be-defined-on-kubernetes-services"></a>Recommandation de la préversion AKS déconseillée : « Des stratégies de sécurité de pods doivent être définies sur les services Kubernetes »

La recommandation de préversion « Des stratégies de sécurité de pods doivent être définies sur les services Kubernetes » est déconseillée comme décrit dans la documentation [Azure Kubernetes Service](../aks/use-pod-security-policies.md).

La fonctionnalité « stratégie de sécurité des pods (préversion) », sera bientôt déconseillée et ne sera plus disponible après le 15 octobre 2020 pour laisser place à Azure Policy pour AKS.

Une fois que la stratégie de sécurité des pods (préversion) sera déconseillée, vous devrez désactiver la fonctionnalité sur tous les clusters existants à l’aide de la fonctionnalité déconseillée pour effectuer les futures mises à niveau de cluster et continuer à bénéficier du support Azure.


### <a name="email-notifications-from-azure-security-center-improved"></a>Notifications par e-mail améliorées dans Azure Security Center

Les zones suivantes des e-mails concernant les alertes de sécurité ont été améliorées : 

- ajout de la possibilité d’envoyer des notifications par e-mail concernant les alertes pour tous les niveaux de gravité
- La possibilité d’informer les utilisateurs avec différents rôles Azure sur l’abonnement a été ajoutée
- Nous avertissons de manière proactive les propriétaires d’abonnements par défaut sur les alertes de gravité élevée (qui ont une probabilité élevée d’être des violations authentiques)
- Nous avons supprimé le champ du numéro de téléphone de la page de configuration des notifications par e-mail

Consultez [Configurer les notifications par e-mail pour les alertes de sécurité](security-center-provide-security-contact-details.md) pour en savoir plus.


### <a name="secure-score-doesnt-include-preview-recommendations"></a>Le degré de sécurisation n’inclut pas de recommandations sur la préversion 

Security Center évalue continuellement vos ressources, vos abonnements et votre organisation en recherchant d’éventuels problèmes de sécurité. Il agrège ensuite toutes ses découvertes sous la forme d’un score qui vous permet de déterminer d’un coup d’œil votre niveau de sécurité actuel : plus le score est élevé, plus le niveau de risque identifié est faible.

À mesure que de nouvelles menaces sont découvertes, de nouveaux conseils en matière de sécurité sont mis à disposition dans Security Center via la création de recommandations. Pour éviter que des modifications ne soient apportées à votre degré de sécurisation et pour fournir une période de grâce pendant laquelle vous pouvez découvrir de nouvelles recommandations avant qu’elles n’aient un impact sur vos scores, les recommandations marquées **Preview (Préversion)** ne sont plus incluses dans les calculs du degré de sécurisation. Elles doivent tout de même être corrigées dans la mesure du possible, ainsi lorsque la période de préversion se termine, elles seront prises en compte dans le calcul.

En outre, les recommandations **Preview (Préversion)** de préversion n’affichent pas de ressources « non saines ».

Exemple de recommandation de préversion :

:::image type="content" source="./media/secure-score-security-controls/example-of-preview-recommendation.png" alt-text="Recommandation portant l’indicateur Preview (Préversion)":::

[En savoir plus sur le degré de sécurisation](secure-score-security-controls.md).


### <a name="recommendations-now-include-a-severity-indicator-and-the-freshness-interval"></a>Les recommandations incluent désormais un indicateur de gravité et l’intervalle d’actualisation

La page de détails des recommandations comprend désormais un indicateur d’intervalle d’actualisation (le cas échéant) et affiche clairement la gravité de la recommandation.

:::image type="content" source="./media/release-notes/recommendations-severity-freshness-indicators.png" alt-text="Page de recommandation affichant l’actualisation et la gravité":::



## <a name="august-2020"></a>Août 2020

Les mises à jour en août sont les suivantes :

- [Inventaire des ressources : nouvelle vue puissante de la position de sécurité de vos ressources](#asset-inventory---powerful-new-view-of-the-security-posture-of-your-assets)
- [Ajout de la prise en charge des paramètres de sécurité par défaut d’Azure Active Directory (pour l’authentification multifacteur)](#added-support-for-azure-active-directory-security-defaults-for-multi-factor-authentication)
- [Ajout d’une recommandation en faveur des principaux de service](#service-principals-recommendation-added)
- [Évaluation des vulnérabilités sur les machines virtuelles - recommandations et stratégies consolidées](#vulnerability-assessment-on-vms---recommendations-and-policies-consolidated)
- [Nouvelles stratégies de sécurité AKS ajoutées à ASC_default initiative : pour une utilisation par les clients de la préversion privée uniquement](#new-aks-security-policies-added-to-asc_default-initiative--for-use-by-private-preview-customers-only)


### <a name="asset-inventory---powerful-new-view-of-the-security-posture-of-your-assets"></a>Inventaire des ressources : nouvelle vue puissante de la position de sécurité de vos ressources

L’inventaire des ressources de Security Center (actuellement en préversion) permet de visualiser la posture de sécurité des ressources que vous avez connectées à Security Center.

Security Center analyse périodiquement l’état de sécurité de vos ressources Azure pour identifier les vulnérabilités de sécurité potentielles. Il fournit ensuite des recommandations sur la façon de corriger ces vulnérabilités. Lorsqu’une ressource contient des recommandations en suspens, celles-ci apparaissent dans l’inventaire.

Vous pouvez utiliser la vue et ses filtres pour explorer les données relatives à votre posture de sécurité et prendre d’autres mesures en fonction de vos conclusions.

En savoir plus sur l’[inventaire des ressources](asset-inventory.md).


### <a name="added-support-for-azure-active-directory-security-defaults-for-multi-factor-authentication"></a>Ajout de la prise en charge des paramètres de sécurité par défaut d’Azure Active Directory (pour l’authentification multifacteur)

Security Center a ajouté la prise en charge complète des [paramètres de sécurité par défaut](../active-directory/fundamentals/concept-fundamentals-security-defaults.md), les protections gratuites de Microsoft en matière de sécurité de l’identité.

Les paramètres de sécurité par défaut fournissent des paramètres de sécurité d’identité préconfigurés pour défendre votre organisation contre les attaques courantes liées aux identités. Les paramètres de sécurité par défaut protègent déjà plus de 5 millions de locataires ; 50 000 locataires sont également protégés par Security Center.

Security Center fournit désormais une recommandation de sécurité chaque fois qu’il identifie un abonnement Azure sans activation des paramètres de sécurité par défaut. Jusqu’à présent, Security Center recommandait d’activer l’authentification multifacteur à l’aide de l’accès conditionnel, qui fait partie de la licence Premium d’Azure Active Directory (AD). Pour les clients qui utilisent Azure AD gratuitement, nous vous recommandons maintenant d’activer les paramètres de sécurité par défaut. 

Notre objectif est d’encourager un plus grand nombre de clients à sécuriser leurs environnements cloud grâce à l’authentification multifacteur et d’atténuer l’un des risques les plus élevés, qui est également le plus important pour votre [score de sécurité](secure-score-security-controls.md).

En savoir plus sur les [paramètres de sécurité par défaut](../active-directory/fundamentals/concept-fundamentals-security-defaults.md).


### <a name="service-principals-recommendation-added"></a>Ajout d’une recommandation en faveur des principaux de service

Une nouvelle recommandation a été ajoutée pour recommander aux clients de Security Center qui utilisent des certificats de gestion pour gérer leurs abonnements de basculer vers des principaux de service.

La recommandation **Des principaux de service doivent être utilisés pour protéger vos abonnements à la place des certificats de gestion** vous conseille d’utiliser des principaux de service ou Azure Resource Manager de gérer vos abonnements de manière plus sécurisée. 

En savoir plus sur [Objets du principal du service et de l’application dans Azure Active Directory](../active-directory/develop/app-objects-and-service-principals.md#service-principal-object).


### <a name="vulnerability-assessment-on-vms---recommendations-and-policies-consolidated"></a>Évaluation des vulnérabilités sur les machines virtuelles - recommandations et stratégies consolidées

Security Center inspecte vos machines virtuelles pour vérifier si elles exécutent une solution d’évaluation des vulnérabilités. Si aucune solution d’évaluation des vulnérabilités n’est trouvée, Security Center fournit une recommandation pour simplifier le déploiement.

Lorsque des vulnérabilités sont détectées, Security Center fournit une recommandation résumant les résultats à examiner et à corriger si nécessaire.

Pour garantir une expérience cohérente pour tous les utilisateurs, quel que soit le type d’analyse utilisé, nous avons unifié quatre recommandations dans les deux cas suivants :

|Recommandation unifiée|Description de la modification|
|----|:----|
|**Une solution d’évaluation des vulnérabilités doit être activée sur vos machines virtuelles**|Remplace les deux recommandations suivantes :<br> **•** Activer la solution intégrée d’évaluation des vulnérabilités sur les machines virtuelles (par Qualys) (désormais déconseillée) (incluse avec le niveau standard)<br> **•** La solution d’évaluation des vulnérabilités doit être installée sur vos machines virtuelles (désormais déconseillée) (niveaux standard et gratuits)|
|**Les vulnérabilités de vos machines virtuelles doivent être corrigées**|Remplace les deux recommandations suivantes :<br>**•** Corriger les vulnérabilités trouvées sur vos machines virtuelles (avec Qualys) (à présent déconseillée)<br>**•** Les vulnérabilités doivent être corrigées avec une solution d’évaluation des vulnérabilités (à présent déconseillée)|
|||

Vous allez maintenant utiliser la même recommandation pour déployer l’extension d’évaluation de la vulnérabilité de Security Center ou une solution sous licence privée (« BYOL ») d’un partenaire tel que Qualys ou Rapid7.

De plus, lorsque des vulnérabilités sont détectées et signalées à Security Center, une recommandation unique vous avertit des conclusions, quelle que soit la solution d’évaluation des vulnérabilités qui les a identifiées.

#### <a name="updating-dependencies"></a>Mise à jour des dépendances

Si vous avez des scripts, des requêtes ou des automations qui font référence aux recommandations ou aux clés/noms de stratégie précédents, utilisez les tableaux ci-dessous pour mettre à jour les références :

##### <a name="before-august-2020"></a>Avant août 2020

|Recommandation|Étendue|
|----|:----|
|**Activer la solution intégrée d’évaluation des vulnérabilités sur les machines virtuelles (par Qualys)**<br>Clé : 550e890b-e652-4d22-8274-60b3bdb24c63|Intégré|
|**Corriger les vulnérabilités trouvées sur vos machines virtuelles (avec Qualys)**<br>Clé : 1195afff-c881-495e-9bc5-1486211ae03f|Intégré|
|**La solution d’évaluation des vulnérabilités doit être installée sur vos machines virtuelles**<br>Clé : 01b1ed4c-b733-4fee-b145-f23236e70cf3|BYOL|
|**Les vulnérabilités doivent être corrigées avec une solution d’évaluation des vulnérabilités**<br>Clé : 71992a2a-d168-42e0-b10e-6b45fa2ecddb|BYOL|
||||


|Policy|Étendue|
|----|:----|
|**L’évaluation des vulnérabilités doit être activée sur les machines virtuelles**<br>ID de stratégie : 501541f7-f7e7-4cd6-868c-4190fdad3ac9|Intégré|
|**Les vulnérabilités doivent être corrigées avec une solution d’évaluation des vulnérabilités**<br>ID de stratégie : 760a85ff-6162-42b3-8d70-698e268f648c|BYOL|
||||


##### <a name="from-august-2020"></a>À partir d’août 2020

|Recommandation|Étendue|
|----|:----|
|**Une solution d’évaluation des vulnérabilités doit être activée sur vos machines virtuelles**<br>Clé : ffff0522-1e88-47fc-8382-2a80ba848f5d|Intégré + BYOL|
|**Les vulnérabilités de vos machines virtuelles doivent être corrigées**<br>Clé : 1195afff-c881-495e-9bc5-1486211ae03f|Intégré + BYOL|
||||

|Policy|Étendue|
|----|:----|
|[**L’évaluation des vulnérabilités doit être activée sur les machines virtuelles**](https://portal.azure.com/#blade/Microsoft_Azure_Policy/PolicyDetailBlade/definitionId/%2fproviders%2fMicrosoft.Authorization%2fpolicyDefinitions%2f501541f7-f7e7-4cd6-868c-4190fdad3ac9)<br>ID de stratégie : 501541f7-f7e7-4cd6-868c-4190fdad3ac9 |Intégré + BYOL|
||||


### <a name="new-aks-security-policies-added-to-asc_default-initiative--for-use-by-private-preview-customers-only"></a>Nouvelles stratégies de sécurité AKS ajoutées à ASC_default initiative : pour une utilisation par les clients de la préversion privée uniquement

Pour vous assurer que les charges de travail Kubernetes sont sécurisées par défaut, Security Center ajoute des stratégies de niveau Kubernetes et des suggestions de renforcement, y compris des options de mise en œuvre avec le contrôle d’admission Kubernetes.

La première phase de ce projet comprend une préversion privée et l’ajout de nouvelles stratégies (désactivées par défaut) à l’initiative ASC_default.

Vous pouvez ignorer ces stratégies en toute sécurité et il n’y aura aucun impact sur votre environnement. Si vous souhaitez les activer, inscrivez-vous à la préversion sur https://aka.ms/SecurityPrP et sélectionnez à partir des options suivantes :

1. **Préversion unique** : pour rejoindre uniquement cette préversion privée. Mentionnez explicitement « Analyse continu ASC » comme préversion que vous souhaitez rejoindre.
1. **Programme en cours** : à ajouter à cette préversion privée et aux prochaines. Vous devrez remplir un profil et un accord de confidentialité.