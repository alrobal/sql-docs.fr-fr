---
title: "Protocoles clients - nommé de propriétés de canaux (onglet protocole) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 33d801033e2431f465e97502dcabf37f6a9c4847
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# Protocoles clients - Propriétés de Canaux nommés (onglet Protocole)
  Dans le Gestionnaire de configuration [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilisez l'onglet **Protocole** de la boîte de dialogue **Propriétés de Canaux nommés** pour visualiser ou modifier la description du canal par défaut. Pour vous connecter à un autre canal, tapez son nom dans la zone **Canal par défaut** . Pour plus d'informations sur les chaînes de connexion, consultez [Creating a Valid Connection String Using Named Pipes](http://msdn.microsoft.com/library/90930ff2-143b-4651-8ae3-297103600e4f).  
  
## Options  
 **Canal par défaut**  
 Spécifie le canal par défaut que la Net-Library des canaux nommés essaie d'utiliser pour se connecter à l'instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est à l'écoute sur : `\\.\pipe\sql\query`  
  
 Pour vous connecter au canal par défaut, entrez `sql\query`  
  
 **Activé**  
 Les valeurs possibles sont **Yes** et **No**.  
  
## Voir aussi  
 [Choix d’un protocole réseau](http://msdn.microsoft.com/library/6565fb7d-b076-4447-be90-e10d0dec359a)  
  
  