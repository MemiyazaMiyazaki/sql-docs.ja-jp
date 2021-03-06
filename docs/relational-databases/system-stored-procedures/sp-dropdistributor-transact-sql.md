---
title: sp_dropdistributor (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_dropdistributor
- sp_dropdistributor_TSQL
helpviewer_keywords:
- sp_dropdistributor
ms.assetid: 0644032f-5ff0-4718-8dde-321bc9967a03
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 55ebb2b9c42c0690bcffe409cbc6a5bf5bf68fc0
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82830154"
---
# <a name="sp_dropdistributor-transact-sql"></a>sp_dropdistributor (Transact-SQL)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

  ディストリビューターをアンインストールします。 このストアドプロシージャは、ディストリビューター側のディストリビューションデータベース以外の任意のデータベースで実行されます。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_dropdistributor [ [ @no_checks= ] no_checks ]   
    [ , [ @ignore_distributor= ] ignore_distributor ]  
```  
  
## <a name="arguments"></a>引数  
`[ @no_checks = ] no_checks`ディストリビューターを削除する前に依存オブジェクトを確認するかどうかを示します。 *no_checks*は**ビット**,、既定値は0です。  
  
 **0**の場合、 **sp_dropdistributor**によって、ディストリビューターに加えて、すべてのパブリッシングおよびディストリビューションオブジェクトが削除されていることを確認します。  
  
 **1**の場合、 **sp_dropdistributor**ディストリビューターをアンインストールする前に、すべてのパブリッシングオブジェクトおよびディストリビューションオブジェクトを削除します。  
  
`[ @ignore_distributor = ] ignore_distributor`ディストリビューターに接続せずにこのストアドプロシージャを実行するかどうかを示します。 *ignore_distributor*は**ビット**,、既定値は**0**です。  
  
 **0**の場合、 **sp_dropdistributor**はディストリビューターに接続し、すべてのレプリケーションオブジェクトを削除します。 **Sp_dropdistributor**がディストリビューターに接続できない場合、ストアドプロシージャは失敗します。  
  
 **1**の場合、ディストリビューターへの接続は確立されず、レプリケーションオブジェクトは削除されません。 これは、ディストリビューターがアンインストールされているか、完全にオフラインになっている場合に使用されます。 ディストリビューターでのこのパブリッシャーのオブジェクトは、ディストリビューターが将来の時刻に再インストールされるまで削除されません。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="remarks"></a>解説  
 **sp_dropdistributor**は、すべての種類のレプリケーションで使用されます。  
  
 他のパブリッシャーまたは配布オブジェクトがサーバーに存在する場合、 ** \@ no_checks**が**1**に設定されていないと**sp_dropdistributor**は失敗します。  
  
 このストアドプロシージャは、 **sp_dropdistributiondb**を実行してディストリビューションデータベースを削除した後に実行する必要があります。  
  
## <a name="example"></a>例  
 [!code-sql[HowTo#sp_DropDistPub](../../relational-databases/replication/codesnippet/tsql/sp-dropdistributor-trans_1.sql)]  
  
## <a name="permissions"></a>アクセス許可  
 **Sp_dropdistributor**を実行できるのは、 **sysadmin**固定サーバーロールのメンバーだけです。  
  
## <a name="see-also"></a>参照  
 [パブリッシングおよびディストリビューションを無効にする](../../relational-databases/replication/disable-publishing-and-distribution.md)   
 [sp_adddistributor &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-adddistributor-transact-sql.md)   
 [sp_changedistributor_property &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql.md)   
 [sp_helpdistributor &#40;Transact-sql&#41;](../../relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql.md)   
 [レプリケーション ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
