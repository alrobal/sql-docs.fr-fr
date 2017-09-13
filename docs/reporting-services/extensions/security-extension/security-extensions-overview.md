---
title: "Vue d’ensemble des Extensions de sécurité | Documents Microsoft"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
caps.latest.revision: 22
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: f7e8c95a478e733722d3c80da4b5e12e992ef4da
ms.contentlocale: fr-fr
ms.lasthandoff: 08/12/2017

---
# <a name="security-extensions-overview"></a>Présentation des extensions de sécurité
  Une extension de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permet l'authentification d'utilisateurs ou de groupes ainsi que l'attribution d'autorisations à ces derniers, en permettant à différents utilisateurs de se connecter à un serveur de rapports et d'effectuer différentes tâches ou opérations selon leur identité. Par défaut, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utilise une extension d'authentification Windows, qui utilise des protocoles de compte Windows pour vérifier l'identité des utilisateurs qui prétendent avoir des comptes sur le système. [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utilise un système de sécurité basé sur les rôles pour l'autorisation des utilisateurs. Le modèle de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] basé sur les rôles est identiques aux modèles de sécurité basé sur les rôles d'autres technologies.  
  
 Les extensions de sécurité étant basées sur une API ouverte et extensible, vous pouvez créer des extensions d'authentification et d'autorisation dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]. L'exemple suivant illustre une implémentation d'extension de sécurité type qui utilise une authentification et une autorisation à base de formulaires :  
  
 ![Processus d’extension de sécurité de Services de création de rapports](../../../reporting-services/extensions/security-extension/media/rosettasecurityextensionflow.gif "processus d’extension de sécurité de Reporting Services")  
  
 Comme indiqué dans l'illustration, l'authentification et l'autorisation se déroulent comme suit :  
  
1.  Un utilisateur tente d'accéder au Gestionnaire de rapports à l'aide d'une URL et est redirigé vers un formulaire qui collecte ses informations d'identification pour l'application cliente.  
  
2.  L'utilisateur indique ses informations d'identification sur le formulaire.  
  
3.  Les informations d'identification de l'utilisateur sont transmises au service Web Reporting Services via la méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A>.  
  
4.  Le service Web appelle l'extension de sécurité fournie par le client et vérifie que le nom et le mot de passe de l'utilisateur existent dans l'autorité de sécurité personnalisée.  
  
5.  Après l'authentification, le service Web crée un ticket d'authentification (appelé « cookie »), gère ce dernier et vérifie le rôle de l'utilisateur pour la page d'accueil du Gestionnaire de rapports.  
  
6.  Le service Web retourne le cookie au navigateur et affiche l'interface utilisateur appropriée dans le Gestionnaire de rapports.  
  
7.  Une fois l'utilisateur authentifié, le navigateur envoie des demandes au Gestionnaire de rapports lors de la transmission du cookie dans l'en-tête HTTP. Ces demandes font suite aux actions de l'utilisateur dans l'application du Gestionnaire de rapports.  
  
8.  Le cookie est transmis dans l'en-tête HTTP au service Web avec l'opération d'utilisateur demandée.  
  
9. Le cookie est validé et, s'il est valide, le serveur de rapports retourne le descripteur de sécurité ainsi que d'autres informations sur l'opération demandée, à partir de la base de données du serveur de rapports.  
  
10. Si le cookie est valide, le serveur de rapports effectue un appel vers l'extension de sécurité afin de vérifier si l'utilisateur dispose des autorisations nécessaires pour effectuer l'opération demandée.  
  
11. Si tel est le cas, le serveur de rapports effectue l'opération demandée et retourne le contrôle à l'appelant.  
  
12. Une fois l'utilisateur authentifié, l'accès URL au serveur de rapports utilise le même cookie. Le cookie est transmis dans l'en-tête HTTP.  
  
13. L'utilisateur continue à demander des opérations sur le serveur de rapports jusqu'à la fin de la session.  
  
## <a name="when-to-implement-a-security-extension"></a>Quand implémenter une extension de sécurité  
 Nous vous recommandons d'utiliser l'authentification Windows dans la mesure du possible. Toutefois, une authentification et une autorisation personnalisées pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] peuvent être appropriées dans les deux cas suivants :  
  
-   Vous disposez d'une application Internet ou extranet qui ne peut pas utiliser de comptes Windows.  
  
-   Vous avez des utilisateurs et des rôles personnalisés et devez fournir un schéma d'autorisation correspondant dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’une Extension de sécurité](../../../reporting-services/extensions/security-extension/implementing-a-security-extension.md)   
 [Configurer le Gestionnaire de rapports pour transmettre des Cookies d’authentification personnalisée](https://msdn.microsoft.com/library/ms345241(v=sql.110).aspx)  
  
  