---
title: 'Tutoriel : Intégration de l’authentification unique Azure Active Directory à Splan Visitor | Microsoft Docs'
description: Découvrez comment configurer l’authentification unique entre Azure Active Directory et Splan Visitor.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: CelesteDG
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 12/14/2020
ms.author: jeedes
ms.openlocfilehash: df26e7041231b5fa9ae3c0ad9d960ae237ff036b
ms.sourcegitcommit: d79513b2589a62c52bddd9c7bd0b4d6498805dbe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97675638"
---
# <a name="tutorial-azure-active-directory-single-sign-on-sso-integration-with-splan-visitor"></a>Tutoriel : Intégration de l’authentification unique Azure Active Directory à Splan Visitor

Ce tutoriel explique comment intégrer Splan Visitor avec Azure Active Directory (Azure AD). Quand vous intégrez Splan Visitor à Azure AD, vous pouvez :

* Contrôler dans Azure AD qui a accès à Splan Visitor.
* Permettre à vos utilisateurs de se connecter automatiquement à Splan Visitor avec leur compte Azure AD.
* Gérer vos comptes à un emplacement central : le Portail Azure.

## <a name="prerequisites"></a>Prérequis

Pour commencer, vous devez disposer de ce qui suit :

* Un abonnement Azure AD Si vous ne disposez d’aucun abonnement, vous pouvez obtenir [un compte gratuit](https://azure.microsoft.com/free/).
* Un abonnement Splan Visitor pour lequel l’authentification unique est activée

## <a name="scenario-description"></a>Description du scénario

Dans ce tutoriel, vous allez configurer et tester l’authentification unique Azure AD dans un environnement de test.

* Splan Visitor prend en charge l’authentification unique lancée par le **fournisseur d’identité**

## <a name="adding-splan-visitor-from-the-gallery"></a>Ajout de Splan Visitor à partir de la galerie

Pour configurer l’intégration de Splan Visitor à Azure AD, vous devez ajouter Splan Visitor, disponible dans la galerie, à votre liste d’applications SaaS managées.

1. Connectez-vous au portail Azure avec un compte professionnel ou scolaire ou avec un compte personnel Microsoft.
1. Dans le panneau de navigation gauche, sélectionnez le service **Azure Active Directory**.
1. Accédez à **Applications d’entreprise**, puis sélectionnez **Toutes les applications**.
1. Pour ajouter une nouvelle application, sélectionnez **Nouvelle application**.
1. Dans la section **Ajouter à partir de la galerie**, tapez **Splan Visitor** dans la zone de recherche.
1. Sélectionnez **Splan Visitor** dans le volet de résultats, puis ajoutez l’application. Patientez quelques secondes pendant que l’application est ajoutée à votre locataire.

## <a name="configure-and-test-azure-ad-sso-for-splan-visitor"></a>Configurer et tester l’authentification unique Azure AD pour Splan Visitor

Configurez et testez l’authentification unique Azure AD avec Splan Visitor à l’aide d’un utilisateur de test appelé **B.Simon**. Pour que l’authentification unique fonctionne, vous devez établir un lien entre un utilisateur Azure AD et l’utilisateur associé dans Splan Visitor.

Pour configurer et tester l’authentification unique Azure AD avec Splan Visitor, effectuez les étapes suivantes :

1. **[Configurer l’authentification unique Azure AD](#configure-azure-ad-sso)** pour permettre à vos utilisateurs d’utiliser cette fonctionnalité.
    1. **[Créer un utilisateur de test Azure AD](#create-an-azure-ad-test-user)** pour tester l’authentification unique Azure AD avec B. Simon.
    1. **[Affecter l’utilisateur de test Azure AD](#assign-the-azure-ad-test-user)** pour permettre à B. Simon d’utiliser l’authentification unique Azure AD.
1. **[Configurer l’authentification unique Splan Visitor](#configure-splan-visitor-sso)** pour configurer les paramètres de l’authentification unique côté application.
    1. **[Créer un utilisateur de test Splan Visitor](#create-splan-visitor-test-user)** pour avoir un équivalent de B.Simon dans Splan Visitor lié à la représentation Azure AD associée.
1. **[Tester l’authentification unique](#test-sso)** pour vérifier si la configuration fonctionne.

## <a name="configure-azure-ad-sso"></a>Configurer l’authentification unique Azure AD

Effectuez les étapes suivantes pour activer l’authentification unique Azure AD dans le Portail Azure.

1. Dans le portail Azure, accédez à la page d’intégration de l’application **Splan Visitor**, recherchez la section **Gérer** et sélectionnez **Authentification unique**.
1. Dans la page **Sélectionner une méthode d’authentification unique**, sélectionnez **SAML**.
1. Dans la page **Configurer l’authentification unique avec SAML**, cliquez sur l’icône de modification/stylet de **Configuration SAML de base** pour modifier les paramètres.

   ![Modifier la configuration SAML de base](common/edit-urls.png)

1. Dans la section **Configuration SAML de base**, l’application est préconfigurée et les URL nécessaires sont déjà préremplies avec Azure. L’utilisateur doit enregistrer la configuration en cliquant sur le bouton **Enregistrer**.

1. Dans la page **Configurer l’authentification unique avec SAML**, dans la section **Certificat de signature SAML**, recherchez **XML de métadonnées de fédération** et sélectionnez **Télécharger** pour télécharger le certificat et l’enregistrer sur votre ordinateur.

    ![Lien Téléchargement de certificat](common/metadataxml.png)

1. Dans la section **Configurer Splan Visitor**, copiez la ou les URL appropriées en fonction de vos besoins.

    ![Copier les URL de configuration](common/copy-configuration-urls.png)
### <a name="create-an-azure-ad-test-user"></a>Créer un utilisateur de test Azure AD

Dans cette section, vous allez créer un utilisateur de test appelé B. Simon dans le portail Azure.

1. Dans le volet gauche du Portail Azure, sélectionnez **Azure Active Directory**, **Utilisateurs**, puis **Tous les utilisateurs**.
1. Sélectionnez **Nouvel utilisateur** dans la partie supérieure de l’écran.
1. Dans les propriétés **Utilisateur**, effectuez les étapes suivantes :
   1. Dans le champ **Nom**, entrez `B.Simon`.  
   1. Dans le champ **Nom de l’utilisateur**, entrez username@companydomain.extension. Par exemple : `B.Simon@contoso.com`.
   1. Cochez la case **Afficher le mot de passe**, puis notez la valeur affichée dans le champ **Mot de passe**.
   1. Cliquez sur **Créer**.

### <a name="assign-the-azure-ad-test-user"></a>Affecter l’utilisateur de test Azure AD

Dans cette section, vous allez autoriser B.Simon à utiliser l’authentification unique Azure en lui accordant l’accès à Splan Visitor.

1. Dans le portail Azure, sélectionnez **Applications d’entreprise**, puis **Toutes les applications**.
1. Dans la liste des applications, sélectionnez **Splan Visitor**.
1. Dans la page de vue d’ensemble de l’application, recherchez la section **Gérer** et sélectionnez **Utilisateurs et groupes**.
1. Sélectionnez **Ajouter un utilisateur**, puis **Utilisateurs et groupes** dans la boîte de dialogue **Ajouter une attribution**.
1. Dans la boîte de dialogue **Utilisateurs et groupes**, sélectionnez **B. Simon** dans la liste Utilisateurs, puis cliquez sur le bouton **Sélectionner** au bas de l’écran.
1. Si vous attendez qu’un rôle soit attribué aux utilisateurs, vous pouvez le sélectionner dans la liste déroulante **Sélectionner un rôle** . Si aucun rôle n’a été configuré pour cette application, vous voyez le rôle « Accès par défaut » sélectionné.
1. Dans la boîte de dialogue **Ajouter une attribution**, cliquez sur le bouton **Attribuer**.

## <a name="configure-splan-visitor-sso"></a>Configurer l’authentification unique Splan Visitor

Pour configurer l’authentification unique côté **Splan Visitor**, vous devez envoyer le **XML des métadonnées de fédération** téléchargé et les URL appropriées copiées à partir du portail Azure à l’[équipe du support technique de Splan Visitor](mailto:support@splan.com). Celles-ci configurent ensuite ce paramètre pour que la connexion SSO SAML soit définie correctement des deux côtés.

### <a name="create-splan-visitor-test-user"></a>Créer un utilisateur de test Splan Visitor

Dans cette section, vous allez créer un utilisateur nommé Britta Simon dans Splan Visitor. Collaborez avec l’[équipe du support technique de Splan Visitor](mailto:support@splan.com) pour ajouter les utilisateurs à la plateforme Splan Visitor. Les utilisateurs doivent être créés et activés avant que vous utilisiez l’authentification unique.

## <a name="test-sso"></a>Tester l’authentification unique (SSO) 

Dans cette section, vous allez tester votre configuration de l’authentification unique Azure AD avec les options suivantes.

* Cliquez sur Tester cette application dans le portail Azure ; vous êtes alors connecté automatiquement à l’instance de Splan Visitor pour laquelle vous avez configuré l’authentification unique.

* Vous pouvez utiliser Mes applications de Microsoft. Quand vous cliquez sur la vignette Splan Visitor dans Mes applications, vous devez être connecté automatiquement à l’instance de Splan Visitor pour laquelle vous avez configuré l’authentification unique. Pour plus d’informations sur Mes applications, consultez [Présentation de Mes applications](https://docs.microsoft.com/azure/active-directory/active-directory-saas-access-panel-introduction).


## <a name="next-steps"></a>Étapes suivantes

Après avoir configuré Splan Visitor, vous pouvez appliquer le contrôle de session, qui protège l’exfiltration et l’infiltration des données sensibles de votre organisation en temps réel. Le contrôle de session est étendu à partir de l’accès conditionnel. [Découvrez comment appliquer un contrôle de session avec Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/proxy-deployment-any-app).


