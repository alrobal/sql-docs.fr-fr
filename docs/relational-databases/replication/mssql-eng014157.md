---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 43d1554f54c46787bfff9dd4bd7c34d5d0410ba1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="mssqleng014157"></a>MSSQL_ENG014157
    
## <a name="message-details"></a>Détails du message  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|14157|  
|Source de l'événement|MSSQLSERVER|  
|Composant|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nom symbolique||  
|Texte du message|L'abonnement créé par l'Abonné '%s' à la publication '%s' a expiré et a été supprimé.|  
  
## <a name="explanation"></a>Explication  
 Un Abonné doit effectuer une synchronisation avec le serveur de publication dans les délais définis par la période de rétention de la publication. Si un Abonné n'effectue pas la synchronisation dans cette période, l'abonnement expire. Pour plus d’informations, voir [Subscription Expiration and Deactivation](../../relational-databases/replication/subscription-expiration-and-deactivation.md).  
  
## <a name="user-action"></a>Action de l'utilisateur  
 L'abonnement doit être recréé et initialisé avant que l'Abonné ne recommence à recevoir des modifications de données :  
  
-   Pour plus d’informations sur la création d’abonnements, consultez [S’abonner à des publications](../../relational-databases/replication/subscribe-to-publications.md).  
  
-   Pour plus d’informations sur l’initialisation des abonnements, consultez [Initialiser un abonnement](../../relational-databases/replication/initialize-a-subscription.md).  
  
 Si la base de données d'abonnement contient des modifications qui n'ont pas été synchronisées avec le serveur de publication, vous pouvez utiliser l' [tablediff Utility](../../tools/tablediff-utility.md) pour identifier les lignes qui sont différentes dans les bases de publication et les bases d'abonnement.  
  
 Vous pouvez augmenter la période de rétention de la publication afin d'empêcher l'expiration des abonnements. Faites preuve de la plus grande vigilance lors de la définition d'une valeur élevée car plus le nombre de données et de métadonnées stockées est important, moins les performances sont bonnes. Pour plus d’informations, consultez [Subscription Expiration and Deactivation](../../relational-databases/replication/subscription-expiration-and-deactivation.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Guide de référence des erreurs et des événements &#40;réplication&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  