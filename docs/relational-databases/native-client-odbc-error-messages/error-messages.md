---
title: エラーメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 7d632d1d22cd8439a3d787e22301ec06ec4e0d93
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81291748"
---
# <a name="error-messages"></a>エラー メッセージ
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] NATIVE Client ODBC ドライバーによって返されるメッセージのテキストは、 **SQLGetDiagRec**の*messagetext*パラメーターに格納されます。 メッセージのヘッダーには、次のようにエラーの発生元が記載されます。  
  
 [Microsoft][ODBC Driver Manager]  
 このヘッダーに関連するエラーは、ODBC ドライバー マネージャーで発生しています。  
  
 [Microsoft][ODBC Cursor Library]  
 このヘッダーに関連するエラーは、ODBC カーソル ライブラリで発生しています。  
  
 [Microsoft][SQL Server Native Client]  
 これらのエラーは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] NATIVE Client ODBC ドライバーによって発生します。 Net-Library または [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の名前が付いているノードが他にない場合、エラーはドライバー内で発生しています。  
  
 エクスプローラー[SQL Server Native Client][*Net-transportname*]  
 これらのエラーは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] net-library によって発生します。 *net-transportname*は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]クライアントネットワークトランスポート (名前付きパイプ、共有メモリ、tcp/ip ソケット、VIA など) の表示名です。 エラー メッセージの残りの部分には、呼び出された Net-Library 関数と、TDS 関数から呼び出された基になるネットワーク API の関数が含まれています。 これらのエラーと共に返される*pfNative*エラーコードは、基になるネットワークプロトコルスタックからのエラーコードです。  
  
 エクスプローラー[SQL Server Native Client][ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]  
 このヘッダーに関連するエラーは、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] で発生しています。 エラー メッセージの残りの部分は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のエラー メッセージのテキストです。 これらのエラーと共に返される*pfNative*コードは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]からのエラー番号です。 に[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]よって返されるエラーメッセージの一覧 (およびその番号) の詳細については、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の**master**データベースにある**sysmessages**システムテーブルの description 列と error 列を参照してください。  
  
## <a name="see-also"></a>参照  
 [エラーとメッセージの処理](../../relational-databases/native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
