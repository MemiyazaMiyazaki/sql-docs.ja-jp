---
title: SQLSetStmtAttr (カーソルライブラリ) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLSetStmtAttr function [ODBC], Cursor Library
ms.assetid: 6018a733-c2c8-4047-92ec-92cf85031767
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1bdd9b3b559d5cc78a0d44f5280aae347bc8996a
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300492"
---
# <a name="sqlsetstmtattr-cursor-library"></a>SQLSetStmtAttr (カーソル ライブラリ)
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新しい開発作業ではこの機能の使用を避け、現在この機能を使用しているアプリケーションの変更を検討してください。 Microsoft では、ドライバーのカーソル機能を使用することをお勧めします。  
  
 このトピックでは、カーソルライブラリでの**SQLSetStmtAttr**関数の使用について説明します。 **SQLSetStmtAttr**の一般的な情報については、「 [SQLSetStmtAttr 関数](../../../odbc/reference/syntax/sqlsetstmtattr-function.md)」を参照してください。  
  
 カーソルライブラリでは、 **SQLSetStmtAttr**で次のステートメント属性がサポートされています。  
  
|||  
|-|-|  
|SQL_ATTR_CONCURRENCY|SQL_ATTR_ROW_BIND_OFFSET_PTR|  
|SQL_ATTR_CURSOR_TYPE|SQL_ATTR_ROW_BIND_TYPE|  
|SQL_ATTR_FETCH_BOOKMARK_PTR|SQL_ATTR_ROWSET_ARRAY_SIZE|  
|SQL_ATTR_PARAM_BIND_OFFSET_PTR|SQL_ATTR_SIMULATE_CURSOR|  
|SQL_ATTR_PARAM_BIND_TYPE|SQL_ATTR_USE_BOOKMARKS|  
  
 カーソルライブラリでサポートされているのは、SQL_ATTR_CURSOR_TYPE statement 属性の SQL_CURSOR_FORWARD_ONLY と SQL_CURSOR_STATIC の値だけです。  
  
 順方向専用カーソルの場合、カーソルライブラリでは、SQL_ATTR_CONCURRENCY statement 属性の SQL_CONCUR_READ_ONLY 値がサポートされます。 静的カーソルの場合、カーソルライブラリは SQL_ATTR_CONCURRENCY statement 属性の SQL_CONCUR_READ_ONLY と SQL_CONCUR_VALUES の値をサポートします。  
  
 カーソルライブラリは、SQL_ATTR_SIMULATE_CURSOR statement 属性の SQL_SC_NON_UNIQUE 値のみをサポートしています。  
  
 ODBC 仕様では、 **Sqlfetch**または**sqlfetchscroll**が呼び出された後、SQL_ATTR_PARAM_BIND_TYPE または SQL_ATTR_ROW_BIND_TYPE 属性を使用した**SQLSetStmtAttr**への呼び出しがサポートされていますが、カーソルライブラリではサポートされません。 カーソルライブラリのバインドの種類を変更する前に、アプリケーションでカーソルを閉じる必要があります。 カーソルライブラリでは、カーソルが開いているときの SQL_ATTR_ROW_BIND_OFFSET_PTR、SQL_ATTR_PARAM_BIND_OFFSET_PTR、SQL_ATTR_ROWS_FETCHED_PTR、および SQL_ATTR_PARAMS_PROCESSED_PTR ステートメントの属性の変更がサポートされています。  
  
 アプリケーションでは、カーソルが開いている間に行セットのサイズを変更するために SQL_ATTR_ROW_ARRAY_SIZE の**属性**を使用して**SQLSetStmtAttr**を呼び出すことができます。 新しい行セットのサイズは、次に**Sqlfetchscroll**または**sqlfetch**が呼び出されたときに有効になります。  
  
 カーソルライブラリでは、SQL_ATTR_PARAM_BIND_OFFSET_PTR または SQL_ATTR_ROW_BIND_OFFSET_PTR statement 属性の設定をサポートして、バインドオフセットを有効にします。 カーソルライブラリが ODBC 2 と共に使用されている場合、バインドオフセットは**Sqlfetch**の呼び出しには使用されません。*x*ドライバー。  
  
 カーソルライブラリでは、SQL_ATTR_USE_BOOKMARKS ステートメント属性を SQL_UB_VARIABLE に設定できます。
