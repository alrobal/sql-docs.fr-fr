---
title: "Tâche Exécuter le travail de SQL Server Agent (Plan de maintenance) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
caps.latest.revision: 21
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 39bb4179c7869d9a9fe0cbbb26263f9e3a91f1ec
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a>Tâche Exécuter le travail de SQL Server Agent (Plan de maintenance)
  La boîte de dialogue **Tâche Exécuter le travail de SQL Server Agent** vous permet d’exécuter les travaux de Microsoft SQL Server Agent dans le cadre d’un plan de maintenance. Cette option n'est pas disponible si vous ne possédez pas de travaux de l'Agent SQL Server sur la connexion sélectionnée.  
  
 Cette tâche utilise l’instruction **.sp_start_job** .  
  
## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur  
 **Connexion**  
 Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.  
  
 **Nouveau**  
 Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche. La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.  
  
 **Travaux d'Agent SQL disponibles**  
 Permet de sélectionner le travail à exécuter. La grille fournit le **Nom du travail** et la **Description** permettant d'identifier les travaux.  
  
 **Vue T-SQL**  
 Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.  
  
> [!NOTE]  
>  Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.  
  
## <a name="new-connection-dialog-box"></a>Boîte de dialogue Nouvelle connexion  
 **Nom de la connexion**  
 Entrez un nom pour la nouvelle connexion.  
  
 **Sélectionnez ou entrez un nom de serveur.**  
 Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.  
  
 **Actualiser**  
 Actualise la liste des serveurs disponibles.  
  
 **Entrez des informations pour vous connecter au serveur**  
 Spécifiez le mode d'authentification sur le serveur.  
  
 **Utiliser la sécurité intégrée à Windows NT**  
 Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.  
  
 **Utiliser un nom d'utilisateur et un mot de passe spécifiques**  
 Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] à l’aide de l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Cette option n'est pas disponible.  
  
 **Nom d'utilisateur**  
 Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification. Cette option n'est pas disponible.  
  
 **Mot de passe**  
 Fournit un mot de passe à utiliser pour l'authentification. Cette option n'est pas disponible.  
  
## <a name="see-also"></a>Voir aussi  
 [sp_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-job-transact-sql.md)   
 [Créer un travail](http://msdn.microsoft.com/library/b35af2b6-6594-40d1-9861-4d5dd906048c)   
 [sp_start_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-start-job-transact-sql.md)  
  
  