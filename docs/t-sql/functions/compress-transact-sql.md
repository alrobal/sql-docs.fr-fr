---
title: COMPRESSER (Transact-SQL) | Documents Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COMPRESS
- COMPRESS_TSQL
helpviewer_keywords:
- COMPRESS function
ms.assetid: c2bfe9b8-57a4-48b4-b028-e1a3ed5ece88
caps.latest.revision: 9
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c30cb5f351d9a84beec608483380edb94b8c7844
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="compress-transact-sql"></a>COMPRESSER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

Compresse l’expression d’entrée à l’aide de l’algorithme GZIP. Le résultat de la compression est de type tableau d’octets **varbinary (max)**.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
COMPRESS ( expression )  
```  
  
## <a name="arguments"></a>Arguments  
*expression*  
Est un **nvarchar (***n***)**, **nvarchar (max)**, **varchar (***n***)**, **varchar (max)**, **varbinary (***n***)**, **varbinary (max)**, **char (***n***)**, **nchar (***n***)**, ou **binaire (***n***)** expression. Pour plus d’informations, consultez [Expressions &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md).
  
## <a name="return-types"></a>Types de retour
Retourne le type de données **varbinary (max)** qui représente le contenu compressé d’entrée.
  
## <a name="remarks"></a>Notes  
Les données compressées ne peuvent pas être indexées.
  
La fonction COMPRESS compresse les données fournies en tant que l’expression d’entrée et doit être appelée pour chaque section de données doit être compressé. Pour la compression au niveau de la ligne ou de page automatique pendant le stockage, consultez [la Compression des données](../../relational-databases/data-compression/data-compression.md).
  
## <a name="examples"></a>Exemples  
  
### <a name="a-compress-data-during-the-table-insert"></a>A. Compresser les données durant l’insertion de la Table  
L’exemple suivant montre comment compresser les données insérées dans la table :
  
```sql
INSERT INTO player (name, surname, info )  
VALUES (N'Ovidiu', N'Cracium',   
        COMPRESS(N'{"sport":"Tennis","age": 28,"rank":1,"points":15258, turn":17}'));  
  
INSERT INTO player (name, surname, info )  
VALUES (N'Michael', N'Raheem', compress(@info));  
```  
  
### <a name="b-archive-compressed-version-of-deleted-rows"></a>B. Archiver la version compressée des lignes supprimées  
L’instruction suivante supprime les anciens enregistrements de lecteur à partir de la `player` table et stocke les enregistrements dans la `inactivePlayer` table dans un format compressé pour économiser de l’espace.
  
```sql
DELETE player  
WHERE datemodified < @startOfYear  
OUTPUT id, name, surname datemodifier, COMPRESS(info)   
INTO dbo.inactivePlayers ;  
```  
  
## <a name="see-also"></a>Voir aussi
[Fonctions de chaîne &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  
[DÉCOMPRESSER &#40; Transact-SQL &#41;](../../t-sql/functions/decompress-transact-sql.md)
  
  
