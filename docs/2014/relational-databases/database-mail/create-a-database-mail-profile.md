---
title: データベース メール プロファイルの作成 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 55eab0bbfacdde17ff69dd36a0641561695bc14d
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62872208"
---
# <a name="create-a-database-mail-profile"></a>データベース メール プロファイルの作成
  **データベース メール構成ウィザード** または [!INCLUDE[tsql](../../includes/tsql-md.md)] を使用して、データベース メールのパブリック プロファイルとプライベート プロファイルを作成します。  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> 前提条件  
 プロファイルに対応する 1 つ以上のデータベース メール アカウントを作成します。 データベース メール アカウントの作成方法については、「 [データベース メール アカウントの作成](create-a-database-mail-account.md)」を参照してください。  
  
###  <a name="security"></a><a name="Security"></a> セキュリティ  
 パブリック プロファイルにより、 **msdb** データベースにアクセスできるすべてのユーザーが、このプロファイルを使用して電子メールを送信できます。 プライベート プロファイルを使用できるのは、ユーザーまたはロールです。 プロファイルにロールのアクセス権を付与すると、保守が簡単なアーキテクチャを作成できます。 メールを送信するには、 **msdb** データベースの **DatabaseMailUserRole** のメンバーであることに加えて、少なくとも 1 つのデータベース メール プロファイルへのアクセス許可が必要です。  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 プロファイル アカウントを作成し、ストアド プロシージャを実行するユーザーは、sysadmin 固定サーバー ロールのメンバーである必要があります。  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> データベース メール構成ウィザードの使用  
 **データベース メール プロファイルを作成するには**  
  
-   オブジェクト エクスプローラーで、データベース メールを構成する [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続し、サーバー ツリーを展開します。  
  
-   **[管理]** ノードを展開します。  
  
-   [データベース メール] をダブルクリックして、データベース メール構成ウィザードを開きます。  
  
-   [**構成タスクの選択**] ページで、[**データベースメールアカウントとプロファイルを管理**する] オプションを選択し、[**次へ**] をクリックします。  
  
-   **[プロファイルとアカウントの管理]** ページで、 **[新しいプロファイルを作成する]** オプションを選択し、 **[次へ]** をクリックします。  
  
-   **[新しいプロファイル]** ページで、プロファイル名と説明を指定し、プロファイルに含めるアカウントを追加して、**[次へ]** をクリックします。  
  
-   **[ウィザードの完了]** ページで、実行される動作を確認し、 **[完了]** をクリックして、新しいプロファイルの作成を完了します。  
  
-   **データベース メールのプライベート プロファイルを構成するには**  
  
    -   データベース メール構成ウィザードを開きます。  
  
    -   **[構成タスクの選択]** ページで、 **[データベース メール アカウントおよびプロファイルを管理する]** オプションを選択して、 **[次へ]** をクリックします。  
  
    -   **[プロファイルとアカウントの管理]** ページで、 **[プロファイル セキュリティの管理]** オプションを選択し、 **[次へ]** をクリックします。  
  
    -   **[プライベート プロファイル]** タブで、構成するプロファイルのチェック ボックスをオンにし、 **[次へ]** をクリックします。  
  
    -   **[ウィザードの完了]** ページで、実行される動作を確認し、 **[完了]** をクリックして、プロファイルの構成を完了します。  
  
-   **データベース メールのパブリック プロファイルを構成するには**  
  
    -   データベース メール構成ウィザードを開きます。  
  
    -   **[構成タスクの選択]** ページで、 **[データベース メール アカウントおよびプロファイルを管理する]** オプションを選択して、 **[次へ]** をクリックします。  
  
    -   **[プロファイルとアカウントの管理]** ページで、 **[プロファイル セキュリティの管理]** オプションを選択し、 **[次へ]** をクリックします。  
  
    -   **[パブリック プロファイル]** タブで、構成するプロファイルのチェック ボックスをオンにし、 **[次へ]** をクリックします。  
  
    -   **[ウィザードの完了]** ページで、実行される動作を確認し、 **[完了]** をクリックして、プロファイルの構成を完了します。  
  

  
## <a name="using-transact-sql"></a>Transact-SQL の使用  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a>データベースメールプライベートプロファイルを作成するには  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続します。  
  
-   新しいプロファイルを作成するには、システム ストアド プロシージャ [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.dbo.sysmail_add_profile_sp**  
  
     *@profile_name*= '*プロファイル名*'  
  
     *@description*= '*説明*'  
  
     *@profile_name*はプロファイル*@description*の名前です。はプロファイルの説明です。 このパラメーターは省略可能です。  
  
-   アカウントごとに、ストアド プロシージャ [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**  
  
     *@profile_name*= '*プロファイルの名前*'  
  
     *@account_name*= '*アカウントの名前*'  
  
     *@sequence_number*= '*プロファイル内のアカウントのシーケンス番号。* '  
  
     *@profile_name*はプロファイルの名前です。はプロファイルに*@account_name*追加するアカウントの名前です。は、 *@sequence_number*プロファイルでアカウントが使用される順序を決定します。  
  
-   このプロファイルを使用してメールを送信する各データベース ロールまたはユーザーについて、プロファイルへのアクセス権を付与します。 そのためには、ストアド プロシージャ [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.sysmail_add_principalprofile_sp**  
  
     *@profile_name*= '*プロファイルの名前*'  
  
     *@ principal_name* = '*Name of the database user or role*'  
  
     *@is_default*= '*既定のプロファイルの状態*'  
  
     *@profile_name*はプロファイル*@principal_name*の名前です。はデータベースユーザーまたはロールの名前です。は、 *@is_default*このプロファイルが、データベースユーザーまたはロールの既定のプロファイルであるかどうかを決定します。  
  
 次の例ではまず、データベース メール アカウントを作成し、データベース メールのプライベート プロファイルを作成します。その後、アカウントをプロファイルに追加し、そのプロファイルへのアクセス権を、 **msdb** データベースの **DBMailUsers** データベース ロールに与えます。  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a>データベースメールパブリックプロファイルを作成するには  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インスタンスに接続します。  
  
-   新しいプロファイルを作成するには、システム ストアド プロシージャ [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.dbo.sysmail_add_profile_sp**  
  
     *@profile_name*= '*プロファイル名*'  
  
     *@description*= '*説明*'  
  
     *@profile_name*はプロファイル*@description*の名前です。はプロファイルの説明です。 このパラメーターは省略可能です。  
  
-   アカウントごとに、ストアド プロシージャ [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**  
  
     *@profile_name*= '*プロファイルの名前*'  
  
     *@account_name*= '*アカウントの名前*'  
  
     *@sequence_number*= '*プロファイル内のアカウントのシーケンス番号。* '  
  
     *@profile_name*はプロファイルの名前です。はプロファイルに*@account_name*追加するアカウントの名前です。は、 *@sequence_number*プロファイルでアカウントが使用される順序を決定します。  
  
-   パブリック アクセス権を付与するには、ストアド プロシージャ [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) を次のように実行します。  
  
     **EXECUTEmsdb.sysmail_add_principalprofile_sp**  
  
     *@profile_name*= '*プロファイルの名前*'  
  
     *@ principal_name* = '**public** or **0**'  
  
     *@is_default*= '*既定のプロファイルの状態*'  
  
     *@profile_name*はプロファイル*@principal_name*の名前です。は、このプロファイルがパブリックプロファイルであることを*@is_default*示します。は、このプロファイルが、データベースユーザーまたはロールの既定のプロファイルであるかどうかを決定します。  
  
 次の例ではまず、データベース メール アカウントを作成し、データベース メールのプライベート プロファイルを作成します。その後、アカウントをプロファイルに追加し、そのプロファイルへのパブリック アクセス権を与えます。  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
