---
title: sysdac_history_internal (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysdac_history_internal
- sysdac_history_internal_TSQL
dev_langs: TSQL
helpviewer_keywords: sysdac_history_internal
ms.assetid: 774a1678-0b27-42be-8adc-a6d7a4a56510
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 55bf1ae9625c5b27c7078bbba61704eef195b0ca
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="data-tier-application-tables---sysdachistoryinternal"></a>Tables d’Application de couche données - sysdac_history_internal
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contient des informations sur les actions entreprises pour gérer les applications de la couche Données (DAC). Cette table est stockée dans le **dbo** schéma de la **msdb** base de données.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**action_id**|**int**|Identificateur de l'action.|  
|**sequence_id**|**int**|Identifie une étape dans une action.|  
|**instance_id**|**uniqueidentifier**|Identificateur de l'instance DAC. Cette colonne peut être jointe sur la **instance_id** colonne [dbo.sysdac_instances &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/data-tier-application-views-dbo-sysdac-instances.md).|  
|**action_type**|**tinyint**|Identificateur du type d'action :<br /><br /> **0** = déployer<br /><br /> **1** = créer<br /><br /> **2** = renommer<br /><br /> **3** = détachement<br /><br /> **4** = suppression|  
|**action_type_name**|**varchar (19)**|Nom du type d'action :<br /><br /> **déployer**<br /><br /> **créer**<br /><br /> **changement de nom**<br /><br /> **détacher**<br /><br /> **supprimer**|  
|**dac_object_type**|**tinyint**|Identificateur du type d'objet affecté par l'action :<br /><br /> **0** = dacpac<br /><br /> **1** = connexion<br /><br /> **2** = base de données|  
|**dac_object_type_name**|**varchar(8)**|Nom du type d'objet affecté par l'action :<br /><br /> **dacpac** = instance DAC<br /><br /> **connexion**<br /><br /> **database**|  
|**action_status**|**tinyint**|Code qui identifie l'état actuel de l'action :<br /><br /> **0** = en attente<br /><br /> **1** = succès<br /><br /> **2** = Échec|  
|**action_status_name**|**varchar(11)**|État actuel de l'action :<br /><br /> **en attente**<br /><br /> **opération réussie**<br /><br /> **Échec**|  
|**Obligatoire**|**bit**|Utilisé par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] lors de la restauration d’une opération DAC.|  
|**dac_object_name_pretran**|**sysname**|Nom de l'objet avant la validation de la transaction qui contient l'action. Utilisé uniquement pour les bases de données et les connexions.|  
|**dac_object_name_posttran**|**sysname**|Nom de l'objet après la validation de la transaction qui contient l'action. Utilisé uniquement pour les bases de données et les connexions.|  
|**sqlScript**|**nvarchar(max)**|Script [!INCLUDE[tsql](../../includes/tsql-md.md)] qui implémente une action sur une base de données ou connexion.|  
|**charge utile**|**varbinary(max)**|Définition de package DAC enregistrée dans une chaîne encodée au format binaire.|  
|**Commentaires**|**varchar(max)**|Enregistre la connexion d'un utilisateur qui a accepté la perte de données potentielle dans une mise à niveau DAC.|  
|**chaîne_erreur**|**nvarchar(max)**|Message d'erreur généré si une erreur se produit lors de l'action.|  
|**created_by**|**sysname**|Connexion à l'origine de l'action qui a créé cette entrée.|  
|**date_de_création**|**datetime**|Date et heure de création de cette entrée.|  
|**date_de_modification**|**datetime**|Date et heure de la dernière modification apportée à l'entrée.|  
  
## <a name="remarks"></a>Notes  
 Les actions de gestion de la DAC, telles que le déploiement ou la suppression d'une DAC, génèrent plusieurs étapes. Un identificateur d'action est attribué à chaque action. Chaque étape est affectée à un numéro de séquence et une ligne dans **sysdac_history_internal**, où l’état de l’étape est enregistré. Chaque ligne est créée lors du démarrage de l'étape de l'action et est mise à jour autant que nécessaire pour refléter l'état de l'opération. Par exemple, une action DAC de déploiement peut être attribuée **action_id** 12 et quatre lignes dans **sysdac_history_internal**:  
  
|||||  
|-|-|-|-|  
|**action_id**|**sequence_id**|**action_type_name**|**dac_object_type_name**|  
|12|0|create|dacpac|  
|12|1|create|login|  
|12|2|create|database|  
|12|3|renommer|database|  
  
 Les opérations DAC, telles que supprimer, ne supprimez pas les lignes à partir de **sysdac_history_internal**. Vous pouvez utiliser la requête suivante pour supprimer manuellement les lignes pour les DAC ne sont plus déployées sur une instance de la [!INCLUDE[ssDE](../../includes/ssde-md.md)]:  
  
```tsql  
DELETE FROM msdb.dbo.sysdac_history_internal  
WHERE instance_id NOT IN  
   (SELECT instance_id  
    FROM msdb.dbo.sysdac_instances_internal);  
```  
  
 La suppression de lignes pour les opérations DAC actives n'a aucune incidence sur les opérations DAC, si ce n'est que vous ne pourrez pas créer de rapport sur l'historique complet de l'opérations DAC.  
  
> [!NOTE]  
>  Actuellement, il n’existe aucun mécanisme pour supprimer **sysdac_history_internal** sur les lignes [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].  
  
## <a name="permissions"></a>Permissions  
 Nécessite l'appartenance au rôle serveur fixe sysadmin. Accès en lecture seule à cette vue est disponible pour tous les utilisateurs disposant d’autorisations pour se connecter à la base de données master.  
  
## <a name="see-also"></a>Voir aussi  
 [Applications de la couche Données](../../relational-databases/data-tier-applications/data-tier-applications.md)   
 [dbo.sysdac_instances &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/data-tier-application-views-dbo-sysdac-instances.md)   
 [sysdac_instances_internal &#40; Transact-SQL &#41;](../../relational-databases/system-tables/data-tier-application-tables-sysdac-instances-internal.md)  
  
  