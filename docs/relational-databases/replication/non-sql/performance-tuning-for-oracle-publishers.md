---
title: "Réglage des performances pour les serveurs de publication Oracle | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Oracle publishing [SQL Server replication], performance tuning
ms.assetid: 32c0b4ec-c166-45a3-b41e-38a30fd56813
caps.latest.revision: 34
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 43042f93e80be4f9bf7c5044cc11791c614d85f0
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="performance-tuning-for-oracle-publishers"></a>Réglage des performances pour les serveurs de publication Oracle
  L’architecture de publication Oracle est semblable à celle de [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; c’est pourquoi la première étape de réglage des performances de réplication d’Oracle exige que vous suiviez les recommandations générales de réglage exposées dans la rubrique [Enhance General Replication Performance](../../../relational-databases/replication/administration/enhance-general-replication-performance.md).  
  
 Il existe en outre pour les serveurs de publication Oracle deux options liées aux performances :  
  
-   Spécification des options de publication adéquates : Oracle ou Oracle Gateway.  
  
-   Configuration du travail du jeu de transactions pour traiter les changements sur le serveur de publication selon une périodicité appropriée.  
  
## <a name="specifying-the-appropriate-publishing-option"></a>Spécification de l'option de publication adéquate  
 L'option Oracle Gateway offre de meilleures performances que l'option Oracle Complete ; il n'est cependant pas possible de l'utiliser pour publier la même table dans plusieurs publications transactionnelles. Une table peut faire partie d'un nombre quelconque de publications d'instantané mais d'une seule publication transactionnelle uniquement. Si vous devez publier la même table dans plusieurs publications transactionnelles, choisissez l'option Oracle Complete. Spécifiez cette option pour identifier le serveur de publication Oracle sur le serveur de distribution [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Pour plus d’informations, consultez [Create a Publication from an Oracle Database](../../../relational-databases/replication/publish/create-a-publication-from-an-oracle-database.md).  
  
## <a name="configuring-the-transaction-set-job"></a>Configuration du travail du jeu de transactions  
 Les changements apportés aux tables Oracle publiées sont traités par groupes appelés jeux de transactions. Pour garantir la cohérence des transactions, chaque jeu de transactions est validé comme une unique transaction au niveau de la base de données de distribution. Si le jeu de transactions devient trop volumineux, il ne peut pas être correctement traité comme une unique transaction.  
  
 Par défaut, les jeux de transactions ne sont créés que par l'Agent de lecture du journal. Si, en période de forte activité de changement, l'Agent de lecture du journal ne s'exécute pas ou ne parvient pas à se connecter à partir du serveur de distribution [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur le serveur de publication Oracle, les jeux de transactions risquent de devenir trop volumineux pour être gérés. Pour prévenir ce problème, assurez-vous que des jeux de transactions sont régulièrement créés même si l'Agent de lecture du journal ne s'exécute pas ou ne parvient pas à se connecter au serveur de publication Oracle.  
  
 Les jeux de transactions peuvent se créer à l'aide de la tâche Xactset (tâche de base de données Oracle installée par la réplication), qui a recours au même mécanisme que l'Agent de lecture de journal pour créer ces jeux. Chaque fois que cette tâche s'exécute, elle crée un nouveau jeu de transactions. Lors de sa prochaine exécution, l'Agent de lecture de journal traitera tous les jeux qui ont été créés. S'il demeure des changements en attente après que tous les jeux de transactions ont été traités, l'Agent de lecture du journal crée et traite un ou plusieurs jeux de transactions supplémentaires.  
  
 Pour configurer le travail du jeu de transactions, consultez [Configurer le travail d’un jeu de transactions pour un serveur de publication Oracle &#40;programmation Transact-SQL de la réplication&#41;](../../../relational-databases/replication/administration/configure-the-transaction-set-job-for-an-oracle-publisher.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Configurer un serveur de publication Oracle](../../../relational-databases/replication/non-sql/configure-an-oracle-publisher.md)   
 [Oracle Publishing Overview](../../../relational-databases/replication/non-sql/oracle-publishing-overview.md)  
  
  