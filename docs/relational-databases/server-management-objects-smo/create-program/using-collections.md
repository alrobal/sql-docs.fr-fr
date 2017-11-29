---
title: "L’utilisation de Collections | Documents Microsoft"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, collections
- SMO [SQL Server], collections
- collections [SMO]
ms.assetid: 209eb175-2514-4de1-bc32-b2e6a469d945
caps.latest.revision: "49"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: fbe0ff814ef0457993feedba45b59cdfb958288e
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="using-collections"></a>Utilisation de collections
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Une collection est une liste d’objets qui ont été construits à partir de la même classe d’objet et qui partagent le même objet parent. L'objet de collection contient toujours le nom du type d'objet avec le suffixe Collection. Par exemple, pour accéder aux colonnes dans une table spécifiée, utilisez le type d'objet <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection>. Il contient tous les objets <xref:Microsoft.SqlServer.Management.Smo.Column> qui appartiennent au même objet <xref:Microsoft.SqlServer.Management.Smo.Table>.  
  
 Le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] **pour... Chaque** instruction ou le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] **foreach** instruction peut être utilisée pour itérer sur chaque membre de la collection.  
  
## <a name="examples"></a>Exemples  
Pour utiliser un exemple de code fourni, vous devrez sélectionner l'environnement, le modèle et le langage de programmation dans lequel créer votre application. Pour plus d’informations, consultez [créer un Visual C &#35; Projet SMO dans Visual Studio .NET](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-basic"></a>Référence d'un objet à l'aide d'une collection en Visual Basic  
 Cet exemple de code montre comment définir une propriété de colonne à l’aide de la <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, et <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> propriétés. Ces propriétés représentent des collections, qui peuvent être utilisées pour identifier un objet particulier lorsqu'elles sont utilisées avec un paramètre qui spécifie le nom de l'objet. Le nom et le schéma sont requis pour le <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> propriété de l’objet collection.  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Modify a property using the Databases, Tables, and Columns collections to reference a column.
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("ModifiedDate").Nullable = True
'Call the Alter method to make the change on the instance of SQL Server.
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("ModifiedDate").Alter()
```
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-c"></a>Référence d'un objet à l'aide d'une collection en Visual C#  
 Cet exemple de code montre comment définir une propriété de colonne à l’aide de la <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, et <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> propriétés. Ces propriétés représentent des collections, qui peuvent être utilisées pour identifier un objet particulier lorsqu'elles sont utilisées avec un paramètre qui spécifie le nom de l'objet. Le nom et le schéma sont requis pour le <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> propriété de l’objet collection.  
  
```csharp  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Modify a property using the Databases, Tables, and Columns collections to reference a column.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Nullable = true;   
//Call the Alter method to make the change on the instance of SQL Server.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Alter();   
}  
```  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-basic"></a>Parcours des membres d'une collection en Visual Basic  
 Cet exemple de code effectue une itération dans les <xref:Microsoft.AnalysisServices.Server.Databases%2A> affiche toutes les connexions à l’instance de base de données et la propriété de collection [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
Dim count As Integer
Dim total As Integer
'Iterate through the databases and call the GetActiveDBConnectionCount method.
Dim db As Database
For Each db In srv.Databases
    count = srv.GetActiveDBConnectionCount(db.Name)
    total = total + count
    'Display the number of connections for each database.
    Console.WriteLine(count & " connections on " & db.Name)
Next
'Display the total number of connections on the instance of SQL Server.
Console.WriteLine("Total connections =" & total)
```
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-c"></a>Parcours des membres d'une collection en Visual C#  
 Cet exemple de code effectue une itération dans les <xref:Microsoft.AnalysisServices.Server.Databases%2A> affiche toutes les connexions à l’instance de base de données et la propriété de collection [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
```csharp  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
int count = 0;   
int total = 0;   
//Iterate through the databases and call the GetActiveDBConnectionCount method.   
Database db = default(Database);   
foreach ( db in srv.Databases) {   
  count = srv.GetActiveDBConnectionCount(db.Name);   
  total = total + count;   
  //Display the number of connections for each database.   
  Console.WriteLine(count + " connections on " + db.Name);   
}   
//Display the total number of connections on the instance of SQL Server.   
Console.WriteLine("Total connections =" + total);   
}   
```  
  
  