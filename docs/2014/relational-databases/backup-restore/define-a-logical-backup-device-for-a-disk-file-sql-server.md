---
title: ディスク ファイルの論理バックアップ デバイスの定義 (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 0ae32391bd2f10525b89015272d11bcdb6468298
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62877867"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a>ディスク ファイルの論理バックアップ デバイスの定義 (SQL Server)
  このトピックでは、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] または [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] を使用して、 [!INCLUDE[tsql](../../includes/tsql-md.md)]でディスク ファイルの論理バックアップ デバイスを定義する方法について説明します。 論理バックアップ デバイスとは、特定の物理バックアップ デバイス (ディスク ファイルまたはテープ ドライブ) を示すユーザー定義名です。  物理デバイスは、後で、つまりバックアップがバックアップ デバイスに書き込まれたときに初期化されます。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [Recommendations (推奨事項)](#Recommendations)  
  
     [セキュリティ](#Security)  
  
-   **ディスク ファイルの論理バックアップ デバイスを定義する方法:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> 制限事項と制約事項  
  
-   論理デバイス名は、サーバー インスタンス上のすべての論理バックアップ デバイスで一意になる必要があります。 既存の論理デバイス名を表示するには、 [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) カタログ ビューに対してクエリを実行します。  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> 推奨事項  
  
-   バックアップ ディスクには、データベースのデータ ディスクやログ ディスクとは別のディスクを使用することをお勧めします。 これは、データ ディスクやログ ディスクで障害が発生した場合に確実にバックアップにアクセスできるようにするために必要です。  
  
###  <a name="security"></a><a name="Security"></a> セキュリティ  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 **diskadmin** 固定サーバー ロールのメンバーシップが必要です。  
  
 ディスクに対する書き込み権限が必要です。  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a>ディスク ファイルの論理バックアップ デバイスを定義するには  
  
1.  オブジェクト エクスプローラーで適切な [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]のインスタンスに接続した後、サーバー名をクリックしてサーバー ツリーを展開します。  
  
2.  **[サーバー オブジェクト]** を展開し、 **[バックアップ デバイス]** を右クリックします。  
  
3.  **[新しいバックアップ デバイス]** をクリックします。 **[バックアップ デバイス]** ダイアログ ボックスが開きます。  
  
4.  デバイス名を入力します。  
  
5.  バックアップ先として、 **[ファイル]** をクリックし、ファイルの完全なパスを指定します。  
  
6.  新しいデバイスを定義するには、 **[OK]** をクリックします。  
  
 この新しいデバイスにバックアップするには、このデバイスを **[データベースのバックアップ]** ダイアログ ボックス ( **[全般]** ) の **[バックアップ先]** フィールドに追加します。 詳細については、「[データベースの完全バックアップの作成 &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md)」を参照してください。  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a>ディスク ファイルの論理バックアップを定義するには  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]に接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。 この例では、 [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) を使用して、ディスク ファイルの論理バックアップ デバイスを定義します。 この例では、 `mydiskdump`という物理名を持つ、 `c:\dump\dump1.bak`というディスク バックアップ デバイスを追加します。  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql)   
 [バックアップ デバイス &#40;SQL Server&#41;](backup-devices-sql-server.md)   
 [sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql)   
 [sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)   
 [sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql)   
 [テープ ドライブの論理バックアップ デバイスの定義 &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)   
 [論理バックアップ デバイスのプロパティと内容の表示 &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
