---
title: SQL Server エージェントのマスター ジョブのスケジューリングの詳細の変更 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 01f9e53c4ae42f981b1b579294954a965ef8c376
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "63140695"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a>Change the Scheduling Details for a SQL Server Agent Master Job
  このトピックでは、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] または [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] を使用して、 [!INCLUDE[tsql](../../includes/tsql-md.md)]でジョブ定義のスケジューリングの詳細を変更する方法について説明します。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [セキュリティ](#Security)  
  
-   **以下を使用してジョブ定義のスケジューリングの詳細を変更するには:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> 制限事項と制約事項  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのマスター ジョブの対象サーバーを、ローカル サーバーとリモート サーバーの両方に設定することはできません。  
  
###  <a name="security"></a><a name="Security"></a> セキュリティ  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 **sysadmin** 固定サーバー ロールのメンバー以外は、所有しているジョブしか変更できません。 詳細については、「 [SQL Server エージェントのセキュリティの実装](implement-sql-server-agent-security.md)」をご覧ください。  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a>ジョブ定義のスケジューリングの詳細を変更するには  
  
1.  **オブジェクト エクスプローラー** で、スケジュールを編集するジョブを含むサーバーをプラス記号をクリックして展開します。  
  
2.  プラス記号をクリックして **[SQL Server エージェント]** を展開します。  
  
3.  プラス記号をクリックして **[ジョブ]** フォルダーを展開します。  
  
4.  スケジュールを編集するジョブを右クリックして、 **[プロパティ]** をクリックします。  
  
5.  [**ジョブのプロパティ-**_job_name_ ] ダイアログボックスの [**ページの選択**] で、[**スケジュール**] を選択します。 このページで使用可能なオプションの詳細については、「[ジョブのプロパティ: [新しいジョブ &#40;スケジュール] ページ&#41;](job-properties-new-job-schedules-page.md)」を参照してください。  
  
6.  完了したら、[**OK**] をクリックします。  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a>ジョブ定義のスケジューリングの詳細を変更するには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDE](../../includes/ssde-md.md)]のインスタンスに接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 詳細については、「 [sp_update_schedule &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql)」を参照してください。  
  
  
