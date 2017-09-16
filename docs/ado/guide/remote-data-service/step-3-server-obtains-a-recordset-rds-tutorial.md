---
title: "Étape 3 : Le serveur obtient un objet Recordset (didacticiel RDS) | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RDS tutorial [ADO], server obtains Recordset
ms.assetid: 9c6779c9-1208-4696-ac51-c39f3a6d9240
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 62210ae4cbf206faebed32b87bdbf64edd3265d9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="step-3-server-obtains-a-recordset-rds-tutorial"></a>Étape 3 : Le serveur obtient un jeu d’enregistrements (didacticiel sur les services Bureau à distance)
Le programme de serveur utilise le texte de chaîne et la commande de se connecter pour interroger la source de données pour les lignes souhaitées. ADO est généralement utilisé pour récupérer cette **Recordset**, bien que les autres Microsoft d’accès aux données des interfaces, telles que OLE DB, peut être utilisé.  
  
> [!IMPORTANT]
>  À compter de Windows 8 et Windows Server 2012, les composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (consultez Windows 8 et [Cookbook de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client Bureau à distance seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. La migration vers les applications qui utilisent des services Bureau à distance [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Un programme de serveur personnalisé peut ressembler à ceci :  
  
```  
Public Function ServerProgram(cn as String, qry as String) as Object  
Dim rs as New ADODB.Recordset  
   rs.CursorLocation = adUseClient  
   rs.Open qry, cn   
   rs.ActiveConnection = Nothing  
   Set ServerProgram = rs  
End Function  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Étape 4 : Le serveur retourne le jeu d’enregistrements (didacticiel sur les services Bureau à distance)](../../../ado/guide/remote-data-service/step-4-server-returns-the-recordset-rds-tutorial.md)   
 [Didacticiel RDS (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
