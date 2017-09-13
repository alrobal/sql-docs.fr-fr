---
title: "Renommer des fonctions définies par l’utilisateur | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-udf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
caps.latest.revision: 7
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 6af95b4d0b4bc3b8e652fd40fa1427cd156c1514
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="rename-user-defined-functions"></a>Renommer des fonctions définies par l'utilisateur
  Vous pouvez renommer les fonctions définies par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
     [Limitations et restrictions](#Restrictions)  
  
     [Sécurité](#Security)  
  
-   **Pour renommer des fonctions définies par l'utilisateur, utilisez :**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Avant de commencer  
  
###  <a name="Restrictions"></a> Limitations et restrictions  
  
-   Les noms de fonction doivent respecter les règles applicables aux [identificateurs](../../relational-databases/databases/database-identifiers.md).  
  
-   Le fait de renommer une fonction définie par l’utilisateur ne modifie pas le nom de l’objet correspondant dans la colonne de définition de l’affichage catalogue **sys.sql_modules** . Par conséquent, nous vous recommandons de ne pas renommer ce type d'objet. À la place, supprimez, puis recréez la procédure stockée avec son nouveau nom.  
  
-   La modification du nom ou de la définition d'une fonction définie par l'utilisateur peut entraîner l'échec de ses objets dépendants si ceux-ci n'ont pas été mis à jour pour refléter les modifications apportées à la fonction.  
  
###  <a name="Security"></a> Sécurité  
  
####  <a name="Permissions"></a> Autorisations  
 Pour supprimer la fonction, un utilisateur doit disposer de l'autorisation ALTER sur le schéma auquel la fonction appartient ou de l'autorisation CONTROL sur la fonction. Pour recréer la fonction, un utilisateur doit disposer de l'autorisation CREATE FUNCTION dans la base de données et de l'autorisation ALTER sur le schéma dans lequel la fonction est en cours de création.  
  
##  <a name="SSMSProcedure"></a> Utilisation de SQL Server Management Studio  
  
#### <a name="to-rename-user-defined-functions"></a>Pour renommer des fonctions définies par l'utilisateur  
  
1.  Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) en regard de la base de données qui contient la fonction que souhaitez renommer, puis  
  
2.  Cliquez sur le signe plus (+) en regard du dossier **Programmabilité** .  
  
3.  Cliquez sur le signe plus (+) en regard du dossier qui contient la fonction à renommer :  
  
    -   Fonction table  
  
    -   Fonction scalaire  
  
    -   Fonction d'agrégation  
  
4.  Cliquez avec le bouton droit sur la fonction que vous voulez renommer et sélectionnez **Renommer**.  
  
5.  Entrez le nouveau nom de la fonction.  
  
##  <a name="TsqlProcedure"></a> Utilisation de Transact-SQL  
 **Pour renommer des fonctions définies par l'utilisateur**  
  
 Cette tâche ne peut pas être effectuée à l'aide d'instructions Transact-SQL. Pour renommer une fonction définie par l'utilisateur à l'aide de Transact-SQL, vous devez d'abord supprimer la fonction existante puis la recréer sous son nouveau nom. Vérifiez que l'ensemble du code et des applications qui utilisaient l'ancien nom de la fonction utilisent désormais le nouveau nom.  
  
 Pour plus d’informations, consultez [CREATE VIEW &#40;Transact-SQL&#41;](../../t-sql/statements/create-function-transact-sql.md) et [DROP VIEW &#40;Transact-SQL&#41;](../../t-sql/statements/drop-function-transact-sql.md).  
  
## <a name="see-also"></a>Voir aussi  
 [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md)   
 [Afficher les fonctions définies par l'utilisateur](../../relational-databases/user-defined-functions/view-user-defined-functions.md)  
  
  