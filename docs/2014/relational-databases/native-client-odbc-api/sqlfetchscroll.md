---
title: SQLFetchScroll |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 2b4a5094f8bac1e3972b4d0b2daa7a0da9fa3629
ms.sourcegitcommit: b72c9fc9436c44c6a21fd96223c73bf94706c06b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706130"
---
# <a name="sqlfetchscroll"></a>SQLFetchScroll
  **Sqlfetchscroll**は、データの1つの行セットをアプリケーションに返します。 行セットのサイズは[SQLSetStmtAttr](sqlsetstmtattr.md)を使用して設定されます。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Native CLIENT ODBC ドライバーでは、定義済みのすべてのフェッチ命令 (SQL_FETCH_RELATIVE など) がサポートされていますが、次の制限があります。  
  
-   ステートメントに順方向専用カーソルを定義する場合は、SQL_FETCH_NEXT が必要です。他の形式でフェッチを試行すると、エラーが返されます。  
  
-   SQL_FETCH_BOOKMARK がサポートされるのは、静的カーソルとキーセット ドリブン カーソルに対してのみです。  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a>SQLFetchScroll による機能強化された日付と時刻のサポート  
 Date 型または time 型の結果列の値は、「 [SQL から C への変換](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md)」で説明されているように変換されます。  
  
 詳細については、「[日付と時刻の機能強化 &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md)」を参照してください。  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a>SQLFetchScroll による大きな CLR UDT のサポート  
 **Sqlfetchscroll**は、大きな CLR ユーザー定義型 (udt) をサポートしています。 詳細については、「[大容量の CLR ユーザー定義型 &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [SQLFetchScroll 関数](https://go.microsoft.com/fwlink/?LinkId=59343)   
 [ODBC API 実装の詳細](odbc-api-implementation-details.md)  
  
  
