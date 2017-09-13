---
title: "L’élément Parameters (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Parameters Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Parameters
- urn:schemas-microsoft-com:xml-analysis#Parameters
- microsoft.xml.analysis.parameters
helpviewer_keywords:
- Parameters element
ms.assetid: d46454a1-a1d1-4aa8-95ea-54be22a53e83
caps.latest.revision: 11
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 27bf966c1a1fb44c547a74f38cc3cddd6399793c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="parameters-element-xmla"></a>Élément Parameters (XMLA)
  Contient une collection de [paramètre](../../../analysis-services/xmla/xml-elements-properties/parameter-element-xmla.md) éléments utilisés par le [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) (méthode).  
  
 **Namespace :**`urn:schemas-microsoft-com:xml-analysis`  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
<Execute>  
...  
   <Parameters>  
      <Parameter>...</Parameter>  
   </Parameters>  
...  
</Execute>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Exécuter](../../../analysis-services/xmla/xml-elements-methods-execute.md)|  
|Éléments enfants|[Paramètre](../../../analysis-services/xmla/xml-elements-properties/parameter-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 Certaines commandes XMLA (XML for Analysis), telles que la commande [Process](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) , peuvent exiger des informations supplémentaires. Le **paramètres** élément fournit un mécanisme qui fournit des informations supplémentaires, y compris des informations mémorisées en bloc, à une commande XMLA.  
  
 Si la commande XMLA n’utilise pas le **paramètres** élément, l’élément peut être omis lorsque vous appelez le **Execute** (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  