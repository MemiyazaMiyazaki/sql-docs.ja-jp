---
title: sysmail_start_sp (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_start_sp
- sysmail_start_sp_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_start_sp
ms.assetid: 25fd7bb6-cfdd-463f-bea8-c6fcb805d3f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e15996a9db6e1b782875f2dd3d73d0e3e514c8f5
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68044442"
---
# <a name="sysmail_start_sp-transact-sql"></a>sysmail_start_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  外部プログラムが使用する[!INCLUDE[ssSB](../../includes/sssb-md.md)]オブジェクトを起動することによってデータベースメールを開始します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sysmail_start_sp  
```  
  
## <a name="arguments"></a>引数  
 None  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="result-sets"></a>結果セット  
 None  
  
## <a name="remarks"></a>Remarks  
 データベース メールは、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインストール時に有効化またはインストールされません。 データベース メール オブジェクトを有効化およびインストールするには、データベース メール構成ウィザードを使用します。  
  
 このストアドプロシージャは**msdb**データベースにあります。 このストアド プロシージャは、送信メッセージ要求を保持しているデータベース メール キューを開始し、外部プログラムに対する [!INCLUDE[ssSB](../../includes/sssb-md.md)] のアクティブ化を有効にします。  
  
 キューが開始されると、データベースメール外部プログラムはメッセージを処理できます。 このプロシージャを使用すると、 **sysmail_stop_sp**ストアドプロシージャを使用してキューを停止した後で、キューを再起動できます。  
  
> [!NOTE]  
>  このストアドプロシージャは、データベースメールのキューのみを開始します。 データベースでの [!INCLUDE[ssSB](../../includes/sssb-md.md)] のメッセージ配信はアクティブになりません。  
  
## <a name="permissions"></a>アクセス許可  
 このプロシージャの実行権限は、既定では**sysadmin**固定サーバーロールのメンバーに与えています。  
  
## <a name="examples"></a>使用例  
 次の例では、 **msdb**データベースのデータベースメールを開始します。 この例では、データベースメールが有効になっていることを前提としています。  
  
```  
USE msdb ;  
GO  
  
EXECUTE dbo.sysmail_start_sp ;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [データベース メール](../../relational-databases/database-mail/database-mail.md)   
 [データベースメール XPs サーバー構成オプション](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md)   
 [sysmail_stop_sp &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sysmail-stop-sp-transact-sql.md)   
 [Transact-sql&#41;&#40;のストアドプロシージャのデータベースメール](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
