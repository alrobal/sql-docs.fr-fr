---
title: Paramètres globaux (boîtes de dialogue) (SybaseToSQL) | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssma-sybase
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: e11452b7-ba94-4367-a745-5ccf1764acec
caps.latest.revision: 3
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 7590ba9e50a78d572b46820e0f51ba118e21e8b0
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="global-settings-dialogs--sybasetosql"></a>Paramètres globaux (boîtes de dialogue) (SybaseToSQL)
Utilisez la page de boîtes de dialogue de la **paramètres globaux** boîte de dialogue pour spécifier l’action de l’utilisateur par défaut et les paramètres d’avertissement pour SSMA.  
  
Pour accéder aux paramètres de la boîte de dialogue sur le **outils** menu, sélectionnez **paramètres globaux**, cliquez sur **GUI** en bas du volet gauche, puis **boîtes de dialogue**.  
  
## <a name="options"></a>Options  
**Avertir avant d’écraser des objets**  
Lorsque SSMA convertit des objets SQL Server, certains objets peuvent déjà exister dans les métadonnées du projet SQL Server. Ces objets peuvent avoir déjà été convertis, ou les objets peuvent tout simplement avoir le même nom dans le schéma cible en tant qu’objets que vous vous apprêtez à convertir.  
  
Utilisez cette option pour spécifier si SSMA vous invite à entrer pour remplacer les définitions d’objet en double :  
  
-   Si vous sélectionnez **True**, SSMA affichera une boîte de dialogue d’avertissement lorsqu’il rencontre un objet dupliqué. Dans cette boîte de dialogue, vous pouvez spécifier pour remplacer des objets individuels ou tous les objets en double ou ignorer des objets individuels ou tous les objets en double.  
  
-   Si vous sélectionnez **False**, le **action de remplacement par défaut de l’objet** option apparaît, où vous spécifiez l’action par défaut.  
  
**Action par défaut de remplacement d’objet**  
Cette option apparaît si vous sélectionnez **False** pour le **avertir avant d’écraser des objets** option.  
  
Utilisez cette option pour spécifier l’objet par défaut de remplacer le comportement :  
  
-   Si vous sélectionnez **True**, SSMA remplace automatiquement dans les métadonnées de projet SQL Server, les objets qui ont le même nom et se trouvent dans le même schéma cible en tant que l’objet à convertir.  
  
-   Si vous sélectionnez **False**, SSMA ne remplace pas les métadonnées de l’objet lors de la conversion.  
  
