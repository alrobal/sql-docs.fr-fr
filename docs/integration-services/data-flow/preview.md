---
title: "Version préliminaire | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f51bbd1d818a8ffd20e5124180947846c58f98c3
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="preview"></a>Aperçu
  Utilisez la boîte de dialogue **Aperçu** pour afficher un aperçu des données que la source SAP BW devra extraire.  
  
> [!IMPORTANT]  
>  L'option **Aperçu** , qui est disponible sur la page **Gestionnaire de connexions** de l' **Éditeur de source SAP BW**, extrait réellement des données. Si vous avez configuré le système SAP Netweaver BW pour extraire uniquement les données qui ont été modifiées depuis l'extraction précédente, la sélection d' **Aperçu** exclura les données de l'aperçu de l'extraction suivante.  
  
 Pour en savoir plus sur le composant source SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Source SAP BW](../../integration-services/data-flow/sap-bw-source.md).  
  
> [!IMPORTANT]  
>  La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW. Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.  
  
> [!IMPORTANT]  
>  Vous devez disposer d'une licence SAP supplémentaire pour extraire des données à partir de SAP Netweaver BW. Vérifiez auprès de SAP.  
  
 **Pour ouvrir la boîte de dialogue Aperçu**  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui contient la source SAP BW.  
  
2.  Sous l’onglet **Flux de données** , double-cliquez sur la source SAP BW.  
  
3.  Dans l' **Éditeur de source SAP BW**, cliquez sur **Gestionnaire de connexions** pour ouvrir la page **Gestionnaire de connexions** de l'éditeur.  
  
4.  Configurez la source SAP BW.  
  
5.  Après avoir configuré la source SAP BW, sur la page **Gestionnaire de connexions** , cliquez sur **Aperçu** pour afficher un aperçu des données dans la boîte de dialogue **Aperçu** .  
  
    > [!NOTE]  
    >  Cliquer sur **Aperçu** ouvre également la boîte de dialogue **Journal des requêtes** . Pour plus d'informations sur cette boîte de dialogue, consultez [Request Log](../../integration-services/data-flow/request-log.md).  
  
## <a name="options"></a>Options  
 La boîte de dialogue **Aperçu** affiche les lignes qui sont demandées par le système SAP Netweaver BW. Les colonnes qui sont affichées sont les colonnes qui sont définies dans les données sources.  
  
 Il n'existe aucune autre option dans cette boîte de dialogue.  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de source SAP BW &#40;page Gestionnaire de connexions&#41;](../../integration-services/data-flow/sap-bw-source-editor-connection-manager-page.md)   
 [Aide (F1) sur Microsoft Connector pour SAP BW](../../integration-services/microsoft-connector-for-sap-bw-f1-help.md)  
  
  