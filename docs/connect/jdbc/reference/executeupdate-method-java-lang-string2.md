---
title: executeUpdate メソッド (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 02/07/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerPreparedStatement.executeUpdate (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 91ecb1cd-001d-4ac9-9ae8-5db05c3c2959
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 428127147d00885dc379752e97154e8eabad54d1
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80924206"
---
# <a name="executeupdate-method-javalangstring"></a>executeUpdate (java.lang.String) メソッド

渡された SQL ステートメントを実行します。ステートメントは INSERT、UPDATE、MERGE、DELETE、または SQL DDL ステートメントのような何も返さない SQL ステートメントが可能です。

## <a name="syntax"></a>構文

```
public final int executeUpdate(java.lang.String sql)
```

#### <a name="parameters"></a>パラメーター
*sql*

SQL ステートメントを含む**文字列**です。

## <a name="return-value"></a>戻り値
影響を受けた行数を示す **int** です。DDL ステートメントを使用している場合は 0 です。

## <a name="exceptions"></a>例外
[SQLServerException](./sqlserverexception-class.md)

## <a name="remarks"></a>解説
この executeUpdate メソッドは、java.sql.PreparedStatement インターフェイスの executeUpdate メソッドで規定されています。

SQLServerPreparedStatement オブジェクトが作成される際、オブジェクトの SQL ステートメントが指定されるため、このメソッドを呼び出すと例外が発生します。

## <a name="see-also"></a>参照

[executeUpdate メソッド &#40;SQLServerPreparedStatement&#41;](./executeupdate-method-sqlserverpreparedstatement.md)

[SQLServerPreparedStatement のメンバー](./sqlserverpreparedstatement-members.md)

[SQLServerPreparedStatement クラス](./sqlserverpreparedstatement-class.md)
