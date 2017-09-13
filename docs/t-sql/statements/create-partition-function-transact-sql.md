---
title: "CRÉER la fonction de PARTITION (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CREATE PARTITION FUNCTION
- PARTITION
- PARTITION FUNCTION
- PARTITION_FUNCTION_TSQL
- PARTITION_TSQL
- CREATE_PARTITION_FUNCTION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- RANGE RIGHT partition functions
- RANGE LEFT partition functions
- partitioned indexes [SQL Server], functions
- functions [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], functions
- CREATE PARTITION FUNCTION statement
ms.assetid: 9dfe8b76-721e-42fd-81ae-14e22258c4f2
caps.latest.revision: 57
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a08cf71066a3713d2eb96ff11bafd951795819ff
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="create-partition-function-transact-sql"></a>CREATE PARTITION FUNCTION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Crée une fonction, dans la base de données active, qui mappe les lignes d'une table ou d'un index avec des partitions à partir des valeurs d'une colonne spécifiée. L'utilisation de CREATE PARTITION FUNCTION est la première étape de la création d'une table ou d'un index partitionné. Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], une table ou un index peut comprendre au maximum 15 000 partitions.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CREATE PARTITION FUNCTION partition_function_name ( input_parameter_type )  
AS RANGE [ LEFT | RIGHT ]   
FOR VALUES ( [ boundary_value [ ,...n ] ] )   
[ ; ]  
```  
  
## <a name="arguments"></a>Arguments  
 *partition_function_name*  
 Nom de la fonction de partition. Les noms de fonctions de partition doivent être uniques au sein de la base de données et respecter les règles pour [identificateurs](../../relational-databases/databases/database-identifiers.md).  
  
 *input_parameter_type*  
 Type de données de la colonne utilisée pour le partitionnement. Tous les types de données sont utilisables comme colonnes de partitionnement, à l’exception de **text**, **ntext**, **image**, **xml**, **timestamp**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, des types de données d’alias ou des types de données CLR définis par l’utilisateur.  
  
 La colonne effectivement utilisée, appelée « colonne de partitionnement », est spécifiée dans l'instruction CREATE TABLE ou CREATE INDEX.  
  
 *boundary_value*  
 Spécifie les valeurs limites pour chaque partition d’une table ou index partitionné qui utilise *partition_function_name*. Si *boundary_value* est vide, la fonction de partition mappe la totalité de la table ou à l’aide de l’index *partition_function_name* en une seule partition. Une seule colonne de partitionnement, spécifiée dans une instruction CREATE TABLE ou CREATE INDEX, peut être utilisée.  
  
 *boundary_value* est une expression constante qui permettre référencer des variables. Il peut s'agir de variables de type définies par l'utilisateur, de fonctions et de fonctions définies par l'utilisateur. Elle ne peut pas référencer des expressions [!INCLUDE[tsql](../../includes/tsql-md.md)]. *boundary_value* doit correspondre ou être implicitement convertible au type de données fourni dans *input_parameter_type*et ne peut pas être tronquée pendant une conversion implicite d’une manière que la taille et l’échelle de la valeur ne correspond pas à celles de son *input_parameter_type*.  
  
> [!NOTE]  
>  Si *boundary_value* se compose de **datetime** ou **smalldatetime** littéraux, ces littéraux sont évalués en supposant que l’anglais est la langue de session. Ce comportement est déconseillé. Pour vous assurer que la définition de la fonction de partition fonctionne comme prévu pour toutes les langues de session, nous vous recommandons d'utiliser des constantes qui sont interprétées de la même manière quels que soient vos paramètres linguistiques, comme le format aaaammjj, ou bien de convertir explicitement les littéraux dans un style spécifique. Pour déterminer la langue de session de votre serveur, exécutez `SELECT @@LANGUAGE`.  
  
 *.. .n*  
 Spécifie le nombre de valeurs fournies par *boundary_value*, pour ne pas dépasser 14,999. Le nombre de partitions créées est égal à  *n*  + 1. Il n'est pas nécessaire que les valeurs soient recensées dans l'ordre. Si les valeurs ne sont pas dans l'ordre, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] les trie, crée la fonction et affiche un message d'avertissement indiquant qu'elles ne sont pas fournies dans l'ordre. Le moteur de base de données renvoie une erreur si  *n*  comprend des valeurs dupliquées.  
  
 **GAUCHE** | OUI  
 Spécifie à quel côté de chaque intervalle de valeur limite, gauche ou à droite, la *boundary_value* [ **,***.. .n* ] appartient, lorsque les valeurs d’intervalle sont triés par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans l’ordre croissant de gauche à droite. Si cet argument n'est pas spécifié, la valeur par défaut est LEFT.  
  
## <a name="remarks"></a>Notes  
 L'étendue d'une fonction de partition est limitée à la base de données dans laquelle elle est créée. Dans la base de données, les fonctions de partition résident dans un espace de noms distinct des autres fonctions.  
  
 Toutes les lignes dont la colonne de partitionnement possède des valeurs NULL sont placées dans la partition située le plus à gauche, sauf si NULL est spécifié comme valeur limite et que RIGHT est indiqué. Dans ce cas, la partition située le plus à gauche est une partition vide et les valeurs NULL sont placées dans la partition suivante.  
  
## <a name="permissions"></a>Permissions  
 N'importe laquelle des autorisations suivantes permet d'exécuter CREATE PARTITION FUNCTION :  
  
-   Autorisation ALTER ANY DATASPACE. Cette autorisation est attribuée par défaut aux membres du rôle de serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_ddladmin** .  
  
-   Autorisation CONTROL ou ALTER sur la base de données dans laquelle la fonction de partition est créée.  
  
-   Autorisation CONTROL SERVER ou ALTER ANY DATABASE sur le serveur de la base de données dans laquelle la fonction de partition est créée.  
  
##  <a name="BKMK_examples"></a> Exemples  
  
### <a name="a-creating-a-range-left-partition-function-on-an-int-column"></a>A. Création d'une fonction de partition RANGE LEFT sur une colonne de type int  
 La fonction de partition suivante partitionne une table ou un index en quatre partitions.  
  
```tsql  
CREATE PARTITION FUNCTION myRangePF1 (int)  
AS RANGE LEFT FOR VALUES (1, 100, 1000);  
```  
  
 Le tableau suivant illustre une table qui utilise cette fonction de partition sur la colonne de partitionnement **col1** serait partitionnée.  
  
|Partition|1|2|3|4|  
|---------------|-------|-------|-------|-------|  
|**Valeurs**|**Col1** <= `1`|**col1**  >  `1` AND **col1** <= `100`|**col1**  >  `100` AND **col1** <=`1000`|**Col1** > `1000`|  
  
### <a name="b-creating-a-range-right-partition-function-on-an-int-column"></a>B. Création d'une fonction de partition RANGE RIGHT sur une colonne de type int  
 La fonction de partition suivante utilise les mêmes valeurs pour *boundary_value* [ **,***.. .n* ] en tant que l’exemple précédent, mais elle spécifie RANGE RIGHT.  
  
```tsql  
CREATE PARTITION FUNCTION myRangePF2 (int)  
AS RANGE RIGHT FOR VALUES (1, 100, 1000);  
```  
  
 Le tableau suivant illustre une table qui utilise cette fonction de partition sur la colonne de partitionnement **col1** serait partitionnée.  
  
|Partition|1|2|3|4|  
|---------------|-------|-------|-------|-------|  
|**Valeurs**|**col1** \<`1`|**col1**  >=  `1` AND **col1** \<`100`|**col1**  >=  `100` AND **col1** \<`1000`|**Col1** >= `1000`| 
  
### <a name="c-creating-a-range-right-partition-function-on-a-datetime-column"></a>C. Création d'une fonction de partition RANGE RIGHT sur une colonne de type datetime  
 La fonction de partition suivante partitionne une table ou un index en 12 partitions, une pour chaque mois d’une année de valeurs dans un **datetime** colonne.  
  
```tsql  
CREATE PARTITION FUNCTION [myDateRangePF1] (datetime)  
AS RANGE RIGHT FOR VALUES ('20030201', '20030301', '20030401',  
               '20030501', '20030601', '20030701', '20030801',   
               '20030901', '20031001', '20031101', '20031201');  
```  
  
 Le tableau suivant illustre une table ou un index qui utilise cette fonction de partition sur la colonne de partitionnement **datecol** serait partitionnée.  
  
|Partition|1|2|...|11|12|  
|---------------|-------|-------|---------|--------|--------|  
|**Valeurs**|**datecol** \<`February 1, 2003`|**datecol**  >=  `February 1, 2003` AND **datecol** \<`March 1, 2003`||**datecol**  >=  `November 1, 2003` AND **col1** \<`December 1, 2003`|**datecol** >= `December 1, 2003`| 
  
### <a name="d-creating-a-partition-function-on-a-char-column"></a>D. Création d'une fonction de partition sur une colonne de type char  
 La fonction de partition suivante partitionne une table ou un index en quatre partitions.  
  
```tsql  
CREATE PARTITION FUNCTION myRangePF3 (char(20))  
AS RANGE RIGHT FOR VALUES ('EX', 'RXE', 'XR');  
```  
  
 Le tableau suivant illustre une table qui utilise cette fonction de partition sur la colonne de partitionnement **col1** serait partitionnée.  
  
|Partition|1|2|3|4|  
|---------------|-------|-------|-------|-------|  
|**Valeurs**|**col1** \< `EX`...|**col1**  >=  `EX` AND **col1** \< `RXE`...|**col1**  >=  `RXE` AND **col1** \< `XR`...|**Col1** >= `XR`| 
  
### <a name="e-creating-15000-partitions"></a>E. Création de 15 000 partitions  
 La fonction de partition suivante partitionne une table ou un index en 15 000 partitions.  
  
```tsql  
--Create integer partition function for 15,000 partitions.  
DECLARE @IntegerPartitionFunction nvarchar(max) = 
    N'CREATE PARTITION FUNCTION IntegerPartitionFunction (int) 
    AS RANGE RIGHT FOR VALUES (';  
DECLARE @i int = 1;  
WHILE @i < 14999  
BEGIN  
SET @IntegerPartitionFunction += CAST(@i as nvarchar(10)) + N', ';  
SET @i += 1;  
END  
SET @IntegerPartitionFunction += CAST(@i as nvarchar(10)) + N');';  
EXEC sp_executesql @IntegerPartitionFunction;  
GO  
```  
  
### <a name="f-creating-partitions-for-multiple-years"></a>F. Création de partitions pour plusieurs années  
 La fonction de partition suivante partitionne une table ou un index en 50 partitions sur un **datetime2** colonne. Il y a une partition pour chaque mois entre janvier 2007 et janvier 2011.  
  
```tsql  
--Create date partition function with increment by month.  
DECLARE @DatePartitionFunction nvarchar(max) = 
    N'CREATE PARTITION FUNCTION DatePartitionFunction (datetime2) 
    AS RANGE RIGHT FOR VALUES (';  
DECLARE @i datetime2 = '20070101';  
WHILE @i < '20110101'  
BEGIN  
SET @DatePartitionFunction += '''' + CAST(@i as nvarchar(10)) + '''' + N', ';  
SET @i = DATEADD(MM, 1, @i);  
END  
SET @DatePartitionFunction += '''' + CAST(@i as nvarchar(10))+ '''' + N');';  
EXEC sp_executesql @DatePartitionFunction;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tables et index partitionnés](../../relational-databases/partitions/partitioned-tables-and-indexes.md)   
 [$PARTITION &#40; Transact-SQL &#41;](../../t-sql/functions/partition-transact-sql.md)   
 [ALTER PARTITION FUNCTION &#40; Transact-SQL &#41;](../../t-sql/statements/alter-partition-function-transact-sql.md)   
 [DROP PARTITION FUNCTION &#40; Transact-SQL &#41;](../../t-sql/statements/drop-partition-function-transact-sql.md)   
 [CREATE PARTITION SCHEME &#40;Transact-SQL&#41;](../../t-sql/statements/create-partition-scheme-transact-sql.md)   
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)   
 [ALTER INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-index-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [Sys.partition_functions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partition-functions-transact-sql.md)   
 [Sys.partition_parameters &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partition-parameters-transact-sql.md)   
 [Sys.partition_range_values &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)   
 [Sys.partitions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-partitions-transact-sql.md)   
 [sys.tables &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-tables-transact-sql.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [sys.index_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-index-columns-transact-sql.md)  
  
  

