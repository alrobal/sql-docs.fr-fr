---
title: "Définition des propriétés pour complément Master Data Services pour Excel | Documents Microsoft"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cab1c662-5d40-4c16-9f5c-36ff9608810b
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 14b4715ce4acdc48f6425d2343cb45cd8311d982
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="setting-properties-for-master-data-services-add-in-for-excel"></a>Définition des propriétés pour le complément Master Data Services pour Excel
  Les paramètres du complément Master Data Services pour Excel déterminent la façon dont les données sont chargées à partir de MDS dans le complément Excel et la façon dont les données sont publiées du complément Excel vers MDS.  
  
 Pour créer des paramètres pour le complément Excel, ouvrez **Excel**, cliquez sur le menu **Données maîtres** , puis cliquez sur **Paramètres**. Toute personne ayant accès à Excel peut modifier ces paramètres. Les paramètres s'appliquent à l'ordinateur sur lequel Excel est ouvert.  
  
## <a name="excel-add-in-settings"></a>Paramètres du complément Excel  
  
||||  
|-|-|-|  
|Onglet et section|Paramètre|Description|  
|Paramètres : Publication|Afficher la boîte de dialogue **Publier et annoter** lors de la publication|Sélectionnez cette option pour afficher la boîte de dialogue **Publier et annoter** lorsque vous cliquez sur **Publier**, ce qui vous permet d'entrer une seule annotation pour toutes les modifications ou d'entrer une annotation pour chaque modification.<br /><br /> Désélectionnez cette option pour indiquer que le processus de publication est initialisé sans la boîte de dialogue **Publier et annoter** . Vous n'aurez pas la possibilité d'entrer une annotation.|  
|Paramètres : Version|Sélection de la version|Sélectionnez la version des données maîtres chargées dans le complément Excel. Valeurs possibles :<br /><br /> **Aucune** pour ne pas appliquer une valeur de version par défaut<br /><br /> **Plus ancienne** pour utiliser par défaut la version la plus ancienne **Plus récente** pour utiliser par défaut la version la plus récente.|  
|Paramètres : Journalisation|Activer la journalisation détaillée|Activez la journalisation pour le chargement des données de référence à partir de MDS dans le complément Excel, afin que le résultat de chaque commande du service soit enregistré.|  
|Paramètres : Télémétrie|Activer la collecte de données de télémétrie|Activez la télémétrie pour améliorer la qualité, la fiabilité et les performances du complément Excel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .|  
|Paramètres : Taille du traitement par lot|Nombre de cellules à charger|Sélectionnez un nombre pour indiquer le nombre de milliers de cellules chargées dans un lot transféré du serveur MDS vers Excel. Le nombre par défaut est de 50 000 cellules.|  
|Paramètres : Taille du traitement par lot|Nombre de cellules à publier|Sélectionnez un nombre pour indiquer le nombre de milliers de cellules publiées dans un lot retourné d'Excel vers le serveur. Le nombre par défaut est de 50 000 cellules.|  
|Paramètres : Serveurs ajoutés à la liste approuvée|Effacer tout|Cliquez pour effacer la liste des connexions qui ont été désignées comme sûres lorsque le fichier de requête de raccourci associé a été ouvert.|  
|Données : Filtres|Afficher l'avertissement de filtrage pour les jeux de données volumineux|Cliquez pour afficher un avertissement si le jeu de données chargé de MDS vers Excel dépasse le nombre maximal de lignes ou de colonnes.|  
|Données : Filtres|Lignes au maximum|Sélectionnez le seuil pour le nombre de lignes chargées, au delà duquel un avertissement de filtrage est publié.|  
|Données : Filtres|Colonnes au maximum|Sélectionnez le seuil pour le nombre de colonnes chargées, au delà duquel un avertissement de filtrage est publié.|  
|Données : Format de cellule|Modifier la couleur de cellule quand : Modification des valeurs d'attributs|Cliquez pour indiquer que la couleur d'une cellule change si la valeur d'attribut de cette cellule est modifiée lorsque vous actualisez la table du complément Excel avec de nouvelles données provenant du référentiel MDS.|  
|Données : Format de cellule|Modifier la couleur de cellule quand : Des membres sont ajoutés|Cliquez pour indiquer que la couleur des cellules d'une ligne change si un nouveau membre est ajouté à la ligne lorsque vous actualisez la table du complément Excel avec de nouvelles données provenant du référentiel MDS.|  
|Données : Format de cellule|Format d’affichage|Sélectionnez le format d’affichage souhaité pour les valeurs d’attributs basés sur un domaine. Les options possibles sont Code {Name}, Code et Nom {Code}.|  
  
  