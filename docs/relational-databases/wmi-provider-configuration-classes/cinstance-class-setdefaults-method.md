---
title: "Méthode SetDefaults (classe CInstance) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SetDefaults Method (CInstance Class)
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
caps.latest.revision: "32"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 744bfa80ab7207dc8b9178f4266b58ce7328d1c5
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="cinstance-class---setdefaults-method"></a>Classe CInstance - SetDefaults, méthode
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]Définit toutes les valeurs par défaut pour l’instance de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client avec l’option pour remplacer les données existantes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.SetDefaults(OverwriteAll)  
```  
  
## <a name="parts"></a>Éléments  
 *objet*  
 Objet de [classe CInstance](../../relational-databases/wmi-provider-configuration-classes/cinstance-class.md) qui représente une instance du client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre| Description|  
|---------------|-----------------|  
|*OverwriteAll*|Valeur booléenne qui spécifie s’il faut remplacer les valeurs existantes sur l’instance de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client : **true** pour remplacer les données existantes ou **false** si les données existantes ne doivent ne pas être remplacées.|  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Valeur **uint32** , égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Configurer des protocoles clients](http://technet.microsoft.com/library/ms181035.aspx)  
  
  