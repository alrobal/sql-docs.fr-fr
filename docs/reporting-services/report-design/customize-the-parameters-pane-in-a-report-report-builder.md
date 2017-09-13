---
title: "Personnaliser le volet de paramètres dans un rapport (Générateur de rapports) | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ce9e8d5-911a-4422-928f-a8d005b79fc6
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d9ca14104f9dd60fda20d723290789733f0a9f4a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="customize-the-parameters-pane-in-a-report-report-builder"></a>Customize the Parameters Pane in a Report (Report Builder)
  Lors de la création de rapports paginés avec des paramètres dans le Générateur de rapports, vous pouvez personnaliser le volet Paramètres. Dans la vue Conception de rapport, vous pouvez faire glisser un paramètre vers une colonne et une ligne spécifiques du volet Paramètres. Vous pouvez ajouter et supprimer des colonnes pour modifier la disposition du volet.  
  
 Quand vous faites glisser un paramètre vers une nouvelle colonne et une nouvelle ligne du volet, l’ordre des paramètres change dans le volet **Données du rapport** . Quand vous modifiez l’ordre du paramètre dans le volet **Données du rapport** , ce paramètre change d’emplacement dans le volet. Pour plus d’informations sur la raison pour laquelle l’ordre des paramètres est important, consultez [modifier l’ordre d’un paramètre de rapport &#40; Le Générateur de rapports et SSRS &#41; ](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md).  
  
## <a name="to-customize-the-parameters-pane"></a>Pour personnaliser le volet Paramètres  
  
1.  Dans l’onglet **Affichage** , cochez la case **Paramètres** pour afficher le volet Paramètres.  
  
     ![Volet de paramètres d’accès à partir de l’onglet Affichage](../../reporting-services/report-design/media/ssrs-customparameter-accessparameterpanedesignmode.png "volet de paramètres d’accès à partir de l’onglet Affichage")  
  
     Le volet apparaît dans la partie supérieure de l’aire de conception.  
  
2.  Pour ajouter un paramètre au volet, effectuez l’une des opérations suivantes.  
  
    -   Cliquez avec le bouton droit sur une cellule vide du volet Paramètres et sélectionnez **Ajouter un paramètre**.  
  
         ![Ajouter un nouveau paramètre à partir du volet paramètres](../../reporting-services/report-design/media/ssrs-customizeparameter-addnewparameter.png "ajouter un nouveau paramètre à partir du volet Paramètres")  
  
    -   Dans le volet **Paramètres** , cliquez avec le bouton droit sur **Données du rapport** et sélectionnez **Ajouter un paramètre**.  
  
3.  Pour déplacer un paramètre au sein du volet Paramètres, faites glisser le paramètre vers une autre cellule du volet.  
  
     Lorsque vous modifiez l’emplacement du paramètre dans le volet, l’ordre de ce paramètre dans la liste **Paramètres** du volet **Données du rapport** change automatiquement. Pour plus d’informations sur l’impact de l’ordre des paramètres, consultez [modifier l’ordre d’un paramètre de rapport &#40; Le Générateur de rapports et SSRS &#41;](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
4.  Pour accéder aux propriétés d’un paramètre, effectuez l’une des opérations suivantes.  
  
    -   Cliquez avec le bouton droit sur le paramètre dans le volet Paramètres et sélectionnez **Propriétés du paramètre**.  
  
         ![Accéder aux propriétés de paramètre à partir du volet paramètres](../../reporting-services/report-design/media/ssrs-customizeparameter-accessparameterproperties-composite.png "accéder aux propriétés de paramètre à partir du volet Paramètres")  
  
    -   Cliquez avec le bouton droit sur le paramètre dans le volet **Données du rapport** et sélectionnez **Propriétés du paramètre**.  
  
5.  Pour ajouter des colonnes et des lignes au volet ou pour supprimer des colonnes et lignes existantes, cliquez avec le bouton droit sur un emplacement quelconque du volet Paramètres et sélectionnez la commande appropriée dans le menu qui s’affiche.  
  
     ![Ajouter des colonnes et des lignes dans le volet de paramètres](../../reporting-services/report-design/media/ssrs-customparameter-addcolumnsrows.png "ajouter des colonnes et des lignes dans le volet de paramètres")  
  
    > [!IMPORTANT]  
    >  Quand vous supprimez une colonne ou une ligne contenant des paramètres, ces paramètres sont supprimés du rapport.  
  
6.  Pour supprimer un paramètre du volet et du rapport, effectuez l’une des opérations suivantes.  
  
    -   Cliquez avec le bouton droit sur le paramètre dans le volet Paramètres et sélectionnez  **Supprimer**.  
  
         ![Supprimez les paramètres à partir du volet paramètres](../../reporting-services/report-design/media/ssrs-customparameter-deleteparameter.png "supprimer des paramètres à partir du volet Paramètres")  
  
    -   Cliquez avec le bouton droit sur le paramètre dans le volet **Données du rapport** et sélectionnez **Supprimer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres de rapport &#40; Le Générateur de rapports et le Concepteur de rapports &#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)  
  
  