---
title: sp_delete_log_shipping_primary_secondary (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_delete_log_shipping_primary_secondary_TSQL
- sp_delete_log_shipping_primary_secondary
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_log_shipping_primary_secondary
ms.assetid: d6f71a12-f7b1-4a1c-9639-a533b8287b0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8276a23224495b7bcc69721fd5317d0b2b87821a
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68009170"
---
# <a name="sp_delete_log_shipping_primary_secondary-transact-sql"></a>sp_delete_log_shipping_primary_secondary (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  プライマリサーバー上のセカンダリデータベースのエントリを削除します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_delete_log_shipping_primary_secondary  
    [ @primary_database = ] 'primary_database',   
    [ @secondary_server = ] 'secondary_server',   
    [ @secondary_database = ] 'secondary_database'  
```  
  
## <a name="arguments"></a>引数  
`[ @primary_database = ] 'primary_database'`プライマリサーバー上のデータベースの名前を指定します。 *primary_database*は**sysname**であり、既定値はありません。  
  
`[ @secondary_server = ] 'secondary_server'`セカンダリサーバーの名前を指定します。 *secondary_server*は**sysname**であり、既定値はありません。  
  
`[ @secondary_database = ] 'secondary_database'`セカンダリデータベースの名前を指定します。 *secondary_database*は**sysname**であり、既定値はありません。  
  
## <a name="return-code-values"></a>リターン コードの値  
 0 (成功) または 1 (失敗)  
  
## <a name="result-sets"></a>結果セット  
 なし。  
  
## <a name="remarks"></a>Remarks  
 **sp_delete_log_shipping_primary_secondary**は、プライマリサーバーの**master**データベースから実行する必要があります。 このストアドプロシージャは、セカンダリデータベースのエントリをプライマリサーバーの**log_shipping_primary_secondaries**から削除します。  
  
## <a name="permissions"></a>アクセス許可  
 **sysadmin** 固定サーバー ロールのメンバーシップが必要です。  
  
## <a name="examples"></a>使用例  
 次の例では`sp_delete_log_shipping_primary_secondary` 、セカンダリデータベース`LogShipAdventureWorks`をセカンダリサーバー `FLATIRON`から削除するためにが使用されています。  
  
```  
EXEC master.dbo.sp_delete_log_shipping_primary_secondary  
@primary_database = N'AdventureWorks'  
,@secondary_server = N'FLATIRON'  
,@secondary_database = N'LogShipAdventureWorks';  
GO  
```  
  
## <a name="see-also"></a>参照  
 [ログ配布について &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
