---
title: sp_flush_log (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_flush_log_TSQL
- sys.sp_flush_log
- sys.sp_flush_log_TSQL
- sp_flush_log
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_flush_log
ms.assetid: 75cc9f52-3b1f-4754-b1e7-ce0dd3323bc9
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 61c4cceab6c816d63226216a54d4f647e92e592d
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68066685"
---
# <a name="syssp_flush_log-transact-sql"></a>sp_flush_log (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  現在のデータベースのトランザクション ログをディスクに書き出します。これによって、以前にコミットされた遅延持続性トランザクションがすべてメモリからディスクに書き込まれます。  
  
 性能上の理由から遅延トランザクション持続性の使用を選択したが、サーバーのクラッシュ時やフェールオーバー時に失われるデータの量に上限を設ける場合は、定期的に `sys.sp_flush_log` を実行します。 たとえば、x 秒を超えるデータが失われないようにする場合は、x 秒ごとに実行`sp_flush_log`します。  
  
 `sys.sp_flush_log` を実行すると、以前にコミットされた遅延持続性トランザクションがすべて持続可能な状態になることが保証されます。 詳細については、概念トピック「[トランザクションの持続性の制御](../../relational-databases/logs/control-transaction-durability.md)」を参照してください。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```sql  
  
sys.sp_flush_log  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 なし。  
  
## <a name="return-code-values"></a>リターン コードの値  
 リターンコード1は成功を示します。  それ以外の値は失敗を示します。  
  
## <a name="result-sets"></a>結果セット  
 なし。  
  
## <a name="sample-code"></a>サンプル コード  
  
```sql  
.  
EXECUTE sys.sp_flush_log  
  
```  
  
  
