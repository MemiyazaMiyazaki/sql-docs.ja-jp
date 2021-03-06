---
title: floor 関数 (XQuery) |Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- floor function [XQuery]
- fn:floor function
ms.assetid: 4ace57dd-b66e-4b60-a2b9-a1b0f1a0831d
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c27e432dc258b4d2b9d21bfe0ab28df8ee5b510
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "67946532"
---
# <a name="numeric-values-functions---floor"></a>数値関数 - floor
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  引数の値を超えない分数部分を含まない最大の数値を返します。 引数が空のシーケンスの場合は、空のシーケンスを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
fn:floor ($arg as numeric?) as numeric?  
```  
  
## <a name="arguments"></a>引数  
 *$arg*  
 関数が適用される番号。  
  
## <a name="remarks"></a>Remarks  
 *$Arg*の型が、 **xs: float**、 **xs: double**、または**xs: decimal**の3つの数値基本データ型のいずれかである場合、戻り値の型は *$arg*の型と同じになります。 *$Arg*の型が数値型の1つから派生した型である場合、戻り値の型は基本数値型です。  
  
 Fn: floor、fn: シーリング、または fn: round 関数への入力が**xdt: untypedAtomic**で、型指定されていないデータの場合、 **xs: double**に暗黙的にキャストされます。 その他の型のデータが入力されると、静的エラーが生成されます。  
  
## <a name="examples"></a>使用例  
 このトピックでは、AdventureWorks サンプルデータベースのさまざまな**xml**型の列に格納されている xml インスタンスに対して XQuery の例を示します。  
  
 **Floor ()** xquery 関数には、[天井関数 (xquery)](../xquery/numeric-values-functions-ceiling.md)のワーキングサンプルを使用できます。 クエリの**天井 ()** 関数を**floor ()** 関数に置き換えるだけで済みます。  
  
## <a name="implementation-limitations"></a>実装の制限事項  
 制限事項は次のとおりです。  
  
-   **Floor ()** 関数は、すべての整数値を xs: decimal にマップします。  
  
## <a name="see-also"></a>参照  
 [シーリング関数 &#40;XQuery&#41;](../xquery/numeric-values-functions-ceiling.md)   
 [round 関数 &#40;XQuery&#41;](../xquery/numeric-values-functions-round.md)   
 [xml データ型に対する XQuery 関数](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  
