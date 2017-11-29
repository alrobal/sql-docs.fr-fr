---
title: Sys.dm_db_stats_properties (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/05/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_db_stats_properties_TSQL
- sys.dm_db_stats_properties
- dm_db_stats_properties_TSQL
- dm_db_stats_properties
dev_langs: TSQL
helpviewer_keywords: sys.dm_db_stats_properties
ms.assetid: 8a54889d-e263-4881-9fcb-b1db410a9453
caps.latest.revision: "13"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: e2a1ebc3301372b490de9ec631c3cdb0743f264b
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmdbstatsproperties-transact-sql"></a>sys.dm_db_stats_properties (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne les propriétés de statistiques de l'objet de base de données spécifié (table ou vue indexée) dans la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] active. Pour les tables partitionnées, consultez similaire [sys.dm_db_incremental_stats_properties](../../relational-databases/system-dynamic-management-views/sys-dm-db-incremental-stats-properties-transact-sql.md). 
 
## <a name="syntax"></a>Syntaxe  
  
```  
sys.dm_db_stats_properties (object_id, stats_id)  
```  
  
## <a name="arguments"></a>Arguments  
 *object_id*  
 ID de l'objet dans la base de données active dont les propriétés d'une de ses statistiques sont demandées. *l’object_id* est **int**.  
  
 *stats_id*  
 ID des statistiques pour *l’object_id*. spécifié. L’ID des statistiques peut être obtenu à partir de la vue de gestion dynamique [sys.stats](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md) . *stats_id* correspond à **int**.  
  
## <a name="table-returned"></a>Table retournée  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|object_id|**int**|ID de l'objet (table ou vue indexée) pour lequel retourner les propriétés de l'objet de statistiques.|  
|stats_id|**int**|ID de l'objet de statistiques. Unique dans la table ou la vue indexée. Pour plus d’informations, consultez [sys.stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md).|  
|last_updated|**datetime2**|Date et heure de la dernière mise à jour de l'objet de statistiques.|  
|lignes|**bigint**|Nombre total de lignes dans la table ou la vue indexée au moment de la dernière mise à jour des statistiques. Si les statistiques sont filtrées ou correspondent à un index filtré, le nombre de lignes peut être inférieur à celui de la table.|  
|rows_sampled|**bigint**|Nombre total de lignes échantillonnées pour le calcul des statistiques.|  
|étapes|**int**|Nombre d'étapes dans l'histogramme. Pour plus d’informations, consultez [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md).|  
|unfiltered_rows|**bigint**|Nombre total de lignes dans la table avant l'application de l'expression de filtre (pour les statistiques filtrées). Si les statistiques ne sont pas filtrées, unfiltered_rows est égal à la valeur retournée dans la colonne rows.|  
|modification_counter|**bigint**|Nombre total de modifications de la première colonne de statistiques (la colonne sur laquelle l'histogramme est construit) depuis la dernière mise à jour des statistiques.<br /><br /> Tables optimisées en mémoire : démarrage [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] et dans [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] cette colonne contient : nombre total de modifications pour la table étant donné que les statistiques de dernière mise à jour ou de la base de données a été redémarré.|  
|persisted_sample_percent|**float**|Persistante pourcentage d’échantillonnage destinée mises à jour des statistiques qui ne spécifient pas explicitement un pourcentage d’échantillonnage. Si la valeur est zéro, aucun pourcentage exemple persistante n’est définie pour cette statistique.<br /><br /> **S’applique à :** [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] SP1 CU4|  
  
## <a name="remarks"></a>Notes  
 **Sys.dm_db_stats_properties** renvoie un ensemble de lignes vide si l’une des conditions suivantes :  
  
-   **object_id** ou **stats_id** a la valeur NULL.  
  
-   L'objet spécifié est introuvable ou ne correspond à aucune table ou vue indexée.  
  
-   L'ID de statistiques spécifié ne correspond pas à des statistiques existantes pour l'ID d'objet spécifié.  
  
-   L'utilisateur actuel n'est pas autorisé à afficher l'objet de statistiques.  
  
 Ce comportement permet à l’utilisation sécurisée de **sys.dm_db_stats_properties** lorsque croisée appliqué aux lignes dans les vues comme **sys.objects** et **sys.stats**.  
  
## <a name="permissions"></a>Permissions  
 L'utilisateur doit avoir sélectionné des autorisations sur les colonnes de statistiques, ou bien il doit être le propriétaire de la table, ou encore il doit être membre du rôle serveur fixe `sysadmin`, du rôle de base de données fixe `db_owner` ou du rôle de base de données fixe `db_ddladmin`.  
  
## <a name="examples"></a>Exemples  

### <a name="a-simple-example"></a>A. Exemple simple
L’exemple suivant retourne les statistiques pour le `Person.Person` table dans la base de données AdventureWorks.

```
SELECT * FROM sys.dm_db_stats_properties (object_id('Person.Person'), 1);
``` 
  
### <a name="b-returning-all-statistics-properties-for-a-table"></a>B. Renvoi de toutes les propriétés de statistiques pour une table  
 L'exemple suivant retourne les propriétés de toutes les statistiques existantes pour la table TEST.  
  
```  
SELECT sp.stats_id, name, filter_definition, last_updated, rows, rows_sampled, steps, unfiltered_rows, modification_counter   
FROM sys.stats AS stat   
CROSS APPLY sys.dm_db_stats_properties(stat.object_id, stat.stats_id) AS sp  
WHERE stat.object_id = object_id('TEST');  
```  
  
### <a name="c-returning-statistics-properties-for-frequently-modified-objects"></a>C. Renvoi de toutes les propriétés de statistiques pour les objets modifiés fréquemment  
 L'exemple suivant retourne toutes les tables, les vues indexées et les statistiques de la base de données active, dans lesquelles la première colonne a été modifiée plus de 1000 fois depuis la dernière mise à jour des statistiques.  
  
```  
SELECT obj.name, obj.object_id, stat.name, stat.stats_id, last_updated, modification_counter  
FROM sys.objects AS obj   
INNER JOIN sys.stats AS stat ON stat.object_id = obj.object_id  
CROSS APPLY sys.dm_db_stats_properties(stat.object_id, stat.stats_id) AS sp  
WHERE modification_counter > 1000;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md)   
 [sys.stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)   
 [Fonctions et vues de gestion dynamique relatives à l’objet &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/object-related-dynamic-management-views-and-functions-transact-sql.md)   
 [Fonctions et vues de gestion dynamique &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
 [Sys.dm_db_incremental_stats_properties (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-incremental-stats-properties-transact-sql.md)  
 [Sys.dm_db_stats_histogram (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-histogram-transact-sql.md) 
  
