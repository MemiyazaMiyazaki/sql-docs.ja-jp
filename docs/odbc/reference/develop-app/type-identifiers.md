---
title: 型識別子 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data types [ODBC], identifiers
- type identifiers [ODBC]
- identifiers [ODBC], type
- type identifiers [ODBC], about type identifiers
ms.assetid: 1d9fdfa2-e378-44fe-ac66-9743d9bbdd5a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a274a19eaa0a2fdf98bcaa9ef42406ee8a6b6461
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306433"
---
# <a name="type-identifiers"></a>型識別子
ODBC では、SQL データ型と C データ型を記述するために、2つの*型識別子*のセットを定義しています。 型識別子は、SQL 列または C バッファーの型を記述します。 これは **#define**の値であり、通常は関数の引数として渡されるか、またはメタデータに返されます。  
  
 たとえば、次の**SQLBindParameter**の呼び出しでは、SQL_DATE_STRUCT 型の変数を SQL ステートメントの日付パラメーターにバインドします。 *日付*変数の型を指定 SQL_C_TYPE_DATE C 型識別子 SQL_TYPE_DATE、動的パラメーターの型を指定する SQL 型識別子です。  
  
```  
SQL_DATE_STRUCT Date;  
SQLINTEGER  DateInd = 0;  
SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_TYPE_DATE, SQL_TYPE_DATE, 0, 0,  
                  &Date, 0, &DateInd);  
```
