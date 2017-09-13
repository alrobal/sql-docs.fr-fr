---
title: local-nom-de-QName (XQuery) | Documents Microsoft
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:local-name-from-QName function
- local-name-from-QName function
ms.assetid: fafed718-8c3c-403f-93ee-ec51fc157a6e
caps.latest.revision: 16
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 506a9923b8c74ecb022e6f3ba21305fb28ca49de
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="functions-related-to-qnames---local-name-from-qname"></a>Fonctions relatives aux QName - nom local de QName
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne un xs : NCName qui représente la partie locale de QName indiquée par *$arg*. Le résultat est une séquence vide si *$arg* est la séquence vide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
fn:local-name-from-QName($arg as xs:QName?) as xs:NCName?  
```  
  
## <a name="arguments"></a>Arguments  
 *$arg*  
 QName d'où le nom local doit être extrait.  
  
## <a name="examples"></a>Exemples  
 Cette rubrique fournit des exemples de XQuery relatifs à des instances XML stockés dans différentes **xml** type des colonnes dans le [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] base de données.  
  
 L’exemple suivant utilise le **local-name-from-QName()** fonction pour récupérer le nom local et l’URI d’espace de noms de pièces à partir d’une valeur de type QName. Cet exemple illustre les opérations suivantes :  
  
-   La requête crée une collection de schémas XML.  
  
-   Elle crée ensuite une table possédant une colonne de type xml. Ce type est typé par le biais de la collection de schémas XML.  
  
-   Elle stocke enfin une instance XML servant d'échantillon dans la table. À l’aide de la **query()** méthode du type de données xml, l’expression de requête est exécutée pour récupérer la partie nom local de la valeur de type QName à partir de l’instance.  
  
```  
DROP TABLE T  
go  
DROP XML SCHEMA COLLECTION SC  
go  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
targetNamespace="QNameXSD" >  
      <element name="root" type="QName" nillable="true"/>  
</schema>'  
go  
  
CREATE TABLE T (xmlCol XML(SC))  
go  
-- following OK  
insert into T values ('<root xmlns="QNameXSD" xmlns:a="http://someURI">a:someLocalName</root>')  
 go  
-- Retrieve the local name.   
SELECT xmlCol.query('declare default element namespace "QNameXSD"; local-name-from-QName(/root[1])')  
FROM T  
-- Result = someLocalName  
-- You can retrive namespace URI part from the QName using the namespace-uri-from-QName() function  
SELECT xmlCol.query('declare default element namespace "QNameXSD"; namespace-uri-from-QName(/root[1])')  
FROM T  
-- Result = http://someURI  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions relatives aux QName &#40; XQuery &#41;](http://msdn.microsoft.com/library/7e07eb26-f551-4b63-ab77-861684faff71)  
  
  