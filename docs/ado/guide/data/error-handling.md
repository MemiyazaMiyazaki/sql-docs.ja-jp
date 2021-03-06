---
title: エラー処理 | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- reporting errors [ADO]
- errors [ADO]
- ADO, error handling
ms.assetid: 4909e413-f3b0-4183-8ad3-67b1434df742
author: rothja
ms.author: jroth
ms.openlocfilehash: fa18c5d93617963afa1cf8d472651d03db6ed493
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761018"
---
# <a name="error-handling"></a>エラー処理
ADO では、いくつかの異なるメソッドを使用して、発生したエラーをアプリケーションに通知します。 このセクションでは、ADO を使用しているときに発生する可能性があるエラーの種類と、アプリケーションに通知する方法について説明します。 最後に、これらのエラーを処理する方法についての提案を行います。  
  
## <a name="how-does-ado-report-errors"></a>ADO はどのようにエラーを報告しますか。  
 ADO は、次のいくつかの方法でエラーを通知します。  
  
-   ADO エラーが発生すると、実行時エラーが発生します。 Visual Basic で**On error**ステートメントを使用するなど、他の実行時エラーと同じように ADO エラーを処理します。  
  
-   プログラムは OLE DB からエラーを受け取ることができます。 OLE DB エラーが発生すると、実行時エラーも発生します。  
  
-   エラーがデータプロバイダーに固有のものである場合は、エラーが発生したときにデータストアにアクセスするために使用された**接続**オブジェクトの**エラー**コレクションに、1つまたは複数の**エラー**オブジェクトが配置されます。  
  
-   イベントを発生させたプロセスでもエラーが発生した場合、エラー情報は**エラー**オブジェクトに配置され、パラメーターとしてイベントに渡されます。 イベントの詳細については、「 [ADO イベントの処理](../../../ado/guide/data/handling-ado-events.md)」を参照してください。  
  
-   バッチ更新や**レコードセット**に関連するその他の一括操作を処理するときに発生する問題は、**レコードセット**の**Status**プロパティで示すことができます。 たとえば、スキーマ制約の違反や、 **Recordstatusenum**の値で指定できる権限が不十分です。  
  
-   現在のレコード内の特定の**フィールド**に関連する問題は、**レコード**または**レコードセット**の**Fields**コレクション内の各**フィールド**の**Status**プロパティによっても示されます。 たとえば、完了できなかった更新や互換性のないデータ型を**Fieldstatusenum**値で指定できます。  
  
 このセクションでは、次のトピックを扱います。  
  
-   [ADO エラー](../../../ado/guide/data/ado-errors.md)  
  
-   [プロバイダー エラー](../../../ado/guide/data/provider-errors.md)  
  
-   [フィールドに関連するエラー情報](../../../ado/guide/data/field-related-error-information.md)  
  
-   [レコードセット関連のエラー情報](../../../ado/guide/data/recordset-related-error-information.md)  
  
-   [他の言語でエラーを処理する](../../../ado/guide/data/handling-errors-in-other-languages.md)  
  
-   [エラーの予測](../../../ado/guide/data/anticipating-errors.md)
