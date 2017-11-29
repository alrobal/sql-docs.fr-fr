---
title: Sys.service_broker_endpoints (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.service_broker_endpoints_TSQL
- service_broker_endpoints
- service_broker_endpoints_TSQL
- sys.service_broker_endpoints
dev_langs: TSQL
helpviewer_keywords: sys.service_broker_endpoints catalog view
ms.assetid: 6979ec9b-0043-411e-aafb-0226fa26c5ba
caps.latest.revision: "51"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d7f9fdc08d74c9ca3e8c469462451fdd7bc5e49b
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysservicebrokerendpoints-transact-sql"></a>sys.service_broker_endpoints (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Cet affichage catalogue contient une ligne pour le point de terminaison Service Broker. Pour chaque ligne dans cette vue, il existe une ligne correspondante avec le même **endpoint_id** dans les **sys.tcp_endpoints** vue qui contient les métadonnées de la configuration TCP. TCP est le seul protocole autorisé pour Service Broker.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**\<héritée de colonnes >**|**--**|Hérite des colonnes de [sys.endpoints &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-endpoints-transact-sql.md).|  
|**is_message_forwarding_enabled**|**bit**|Indique si le point de terminaison prend en charge la transmission de message. Ce paramètre est initialement défini **0** (désactivé). Cette colonne n'accepte pas la valeur NULL.|  
|**MESSAGE_FORWARDING_SIZE**|**int**|Le nombre maximal de mégaoctets de **tempdb** espace peut être utilisée pour les messages transmis. Ce paramètre est initialement défini **10**. Cette colonne n'accepte pas la valeur NULL.|  
|**connection_auth**|**tinyint**|Type d'authentification de connexion requis pour les connexions à ce point de terminaison. Peut prendre l'une des valeurs suivantes :<br /><br /> **1** -NTLM<br /><br /> **2** -KERBEROS<br /><br /> **3** -NÉGOCIER<br /><br /> **4** -CERTIFICAT<br /><br /> **5** -NTLM, DE CERTIFICAT<br /><br /> **6** -KERBEROS, LE CERTIFICAT<br /><br /> **7** -NEGOCIATE, CERTIFICAT<br /><br /> **8** -CERTIFICAT, NTLM<br /><br /> **9** -CERTIFICAT, KERBEROS<br /><br /> **10** -CERTIFICAT, NEGOTIATE<br /><br /> Cette colonne n'accepte pas la valeur NULL.|  
|**connection_auth_desc**|**nvarchar (60)**|Description du type d'authentification de connexion requis pour les connexions à ce point de terminaison :<br /><br /> NTLM<br /><br /> KERBEROS<br /><br /> NEGOTIATE<br /><br /> CERTIFICATE<br /><br /> NTLM, CERTIFICATE<br /><br /> KERBEROS, CERTIFICATE<br /><br /> NEGOTIATE, CERTIFICATE<br /><br /> CERTIFICATE, NTLM<br /><br /> CERTIFICATE, KERBEROS<br /><br /> CERTIFICATE, NEGOTIATE<br /><br /> Accepte la valeur NULL.|  
|**id_certificat**|**int**|ID du certificat utilisé pour l'authentification, le cas échéant.<br /><br /> 0 = L'authentification Windows et utilisée.|  
|**encryption_algorithm**|**tinyint**|Algorithme de chiffrement. Voici les valeurs possibles avec leurs descriptions et les options correspondantes de DDL.<br /><br /> **0** : AUCUNE. Option DDL correspondante : désactivé.<br /><br /> **1** : RC4. Option DDL correspondante : {requis &#124; Algorithme requis RC4}.<br /><br /> **2** : AES. Option DDL correspondante : requis algorithme AES.<br /><br /> **3** : NONE, RC4. Option DDL correspondante : {pris en charge &#124; Prise en charge de l’algorithme RC4}.<br /><br /> **4** : AUCUN, AES. Option DDL correspondante : prise en charge d’algorithme AES.<br /><br /> **5** : RC4, AES. Option DDL correspondante : requis algorithme RC4 AES.<br /><br /> **6** : AES, RC4. Option DDL correspondante : requises de l’algorithme AES RC4.<br /><br /> **7** : NONE, RC4, AES. Option DDL correspondante : prise en charge d’algorithme RC4 AES.<br /><br /> **8** : AUCUN, AES, RC4. Option DDL correspondante : prise en charge de l’algorithme AES RC4.<br /><br /> Cette colonne n'accepte pas la valeur NULL.|  
|**encryption_algorithm_desc**|**nvarchar (60)**|Description d’algorithme de chiffrement. Les valeurs possibles et leurs options DDL correspondantes sont répertoriées ci-dessous :<br /><br /> NONE : désactivé<br /><br /> RC4 : {requis &#124; Required Algorithm RC4}<br /><br /> AES : Algorithme AES obligatoire<br /><br /> NONE, RC4 : {pris en charge &#124; Algorithme pris en charge RC4}<br /><br /> Aucun, AES : Algorithme AES pris en charge<br /><br /> RC4, AES : Obligatoire l’algorithme RC4 AES<br /><br /> AES, RC4 : Algorithme AES RC4 obligatoire<br /><br /> NONE, RC4, AES : Prise en charge l’algorithme RC4 AES<br /><br /> Aucun, AES, RC4 : Prise en charge l’algorithme AES RC4<br /><br /> Accepte la valeur NULL.|  
  
## <a name="remarks"></a>Notes  
  
> [!NOTE]  
>  L'algorithme RC4 est uniquement pris en charge pour des raisons de compatibilité descendante. Le nouveau matériel ne peut être chiffré à l'aide de RC4 ou de RC4_128 que lorsque la base de données se trouve dans le niveau de compatibilité 90 ou 100. (Non recommandé.) Utilisez à la place un algorithme plus récent, tel qu'un des algorithmes AES. Dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] et versions ultérieures, le matériel chiffré à l’aide de RC4 ou RC4_128 peut être déchiffré dans n’importe quel niveau de compatibilité.  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER ENDPOINT &#40;Transact-SQL&#41;](../../t-sql/statements/alter-endpoint-transact-sql.md)   
 [CREATE ENDPOINT &#40;Transact-SQL&#41;](../../t-sql/statements/create-endpoint-transact-sql.md)  
  
  