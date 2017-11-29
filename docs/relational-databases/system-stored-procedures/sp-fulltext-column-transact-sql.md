---
title: sp_fulltext_column (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_fulltext_column_TSQL
- sp_fulltext_column
dev_langs: TSQL
helpviewer_keywords: sp_fulltext_column
ms.assetid: a84cc45d-1b50-44af-85df-2ea033b8a6a9
caps.latest.revision: "36"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 79196daa0031516419418061d2d8d2b179deb2ae
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="spfulltextcolumn-transact-sql"></a>sp_fulltext_column (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-xxx-md.md)]

  Spécifie si une colonne particulière d'une table est utilisée dans l'indexation de texte intégral.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]Utilisez [ALTER FULLTEXT INDEX](../../t-sql/statements/alter-fulltext-index-transact-sql.md) à la place.  
  
||  
|-|  
|**S’applique à**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [version actuelle](http://go.microsoft.com/fwlink/p/?LinkId=299658)), [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].|  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_fulltext_column [ @tabname= ] 'qualified_table_name' ,   
     [ @colname= ] 'column_name' ,   
     [ @action= ] 'action'   
     [ , [ @language= ] 'language_term' ]   
     [ , [ @type_colname= ] 'type_column_name' ]  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@tabname=** ] **'***nom_table_qualifée***'**  
 Nom de table en une ou deux parties. La table doit déjà exister dans la base de données actuelle. La table doit avoir un index de recherche en texte intégral. *nom_table_qualifée* est **nvarchar (517)**, sans valeur par défaut.  
  
 [  **@colname=** ] **'***column_name***'**  
 Est le nom d’une colonne dans *nom_table_qualifée*. La colonne doit être de type caractère, **varbinary (max)** ou **image** colonne et ne peut pas être une colonne calculée. *column_name* est **sysname**, sans valeur par défaut.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]peut créer des index de recherche en texte intégral de données texte stockées dans des colonnes de **varbinary (max)** ou **image** type de données. Les images et les dessins ne sont pas indexés.  
  
 [  **@action=** ] **'***action***'**  
 Action à exécuter. *action* est **varchar (20)**, sans valeur par défaut et peut prendre l’une des valeurs suivantes.  
  
|Valeur| Description|  
|-----------|-----------------|  
|**ajouter**|Ajoute *column_name* de *nom_table_qualifée* à l’index de recherche en texte intégral inactif de la table. Cette action permet d'appliquer à la colonne une indexation de texte intégral.|  
|**DROP**|Supprime *column_name* de *nom_table_qualifée* à partir de l’index de recherche en texte intégral inactif de la table.|  
  
 [  **@language=** ] **'***language_term***'**  
 Langue des données stockées dans la colonne. Pour obtenir la liste des langues incluses dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [sys.fulltext_languages &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql.md).  
  
> [!NOTE]  
>  Utilisez l'analyse indépendante lorsqu'une colonne contient des données dans plusieurs langues ou dans une langue non prise en charge. La langue par défaut est spécifiée par l'option de configuration « Default Full-Text Language ».  
  
 [  **@type_colname =** ] **'***type_column_name***'**  
 Est le nom d’une colonne dans *nom_table_qualifée* qui contient le type de document de *column_name*. Cette colonne doit être **char**, **nchar**, **varchar**, ou **nvarchar**. Il est utilisé uniquement lorsque le type de données de *column_name* est de type **varbinary (max)** ou **image**. *type_column_name* est **sysname**, sans valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
 Aucune  
  
## <a name="remarks"></a>Notes  
 Si l'index de texte intégral est actif, tout remplissage en cours est arrêté. De plus, si le suivi des modifications est activé pour une table détenant un index de texte intégral actif, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] garantit la validité de l'index. Par exemple, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arrête tout remplissage en cours sur la table, supprime l'index existant et démarre un nouveau remplissage.  
  
 Si le suivi des modifications est activé et que des colonnes doivent être ajoutées ou supprimées de l'index de texte intégral tout en préservant l'index, la table doit être désactivée puis les colonnes requises doivent être ajoutées ou supprimées. Ces actions gèlent l'index. La table peut être activée ultérieurement lorsque le démarrage d'un remplissage s'avère pratique.  
  
## <a name="permissions"></a>Permissions  
 Utilisateur doit être un membre de la **db_ddladmin** fixe, un rôle de base de données ou un membre de la **db_owner** fixe, un rôle de base de données ou le propriétaire de la table.  
  
## <a name="examples"></a>Exemples  
 L'exemple ci-dessous illustre l'ajout de la colonne `DocumentSummary` de la table `Document` à l'index de texte intégral de la table.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_fulltext_column 'Production.Document', DocumentSummary, 'add';  
GO  
```  
  
 L'exemple ci-dessous suppose la création préalable d'un index de texte intégral sur la table nommée `spanishTbl`. Pour ajouter la colonne `spanishCol` à l'index de texte intégral, exécutez la procédure stockée suivante :  
  
```  
EXEC sp_fulltext_column 'spanishTbl', 'spanishCol', 'add', 0xC0A;  
GO  
```  
  
 Lorsque vous exécutez cette requête :  
  
```  
SELECT *   
FROM spanishTbl   
WHERE CONTAINS(spanishCol, 'formsof(inflectional, trabajar)')  
```  
  
 Le jeu de résultats comprend des lignes avec différentes formes de `trabajar` (travailler), telles que `trabajo`, `trabajamos` et `trabajan`.  
  
> [!NOTE]  
>  Toutes les colonnes répertoriées dans une même clause de fonction de requête de texte intégral doivent utiliser la même langue.  
  
## <a name="see-also"></a>Voir aussi  
 [OBJECTPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/objectproperty-transact-sql.md)   
 [sp_help_fulltext_columns &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-columns-transact-sql.md)   
 [sp_help_fulltext_columns_cursor &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-columns-cursor-transact-sql.md)   
 [sp_help_fulltext_tables &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-tables-transact-sql.md)   
 [sp_help_fulltext_tables_cursor &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-tables-cursor-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Recherche en texte intégral et la recherche sémantique stockées procédures &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/full-text-search-and-semantic-search-stored-procedures-transact-sql.md)  
  
  