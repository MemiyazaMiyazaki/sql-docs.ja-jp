---
title: テーブル名 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQL grammar [ODBC], table names
- table names [ODBC]
ms.assetid: f7a5cb0a-3be7-4f46-82f9-64ffdbceaa9b
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 91a415cd456186f18ef358b9d504145f78152774
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81303123"
---
# <a name="table-names"></a>テーブル名
DBASE、Microsoft Excel、Paradox、または Text driver が使用されている場合、SELECT または DELETE の FROM 句で使用されるテーブル名、INSERT の INTO 句、および after UPDATE、CREATE TABLE、および DROP TABLE の後に、有効なパス、プライマリ名、およびファイル名拡張子を含めることができます。  
  
 SQL ステートメント内の他の場所でテーブル名を使用しても、パスや拡張子の使用はサポートされていませんが、プライマリ名 (たとえば、EMP FROM C:\ABC\EMP) は使用できません。  
  
 相関名 (エイリアス) を使用できます。 次に例を示します。  
  
```  
SELECT *    
FROM C:\ABC\EMP T1    
WHERE T1.COL1 = 'aaa'  
```
