---
title: "Exécuter la tâche de travail de l’Agent SQL Server | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.executesqlserveragentjobtask.f1
helpviewer_keywords:
- Execute SQL Server Agent Job task [Integration Services]
- jobs [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 3aa3bc0e-1a1c-452e-81b8-b4e3422ea053
caps.latest.revision: 44
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: c3e47e4a5ae297202ba43679fba393421880a7ea
ms.openlocfilehash: 65caffce1a119757743f8f2d6bf708112492e767
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="execute-sql-server-agent-job-task"></a>Tâche Exécuter le travail de l'Agent SQL Server
  La tâche Exécuter le travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécute des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent est un service Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] qui exécute des travaux définis dans une instance de SQL Server. Vous pouvez créer des travaux qui exécutent des instructions Transact-SQL et des scripts ActiveX, réalisent des tâches de maintenance des services [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et de réplication ou exécutent des packages. Vous pouvez également configurer une tâche pour surveiller [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et déclencher des alertes. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Les travaux de l’Agent sont généralement utilisés pour automatiser des tâches à caractère répétitif. Pour plus d’informations, consultez [Implémenter des travaux](http://msdn.microsoft.com/library/69e06724-25c7-4fb3-8a5b-3d4596f21756).  
  
 Grâce à la tâche Exécuter le travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un package peut effectuer des tâches d'administration liées aux composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Par exemple, un travail d’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut exécuter une procédure stockée système telle que **sp_enum_dtspackages** pour obtenir la liste des packages stockés dans un dossier.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent doit s’exécuter avant que les travaux d’administration locaux ou multiserveurs peuvent s’exécuter automatiquement.  
  
 Cette tâche encapsule la procédure système **sp_start_job** et transmet le nom du travail d’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à la procédure en guise d’argument. Pour plus d’informations, consultez [sp_start_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-start-job-transact-sql.md).  
  
## <a name="configuring-the-execute-sql-server-agent-job-task"></a>Configuration de la tâche d'exécution de travail d'Agent SQL Server  
 Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] . Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .  
  
 Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :  
  
-   [Tâche Exécuter le travail de l’Agent SQL Server &#40;Plan de maintenance&#41;](../../relational-databases/maintenance-plans/execute-sql-server-agent-job-task-maintenance-plan.md)  
  
 Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :  
  
-   [Définir les propriétés d'une tâche ou d'un conteneur](http://msdn.microsoft.com/library/52d47ca4-fb8c-493d-8b2b-48bb269f859b)  
  
  