---
title: "Stockage de Gestion basée sur des stratégies | Microsoft Docs"
ms.custom: 
ms.date: 08/09/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
caps.latest.revision: 11
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: e59b30393d9bb917fc48511d7e621c14e9a01c9c
ms.openlocfilehash: fa8ad7ecca05b2fe7b4ef6b955f5b24fadb0e23b
ms.contentlocale: fr-fr
ms.lasthandoff: 08/10/2017

---
# <a name="policy-based-management-storage"></a>Stockage de Gestion basée sur des stratégies
  Les stratégies sont stockées dans la base de données msdb. Après la modification d'une stratégie ou d'une condition, vous devez sauvegarder msdb. Pour plus d’informations, consultez [Sauvegarder et restaurer des bases de données système &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md).  
  
## <a name="storing-policies"></a>Stockage des stratégies  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] est fourni avec des stratégies qui peuvent être utilisées pour contrôler une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Par défaut, ces stratégies ne sont pas installées sur le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; toutefois, elles peuvent être importées à partir de l’emplacement d’installation par défaut C:\Program Files(x86)\Microsoft SQL Server\140\Tools\Policies\DatabaseEngine\1033.  
  
 Vous pouvez créer directement des stratégies à l’aide du menu **Fichier/Nouveau** , puis les enregistrer dans un fichier. Cela vous permet de créer des stratégies quand vous n’êtes pas connecté à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
 L’historique de stratégie pour les stratégies évaluées dans l’instance actuelle du [!INCLUDE[ssDE](../../includes/ssde-md.md)] est conservé dans les tables système msdb. L'historique de stratégie pour les stratégies appliquées à d'autres instances du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou appliquées à [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ou à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] n'est pas conservé.  
  
  