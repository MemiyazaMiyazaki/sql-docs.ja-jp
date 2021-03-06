---
title: SQL Server エージェント サービスの SQL Server 接続を設定する
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
author: markingmyname
ms.author: maghan
ms.manager: jroth
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 01/19/2017
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: d7ed666a2190eeaf55e2f7fcd387cac91e33ca48
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "75245870"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service"></a>SQL Server エージェント サービスの SQL Server 接続を設定する

[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) では現在、すべてではありませんがほとんどの SQL Server エージェントの機能がサポートされています。 詳細については、「[Azure SQL Database Managed Instance と SQL Server の T-SQL の相違点](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)」を参照してください。

このトピックでは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] で [!INCLUDE[ssDE](../../includes/ssde_md.md)] を使用して、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] エージェントと [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]間の接続を設定する方法について説明します。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービスでは、Windows 認証を使用して、SQL Server のローカル インスタンスに接続できます。  
  
## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>はじめに  
  
### <a name="limitations-and-restrictions"></a><a name="Restrictions"></a>制限事項と制約事項  
  
-   オブジェクト エクスプローラーに [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント ノードが表示されるのは、このノードの使用権限がある場合に限られます。  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]以降は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証がサポートされません。 このオプションは、以前のバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]を管理している場合にのみ使用できます。  
  
### <a name="security"></a><a name="Security"></a>セキュリティ  
  
#### <a name="permissions"></a><a name="Permissions"></a>アクセス許可  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントの機能を実行するには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]固定サーバー ロールの **sysadmin** のメンバーであるアカウントの資格情報を使用するように構成する必要があります。 このアカウントには、次の Windows 権限が必要です。  
  
-   サービスとしてログオン (SeServiceLogonRight)  
  
-   プロセス レベル トークンを置き換える (SeAssignPrimaryTokenPrivilege)  
  
-   スキャン チェックを行わない (SeChangeNotifyPrivilege)  
  
-   プロセスに対してメモリ クォータを調整する (SeIncreaseQuotaPrivilege)  
  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント サービス アカウントに必要な Windows 権限の詳細については、「 [SQL Server エージェント サービスのアカウントの選択](../../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) 」および「 [Windows サービス アカウントと権限の構成](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)」を参照してください。  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a>SQL Server Management Studio の使用  
  
#### <a name="to-set-the-sql-server-connection"></a>SQL Server の接続を設定するには  
  
1.  **オブジェクト エクスプローラー**で、SQL Server エージェント サービスへの接続を設定するサーバーをプラス記号をクリックして展開します。  
  
2.  **[SQL Server エージェント]** を右クリックし、 **[プロパティ]** を選択します。  
  
3.  **[SQL Server エージェントのプロパティ]** ダイアログ ボックスの **[ページの選択]** で **[接続]** をクリックします。  
  
4.  **[SQL Server 接続]** で、 **[Windows 認証を使用する]** を選択して、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントが [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Windows 認証を使用して [!INCLUDE[ssDE](../../includes/ssde_md.md)] [!INCLUDE[msCoName](../../includes/msconame_md.md)] のインスタンスに接続できるようにします。 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 以降のデータベースへの接続には Windows 認証が必要です。  
  
