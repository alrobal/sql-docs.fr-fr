---
title: "Créer un administrateur d’entité (Master Data Services) | Documents Microsoft"
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
ms.assetid: 717be1e8-488e-4219-8d1e-ca9084b864cd
caps.latest.revision: 5
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: e26187fb7d92fcbae23646b92d6cf02ee5511f5e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="create-an-entity-administrator-master-data-services"></a>Créer un administrateur d’entité (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un administrateur d’entité lorsque vous souhaitez qu’un groupe ou un utilisateur dispose de toutes les autorisations concernant tous les objets dans une ou plusieurs entités, ou de l’autorisation permettant d’approuver les ensembles de modification en attente.  
  
> [!TIP]  
>  Pour simplifier l’administration, créez un groupe Windows ou local et configurez-le en tant qu’administrateur d’entité. Vous pouvez ensuite ajouter et supprimer des utilisateurs dans le groupe sans accéder à l'interface utilisateur de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].  
  
## <a name="prerequisites"></a>Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
## <a name="to-create-an-entity-administrator"></a>Pour créer un administrateur d’entité  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.  
  
2.  Sélectionnez la ligne correspondant à l’utilisateur ou au groupe à modifier, puis cliquez sur **Modifier l’utilisateur sélectionné**.  
  
3.  Cliquez sur l’onglet **Modèles** , sélectionnez un modèle dans la liste **Modèles** , le cas échéant, puis cliquez sur **Modifier**.  
  
4.  Cliquez sur l’entité à laquelle vous souhaitez accorder des autorisations, puis cliquez sur l’option **Admin** dans le menu.  
  
5.  Effectuez l’étape 4 pour chaque entité que le groupe ou l’administrateur doit gérer.  
  
6.  Cliquez sur **Enregistrer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)   
 [Affecter des autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Affecter des autorisations des membres de hiérarchie &#40; Master Data Services &#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [Autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/model-object-permissions-master-data-services.md)   
 [Autorisations des membres de hiérarchie &#40; Master Data Services &#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  