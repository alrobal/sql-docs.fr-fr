---
title: Fournisseur Microsoft OLE DB pour la publication Internet | Documents Microsoft
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: H1Hack27Feb2017
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OLE DB provider for Internet publishing [ADO]
- providers [ADO], OLE DB provider for Internet publishing
- Internet Publishing provider [ADO]
ms.assetid: 66a208d9-b580-4655-a41e-1d36e5b5bfca
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d466123e7330eb599847225d2b108ec7f80d9ea9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="microsoft-ole-db-provider-for-internet-publishing-overview"></a>Fournisseur Microsoft OLE DB pour Internet présentation de la publication
Le fournisseur Microsoft OLE DB pour la publication Internet permet à ADO d’accéder aux ressources pris en charge par Microsoft FrontPage ou Microsoft Internet Information Server. Les ressources incluent des fichiers de source de web tels que des fichiers HTML ou des dossiers web de Windows 2000.

## <a name="connection-string-parameters"></a>Paramètres de chaîne de connexion
 Pour vous connecter à ce fournisseur, définissez la *fournisseur* argument de la [ConnectionString](../../../ado/reference/ado-api/connectionstring-property-ado.md) propriété :

```
MSDAIPP.DSO
```

 Cette valeur peut également être définie ou lue à l’aide du [fournisseur](../../../ado/reference/ado-api/provider-property-ado.md) propriété.

## <a name="typical-connection-string"></a>Chaîne de connexion classique
 Une chaîne de connexion par défaut pour ce fournisseur est :

```
"Provider=MSDAIPP.DSO;Data Source=ResourceURL;User ID=MyUserID;Password=MyPassword;"
```

 -ou-

```
"URL=ResourceURL;User ID=MyUserID;Password=MyPassword;"
```

 La chaîne se compose des mots clés suivants :

|Mot clé| Description|
|-------------|-----------------|
|**Fournisseur**|Spécifie le fournisseur OLE DB pour la publication Internet.|
|**Source de données** - ou - **URL**|Spécifie l’URL d’un fichier ou un répertoire publié dans un dossier Web.|
|**ID d'utilisateur**|Spécifie le nom d’utilisateur.|
|**Mot de passe**|Spécifie le mot de passe.|

> [!NOTE]
>  Si vous vous connectez à un fournisseur de source de données qui prend en charge l’authentification Windows, vous devez spécifier **Trusted_Connection = yes** ou **Integrated Security = SSPI** au lieu des informations d’ID et mot de passe utilisateur dans la chaîne de connexion.

 Si vous définissez la *ResourceURL* valeur à partir de la « URL = » dans la chaîne de connexion à une valeur non valide, par défaut le fournisseur de publication Internet déclenche une boîte de dialogue pour la saisie d’une valeur valide. Il s’agit d’un comportement indésirable pour un composant dans la couche intermédiaire d’une application, car il suspend l’exécution du programme jusqu'à ce que la boîte de dialogue est désactivée et le client se bloque, car il n’a pas reçu de réponse à partir du composant.

> [!NOTE]
>  Si MSDAIPP. DSO est explicitement spécifié comme valeur du fournisseur, à l’aide de la *fournisseur* mot clé de chaîne de connexion ou le **fournisseur** propriété, vous ne pouvez pas utiliser « URL = » dans la chaîne de connexion. Si vous le faites, une erreur se produit. Au lieu de cela, spécifiez simplement l’URL comme indiqué dans la rubrique [à l’aide d’ADO avec le fournisseur OLE DB pour la publication Internet](../../../ado/guide/data/the-ole-db-provider-for-internet-publishing.md).

## <a name="see-also"></a>Voir aussi
 [Scénario de publication Internet](../../../ado/guide/data/internet-publishing-scenario.md) [du fournisseur OLE DB pour la publication Internet](../../../ado/guide/data/the-ole-db-provider-for-internet-publishing.md)
