---
title: "Suppression de lignes dans l’ensemble de lignes avec SQLSetPos | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLSetPos function [ODBC], deleting rows
- updating data [ODBC], SQLSetPos
- data updates [ODBC], SQLSetPos
ms.assetid: 3117a47d-e179-4f76-89d0-656582f1c9bb
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ac33a8370cbd76a3dde43df68c12c9417fc78e07
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="deleting-rows-in-the-rowset-with-sqlsetpos"></a>Suppression de lignes dans l’ensemble de lignes avec SQLSetPos
L’opération de suppression de **SQLSetPos** permet de supprimer une ou plusieurs lignes sélectionnées d’une table de la source de données. Pour supprimer des lignes avec **SQLSetPos**, l’application appelle **SQLSetPos** avec *opération* défini sur SQL_DELETE et *RowNumber* définie pour le numéro de la ligne à supprimer. Si *RowNumber* est 0, toutes les lignes dans l’ensemble de lignes sont supprimées.  
  
 Après avoir **SQLSetPos** est retournée, la ligne supprimée est la ligne actuelle et son statut est SQL_ROW_DELETED. La ligne ne peut pas être utilisée dans toutes les opérations positionnées supplémentaires, telles que les appels à **SQLGetData** ou **SQLSetPos**.  
  
 Lors de la suppression de toutes les lignes de l’ensemble de lignes (*RowNumber* est égal à 0), l’application peut empêcher le pilote à partir de la suppression de certaines lignes à l’aide du tableau d’opération de ligne, de la même façon que pour l’opération de mise à jour de **SQLSetPos**. (Consultez [mise à jour des lignes dans l’ensemble de lignes avec SQLSetPos](../../../odbc/reference/develop-app/updating-rows-in-the-rowset-with-sqlsetpos.md).)  
  
 Chaque ligne supprimée doit être une ligne qui existe dans le jeu de résultats. Si les mémoires tampons d’application ont été remplies par extraction et un tableau d’état de ligne a été maintenu, ses valeurs à chacune de ces positions de ligne ne doivent pas être SQL_ROW_DELETED, SQL_ROW_ERROR ou SQL_ROW_NOROW.