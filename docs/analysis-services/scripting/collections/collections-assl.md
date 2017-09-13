---
title: Collections (ASSL) | Documents Microsoft
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- collections [Analysis Services Scripting Language]
- Analysis Services Scripting Language, collections
- ASSL, collections
ms.assetid: 072b8c6b-1550-4cab-ae64-ba0e3e60b059
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f9751d6b4052575c85abf41f745817def8f7ae75
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="collections-assl"></a>Collections (ASSL)
  Cette section de référence contient des informations de syntaxe et d’utilisation pour chaque élément qui se comporte comme une collection dans le schéma ASSL (Analysis Services Scripting Language).  
  
 Bien que le schéma ASSL renferme uniquement des éléments XML à partir du point de vue d’un développeur, les éléments décrits dans cette section correspondent à des collections d’objets, tels que les **Dimensions** et **Cubes** collections.  
  
 Les collections sont essentiellement des collections d’éléments de l’objet, dans lequel un nom au pluriel désigne la collection (pour obtenir des exemples, **Cubes**), et la collection contient des éléments désignées par le même nom au singulier (par exemple, **Cube**).  
  
 Dans certains cas toutefois, le schéma ne respecte pas cette règle générale. Par exemple, le **ClassifiedColumns** collection contient **ClassifiedColumnID** éléments.  
  
 Dans d'autres cas, une collection contient des éléments qui correspondent à des propriétés d'objet et non à des objets. Par exemple, le **alias** collection contient **Alias** propriétés, chacun d’eux est une valeur de chaîne simple.  
  
|Élément| Description|  
|-------------|-----------------|  
|[Élément Accounts &#40; ASSL &#41;](../../../analysis-services/scripting/collections/accounts-element-assl.md)|Contient la collection des types de compte sont définies dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément actions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/actions-element-assl.md)|Contient la collection d’actions pour un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) ou [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Élément AggregationDesigns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationdesigns-element-assl.md)|Contient la collection des conceptions d'agrégation qu'il est possible de partager sur plusieurs partitions dans une base de données.|  
|[Élément AggregationInstances &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregationinstances-element-assl.md)|Contient la collection d’instances d’agrégation qui sont définies dans un [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) élément.|  
|[Élément Aggregations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aggregations-element-assl.md)|Contient la collection des agrégations définies pour un [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) élément.|  
|[Élément AlgorithmParameters &#40; ASSL &#41;](../../../analysis-services/scripting/collections/algorithmparameters-element-assl.md)|Contient la collection de paramètres pour l’algorithme utilisé par un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément.|  
|[Élément Aliases &#40; ASSL &#41;](../../../analysis-services/scripting/collections/aliases-element-assl.md)|Contient la collection de [Alias](../../../analysis-services/scripting/properties/alias-element-assl.md) éléments associés à un [compte](../../../analysis-services/scripting/objects/account-element-assl.md) élément|  
|[Élément AllMemberTranslations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/allmembertranslations-element-assl.md)|Contient la collection de [traduction](../../../analysis-services/scripting/objects/translation-element-assl.md) éléments pour la légende du membre All d’un [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) élément.|  
|[Élément annotations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/annotations-element-assl.md)|Contient la collection de [Annotation](../../../analysis-services/scripting/objects/annotation-element-assl.md) éléments associés à l’élément parent.|  
|[Élément Assemblies &#40; ASSL &#41;](../../../analysis-services/scripting/collections/assemblies-element-assl.md)|Contient la collection de [Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md) éléments associés à un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément ou un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément AttributeAllMemberTranslations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributeallmembertranslations-element-assl.md)|Contient la collection de traductions pour la légende du membre All de la dimension.|  
|[Élément AttributePermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributepermissions-element-assl.md)|Contient la collection d’autorisations d’attribut pour un individu [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément sur une dimension spécifique d’un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément AttributeRelationships &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributerelationships-element-assl.md)|Contient la collection de [AttributeRelationship](../../../analysis-services/scripting/objects/attributerelationship-element-assl.md) éléments pour l’attribut.|  
|[Élément Attributes &#40; ASSL &#41;](../../../analysis-services/scripting/collections/attributes-element-assl.md)|Contient la collection d'attributs pour la dimension associée.|  
|[Élément Blocks &#40; ASSL &#41;](../../../analysis-services/scripting/collections/blocks-element-assl.md)|Contient la collection de blocs de données binaires qui représentent le contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.|  
|[Élément CalculationProperties &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculationproperties-element-assl.md)|Contient la collection de [CalculationProperty](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md) éléments associés à un [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) élément.|  
|[Élément calculations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/calculations-element-assl.md)|Contient la collection de [PerspectiveCalculation](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md) éléments associés à un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Élément CellPermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cellpermissions-element-assl.md)|Contient la collection d’autorisations pour les cellules dans le type [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément ClassifiedColumns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/classifiedcolumns-element-assl.md)|Contient la collection de colonnes associées classées par le [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) élément.|  
|[Élément Columns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/columns-element-assl.md)|Contient la collection de colonnes associée à l'élément parent.|  
|[Élément Commands &#40; ASSL &#41;](../../../analysis-services/scripting/collections/commands-element-assl.md)|Contient la collection d'éléments [Command](../../../analysis-services/scripting/objects/command-element-assl.md) associée à un élément [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) .|  
|[Élément CubePermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubepermissions-element-assl.md)|Contient la collection d’autorisations applicable à un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Cubes, élément &#40; ASSL &#41;](../../../analysis-services/scripting/collections/cubes-element-assl.md)|Contient la collection de [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) éléments associés à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément DatabasePermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databasepermissions-element-assl.md)|Contient la collection de [DatabasePermission](../../../analysis-services/scripting/objects/databasepermission-element-assl.md) éléments associés à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément de bases de données &#40; ASSL &#41;](../../../analysis-services/scripting/collections/databases-element-assl.md)|Contient la collection de [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) éléments associés à un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément.|  
|[Élément de sources de données &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasources-element-assl.md)|Contient la collection de [DataSourcePermission](../../../analysis-services/scripting/objects/datasourcepermission-element-assl.md) éléments associés à un [source de données](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md) type de données.|  
|[Élément DataSourcePermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourcepermissions-element-assl.md)|Contient la collection de [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) éléments associés à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément DataSourceViews &#40; ASSL &#41;](../../../analysis-services/scripting/collections/datasourceviews-element-assl.md)|Contient la collection de [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) éléments associés à un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément DimensionPermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensionpermissions-element-assl.md)|Contient la collection d’autorisations applicable à un [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) élément ou un [CubePermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md) élément.|  
|[Élément dimensions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/dimensions-element-assl.md)|Contient la collection de dimensions associée à l'élément parent.|  
|[Élément Events &#40; ASSL &#41;](../../../analysis-services/scripting/collections/events-element-assl.md)|Définit la collection d’éléments d’événement à capturer par un [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md).|  
|[Élément de fichiers &#40; ASSL &#41;](../../../analysis-services/scripting/collections/files-element-assl.md)|Contient la collection de [fichier](../../../analysis-services/scripting/objects/file-element-assl.md) les éléments qui composent un [ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) élément.|  
|[Élément ForeignKeyColumns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/foreignkeycolumns-element-assl.md)|Contient la collection des colonnes qui identifient la jointure à la table parente pour une source de données relationnelle.|  
|[Élément Groups &#40; ASSL &#41;](../../../analysis-services/scripting/collections/groups-element-assl.md)|Contient la collection des groupes de membres liés à un attribut.|  
|[Élément Hierarchies &#40; ASSL &#41;](../../../analysis-services/scripting/collections/hierarchies-element-assl.md)|Contient la collection de [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) éléments associés à l’élément parent.|  
|[Élément IncrementalProcessingNotifications &#40; ASSL &#41;](../../../analysis-services/scripting/collections/incrementalprocessingnotifications-element-assl.md)|Contient la collection de [IncrementalProcessingNotification](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md) les éléments qui fournissent des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les requêtes à exécuter afin de déterminer la progression du traitement incrémentiel.|  
|[Élément KeyColumns &#40; ASSL &#41;](../../../analysis-services/scripting/collections/keycolumns-element-assl.md)|Contient la collection de [KeyColumn](../../../analysis-services/scripting/objects/keycolumn-element-assl.md) définitions d’élément pour un objet parent.|  
|[Élément KPIs &#40; ASSL &#41;](../../../analysis-services/scripting/collections/kpis-element-assl.md)|Contient la collection de [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md) éléments associés à l’élément parent.|  
|[Élément Levels &#40; ASSL &#41;](../../../analysis-services/scripting/collections/levels-element-assl.md)|Contient la collection de [niveau](../../../analysis-services/scripting/objects/level-element-assl.md) éléments dans un [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) élément.|  
|[Élément MdxScripts &#40; ASSL &#41;](../../../analysis-services/scripting/collections/mdxscripts-element-assl.md)|Contient la collection de [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) éléments associés à un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément MeasureGroups &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measuregroups-element-assl.md)|Contient la collection de [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) éléments associés à l’élément parent.|  
|[Élément Measures &#40; ASSL &#41;](../../../analysis-services/scripting/collections/measures-element-assl.md)|Contient la collection de [mesure](../../../analysis-services/scripting/objects/measure-element-assl.md) éléments associés à l’élément parent.|  
|[Membres de l’élément &#40; ASSL &#41;](../../../analysis-services/scripting/collections/members-element-assl.md)|Contient la collection d'éléments [Member](../../../analysis-services/scripting/objects/member-element-assl.md) de l'élément parent.|  
|[Élément MiningModelPermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodelpermissions-element-assl.md)|Contient la collection d’autorisations pour un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément.|  
|[Élément MiningModels &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningmodels-element-assl.md)|Contient la collection de [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) éléments associés à un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md).|  
|[Élément MiningStructurePermissions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructurepermissions-element-assl.md)|Contient la collection d’autorisations sur un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) élément.|  
|[Élément MiningStructures &#40; ASSL &#41;](../../../analysis-services/scripting/collections/miningstructures-element-assl.md)|Contient la collection de [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) éléments dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément ModelingFlags &#40; ASSL &#41;](../../../analysis-services/scripting/collections/modelingflags-element-assl.md)|Contient la collection de [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) les éléments d’une colonne dans un [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) ou un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md).|  
|[Élément NamingTemplateTranslations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/namingtemplatetranslations-element-assl.md)|Fournit une collection de traductions localisées pour le [NamingTemplate](../../../analysis-services/scripting/properties/namingtemplate-element-assl.md) élément du parent [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md).|  
|[Élément partitions &#40; ASSL &#41;](../../../analysis-services/scripting/collections/partitions-element-assl.md)|Contient la collection de [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) éléments utilisés par un [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) élément ou la collection de liaisons de partition qui composent une hors ligne [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md) élément.|  
|[Élément perspectives &#40; ASSL &#41;](../../../analysis-services/scripting/collections/perspectives-element-assl.md)|Contient la collection de [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) éléments associés à un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément QueryNotifications &#40; ASSL &#41;](../../../analysis-services/scripting/collections/querynotifications-element-assl.md)|Contient la collection de [QueryNotification](../../../analysis-services/scripting/objects/querynotification-element-assl.md) les éléments qui fournissent des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les requêtes à exécuter pour déterminer si une source de données a été modifiée.|  
|[Élément ReportFormatParameters &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportformatparameters-element-assl.md)|Contient la collection d'éléments [ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md) pour un élément [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) .|  
|[Élément ReportParameters &#40; ASSL &#41;](../../../analysis-services/scripting/collections/reportparameters-element-assl.md)|Contient la collection de [ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md) éléments pour une [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) élément.|  
|[Élément roles &#40; ASSL &#41;](../../../analysis-services/scripting/collections/roles-element-assl.md)|Contient la collection d'éléments [Role](../../../analysis-services/scripting/objects/role-element-assl.md) définie sous l'élément parent.|  
|[Élément ServerProperties &#40; ASSL &#41;](../../../analysis-services/scripting/collections/serverproperties-element-assl.md)|Contient la collection de [ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md) éléments associés à un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément.|  
|[Élément TableNotifications &#40; ASSL &#41;](../../../analysis-services/scripting/collections/tablenotifications-element-assl.md)|Contient la collection de [TableNotification](../../../analysis-services/scripting/objects/tablenotification-element-assl.md) les éléments qui fournissent des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur les tables ou vues dans une source de données qui ont été modifiées.|  
|[Élément traces &#40; ASSL &#41;](../../../analysis-services/scripting/collections/traces-element-assl.md)|Contient la collection d'éléments [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) associée à un élément [Server](../../../analysis-services/scripting/objects/server-element-assl.md) .|  
|[Élément translations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/translations-element-assl.md)|Contient la collection de [traduction](../../../analysis-services/scripting/objects/translation-element-assl.md) éléments associés à l’élément parent.|  
|[Élément UnknownMemberTranslations &#40; ASSL &#41;](../../../analysis-services/scripting/collections/unknownmembertranslations-element-assl.md)|Contient la collection de traductions pour la légende de la [UnknownMember](../../../analysis-services/scripting/properties/unknownmember-element-assl.md) élément d’une dimension.|  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services Scripting Language hiérarchie des éléments XML &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  