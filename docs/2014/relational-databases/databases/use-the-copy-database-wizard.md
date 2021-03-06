---
title: データベース コピー ウィザードの使用 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.cdw.transfermethod.f1
- sql12.swb.cdw.welcome.f1
- sql12.swb.cdw.packageconfiguration.f1
- sql12.swb.cdw.schedule.f1
- sql12.swb.cdw.destination.f1
- sql12.swb.cdw.complete.f1
- sql12.swb.cdw.destinationconfiguration.f1
- sql12.swb.cdw.selectdatabaseobjects.f1
- sql12.swb.cdw.databases.f1
- sql12.swb.cdw.source.f1
- sql12.swb.cdw.locationofsourcedbfiles.f1
helpviewer_keywords:
- Copy Database Wizard
- starting Copy Database Wizard
ms.assetid: 7a999fc7-0a26-4a0d-9eeb-db6fc794f3cb
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e72b960db0fd5b733119cafeca98f124eaa15f38
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62871139"
---
# <a name="use-the-copy-database-wizard"></a>データベース コピー ウィザードの使用
  データベース コピー ウィザードを使用すると、サーバーを停止することなく、データベースとそのオブジェクトをサーバー間で簡単にコピーできます。 また、以前の [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] バージョンから [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]にデータベースをアップグレードすることもできます。 このウィザードを使用すると、次の操作を実行できます。  
  
-   移動元またはコピー元、および移動先またはコピー先サーバーを選択します。  
  
-   移動、コピー、またはアップグレードするデータベースを選択します。  
  
-   データベースのファイルの場所を指定します。  
  
-   移動先またはコピー先サーバー上にログインを作成します。  
  
-   追加のサポート オブジェクト、ジョブ、ユーザー定義のストアド プロシージャ、およびエラー メッセージをコピーします。  
  
-   データベースを移動またはコピーする時期をスケジュールします。  
  
 データベース以外にも、関連したメタデータ (コピーしたデータベースに必要な **master** データベースのログインやオブジェクトなど) をコピーできます。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [前提条件](#Prerequisites)  
  
     [Recommendations (推奨事項)](#Recommendations)  
  
     [Security](#Security)  
  
-   **データベース コピー ウィザードを使用して以下のことを行うには:**  
  
     [データベースのコピー、移動、またはアップグレード](#Copy_Move)  
  
-   **補足情報 (アップグレード後):**  
  
     [SQL Server データベースのアップグレード後](#FollowUp)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> 制限事項と制約事項  
  
-   データベース コピー ウィザードは、Express Edition では使用できません。  
  
-   データベース コピー ウィザードを使用して、次のデータベースをコピーしたり移動したりすることはできません。  
  
    -   システム データベース  
  
    -   データベースはレプリケーション用に設定されています。  
  
    -   アクセス不可、読み込み中、オフライン、復旧中、未確認、または緊急モードのマークが付いたデータベース  
  
-   データベースをアップグレードした後、以前のバージョンにダウングレードすることはできません。  
  
-   **[移動]** オプションを選択した場合、データベースを移動した後で、コピー元データベースが自動的に削除されます。 **[コピー]** オプションを選択した場合は、コピー元データベースが削除されません。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 管理オブジェクトの方法を使用してフルテキスト カタログを移動する場合は、移動後にインデックスを再作成する必要があります。  
  
-   デタッチ後にアタッチする方法では、データベースをデタッチして、データベースの .mdf、.ndf、.ldf ファイルを移動するかコピーして、新しい場所でデータベースをもう一度アタッチします。 デタッチおよびアタッチによる方法でデータの損失や不整合を避けるため、移動またはコピーするデータベースにアクティブなセッションをアタッチすることはできません。 アクティブなセッションが存在する場合、データベース コピー ウィザードでは、移動またはコピー操作は実行されません。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 管理オブジェクトの方法では、データベースがオフラインになることがないため、アクティブなセッションが許可されています。  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> 前提条件  
 移動先またはコピー先のサーバーで SQL Server エージェントが起動されていることを確認します。  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> 推奨事項  
  
-   アップグレードしたデータベースのパフォーマンスを最適化するには、アップグレードしたデータベースに対して sp_updatestats (統計の更新) を実行します。  
  
-   データベースを別のサーバー インスタンスにコピーするときは、ユーザーおよびアプリケーションに一貫した使用環境を提供するために、アタッチ先のサーバー インスタンスで、ログインやジョブなどのデータベースのメタデータの一部またはすべてを作成し直す必要が生じる場合があります。 詳細については、「[データベースを別のサーバーインスタンスで使用できるようにするときのメタデータの管理 &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md)」を参照してください。  
  
###  <a name="security"></a><a name="Security"></a> セキュリティ  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 コピー元または移動元とコピー先または移動先の両方のサーバーにおいて **sysadmin** 固定サーバー ロールのメンバーである必要があります。  
  
##  <a name="copy-move-or-upgrade-databases"></a><a name="Copy_Move"></a>データベースのコピー、移動、またはアップグレード  
  
1.  のオブジェクトエクスプローラーで、[**データベース**] を展開し、データベースを右クリックして [**タスク**] をポイントし、[データベースのコピー] をクリックします。 **Copy Database** [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
2.  **[転送元サーバーの選択]** ページで、移動またはコピーするデータベースがあるサーバーの指定や、ログイン情報の入力を行います。 認証方法を選択し、ログイン情報を入力したら、 **[次へ]** をクリックして転送元サーバーとの接続を確立します。 セッションの間、この接続は開いています。  
  
     **移行元サーバー**  
     移動またはコピーするデータベースが配置されているサーバーの名前を選択するか、参照ボタン ([.**.**.]) をクリックして目的のサーバーを指定します。 サーバーは、 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]以上である必要があります。  
  
     **Windows 認証を使用する**  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ユーザー アカウントを使用して接続することをユーザーに許可します。  
  
     **SQL Server 認証を使用する**  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証用のユーザー名とパスワードを入力して接続することをユーザーに許可します。  
  
     **ユーザー名**  
     接続に使用するユーザー名を入力します。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証による接続が選ばれている場合にのみ利用できます。  
  
     **パスワード**  
     ログインのパスワードを入力します。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証を使用した接続が指定されている場合にのみ使用できます。  
  
     **次へ**  
     サーバーに接続し、ユーザーを検証します。 このプロセスでは、選択したコンピューター上でユーザーが固定サーバー ロール **sysadmin** のメンバーであるかどうかを確認します。  
  
3.  **[転送先サーバーの選択]** ページで、データベースが移動またはコピーされるサーバーを指定します。 転送先またはコピー先のサーバーと、転送元またはコピー元のサーバーに同じサーバー インスタンスを設定した場合、データベースのコピーが作成されます。 この場合、後でウィザードでデータベースの名前を変更する必要があります。 コピー元または移動元データベースの名前をコピー先または移動先データベースの名前に使用できるのは、コピー先または移動先サーバーに名前の競合がない場合のみです。 名前が競合する場合、コピー元または移動元のデータベース名を使用する前にコピー先または移動先サーバーの競合を手動で解決する必要があります。  
  
     **[転送先サーバー]**  
     データベースまたはデータベースを移動またはコピーするサーバーの名前を選択するか、参照ボタン ([.**.**.]) をクリックして移行先サーバーを指定します。  
  
    > [!NOTE]  
    >  転送先またはコピー先のサーバーとして、クラスター化されたサーバーを選択できます。その場合、データベース コピー ウィザードは、そのクラスター化された転送先またはコピー先のサーバーの共有ドライブのみが選択されていることを確認します。  
  
     **Windows 認証を使用する**  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ユーザー アカウントを使用して接続することをユーザーに許可します。  
  
     **SQL Server 認証を使用する**  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証用のユーザー名とパスワードを入力して接続することをユーザーに許可します。  
  
     **ユーザー名**  
     接続に使用するユーザー名を入力します。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証を選択した場合にのみ使用できます。  
  
     **パスワード**  
     ログインのパスワードを入力します。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 認証を選択した場合にのみ使用できます。  
  
     **次へ**  
     サーバーに接続し、ユーザーを検証します。 このプロセスでは、選択したコンピューター上でユーザーが上記の権限を所有しているかどうかを確認します。  
  
4.  **[転送方法の選択]** ページで転送方法を選択します。  
  
     **[デタッチ後にアタッチする方法を使用する]**  
     コピー元サーバーのデータベースをデタッチし、データベース ファイル (.mdf、.ndf、.ldf) をコピー先サーバーにコピーした後、データベースをコピー先サーバーにアタッチします。 主な処理はコピー元ディスクを読み取り、コピー先ディスクに書き込むだけなので、通常は高速に処理されます。 データベース内にオブジェクトを作成したり、データ ストレージ構造体を作成したりするために必要な [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ロジックは不要です。 ただし、データベースに割り当て済みの未使用の領域が多量にある場合は、この方法では時間がかかる場合があります。 たとえば、100 MB の割り当てで新しく作成された事実上空のデータベースの場合、5 MB のみが使用されているだけでも、全 100 MB がコピーされます。  
  
    > [!NOTE]  
    >  この方法の場合、転送中はユーザーがデータベースを使用できなくなります。  
  
     **[失敗した場合にソース データベースを再アタッチする]**  
     データベースのコピー時には、元のデータベース ファイルが必ずコピー元サーバーに再アタッチされます。 データベースの移動を完了できない場合に元のファイルをソース データベースに再アタッチするには、このチェック ボックスをオンにします。  
  
     **[SQL 管理オブジェクトの方法を使用する]**  
     コピー元データベースの各データベース オブジェクトの定義を読み取って、コピー先データベースに各オブジェクトを作成します。 その後、コピー元テーブルのデータをコピー先テーブルに転送し、インデックスとメタデータを再作成します。  
  
    > [!NOTE]  
    >  データベース ユーザーは転送中もデータベースにアクセスできます。  
  
5.  **[データベースの選択]** ページで、サーバーからサーバーへ移動またはコピーする 1 つ以上のデータベースを選択します。 このトピックの「開始する前に」セクションの「[制限事項と制約](#Restrictions)事項」を参照してください。  
  
     **合わせ**  
     データベースが移動先サーバーに移動されます。  
  
     **コピー**  
     データベースがコピー先サーバーにコピーされます。  
  
     **ソース**  
     移動またはコピー元のサーバーに存在するデータベースが表示されます。  
  
     **状態**  
     データベースを移動できる場合は、 **[OK]** が表示されます。 データベースを移動できない場合はその理由が表示されます。  
  
     **更新**  
     データベースの一覧が更新されます。  
  
     **次へ**  
     検証プロセスが開始され、次の画面が表示されます。  
  
6.  **[転送先データベースの構成]** ページで、データベース名を必要に応じて変更し、データベース ファイルの場所と名前を指定します。 このページは、移動またはコピーするデータベースごとに一度表示されます。  
  
7.  **[データベース オブジェクトの選択]** ページで、移動操作またはコピー操作の対象となるオブジェクトを選択します。 このページは、移動元のサーバーと移動先のサーバーが異なる場合にのみ使用できます。 オブジェクトを操作の対象にするには、 **[使用可能な関連オブジェクト]** ボックスでオブジェクト名をクリックした後、 **>>** ボタンをクリックして **[選択した関連オブジェクト]** ボックスにオブジェクトを移動します。 オブジェクトを除外するには、[**選択した関連オブジェクト**] ボックスでオブジェクト名をクリック** < **し、ボタンをクリックして [**使用可能な関連オブジェクト**] ボックスにオブジェクトを移動します。 既定では、選択したそれぞれの種類のオブジェクトがすべて転送されます。 特定の種類のオブジェクトを個別に選択するには、 **[選択した関連オブジェクト]** ボックスの横にある参照ボタンをクリックします。 ここで開くダイアログ ボックスを使用して、オブジェクトを個別に選択できます。  
  
     **[ログイン] (実行時のすべてのログイン)**  
     移動またはコピー操作でのログインが含まれます。 既定で選択されています。  
  
     **[master データベースからのストアド プロシージャ]**  
     移動操作またはコピー操作で、 **master**データベースのストアドプロシージャを含めます。  
  
    > [!NOTE]  
    >  拡張ストアド プロシージャおよび関連する DLL は、自動コピーの対象になりません。  
  
     **SQL Server エージェント ジョブ**  
     移動操作またはコピー操作で**msdb**データベースからのジョブを含めます。  
  
     **ユーザー定義エラーメッセージ**  
     ユーザー定義のエラー メッセージを移動またはコピー操作の対象にします。  
  
     **エンドポイント**  
     ソース データベースに定義されているエンドポイントを対象にします。  
  
     **フルテキストカタログ**  
     ソース データベースのフルテキスト カタログを対象にします。  
  
     **SSIS パッケージ**  
     ソース データベースに定義されている [!INCLUDE[ssIS](../../includes/ssis-md.md)] パッケージを対象にします。  
  
     **説明**  
     オブジェクトの説明。  
  
8.  **[転送元のデータベース ファイルの場所]** ページで、転送元サーバー上のデータベース ファイルが格納されているファイル システム共有を指定します。 転送元と転送先のサーバー インスタンスが異なるコンピューター上に存在する場合、この設定は必須です。  
  
     **[データベース]**  
     移動される各データベースの名前を表示します。  
  
     **[フォルダーの場所]**  
     ファイル システム上にあるソース データベース ファイルの場所を指定します。  
  
     例 : C:\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\DATA  
  
     **[転送元のサーバーでのファイル共有]**  
     ソース データベース ファイルの場所をファイル共有のパスとして指定します。  
  
     例: "\\\\*server_name*\c $ Server\MSSQL110." SQLMSSQLSERVER\MSSQL\Data  
  
9. データベースを転送するための [!INCLUDE[ssIS](../../includes/ssis-md.md)] パッケージがデータベース コピー ウィザードによって作成されます。 **[パッケージの構成]** ページで、適宜パッケージをカスタマイズしてください。  
  
     **[パッケージの場所]**  
     [!INCLUDE[ssIS](../../includes/ssis-md.md)] パッケージを書き込む場所が表示されます。  
  
     **パッケージ名**  
     [!INCLUDE[ssIS](../../includes/ssis-md.md)] パッケージの名前を入力します。  
  
     **[ログ オプション]**  
     ログ情報を Windows イベント ログとして保存するか、テキスト ファイルとして保存するかを選択します。  
  
     **[エラー ログ ファイルのパス]**  
     ログ ファイルの場所のパスを指定します。 このオプションは、テキスト ファイルのログのオプションが選択されている場合のみ使用できます。  
  
10. **[パッケージのスケジュール設定]** ページで、移動操作またはコピー操作をいつ開始するのかを指定します。 システム管理者でない場合は、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SSIS) パッケージ実行サブシステムへのアクセス権がある [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] エージェント プロキシ アカウントを指定する必要があります。  
  
     **[すぐに実行する]**  
     [**次へ**] をクリックした後、移動またはコピー操作を開始します。  
  
     **スケジュール**  
     移動操作またはコピー操作を後で開始します。 説明ボックスには、現在のスケジュール設定が表示されます。 スケジュールを変更するには、 **[変更]** をクリックします。  
  
     **変更**  
     [**新しいジョブスケジュール**] ダイアログボックスを開きます。  
  
     **[Integration Services プロキシ アカウント]**  
     利用可能なプロキシ アカウントを選択します。 転送をスケジュールするには、1 つ以上のプロキシ アカウントをユーザーが使用できる状態であり、SQL Server Integration Services パッケージ実行用サブシステムに対する権限がこれらのアカウントに対して構成されている必要があります。 ****  
  
     パッケージ実行用[!INCLUDE[ssIS](../../includes/ssis-md.md)]のプロキシアカウントを作成するには、オブジェクトエクスプローラーで [ **SQL Server エージェント**] を展開し、[**プロキシ**] を展開します。次に、[ **SSIS パッケージ実行**] を右クリックし、[**新しいプロキシ**] をクリックします。  
  
     **sysadmin** 固定サーバー ロールのメンバーは、必要なアクセス許可のある **SQL Server エージェント サービス アカウント**を選択できます。  
  
11. **[ウィザードの完了]** ページで、選択したオプションの概要を確認します。 オプションを変更するには、 **[戻る]** をクリックします。 **[完了]** をクリックして、データベースを作成します。 転送中は、 **データベース コピー ウィザード** の実行に関する状態情報が **[操作を実行しています]** ページに表示されます。  
  
     **操作**  
     実行されている各アクションが一覧表示されます。  
  
     **状態**  
     アクションが全体として成功したか、失敗したかを示します。  
  
     **メッセージ**  
     各ステップで返されるメッセージが表示されます。  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> 補足情報: SQL Server データベースのアップグレード後  
 データベース コピー ウィザードを使用して、以前のバージョンの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] データベースを [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]のバージョンにアップグレードした後は、データベースが直ちに使用可能となり、自動的にアップグレードされます。 データベースにフルテキスト インデックスがある場合、アップグレード プロセスでは、 **"フルテキスト アップグレード オプション"** サーバー プロパティの設定に応じて、インポート、リセット、または再構築が行われます。 アップグレード オプションが **[インポート]** または **[再構築]** に設定されている場合、アップグレード中はフルテキスト インデックスを使用できなくなります。 インデックスを作成するデータ量によって、インポートには数時間、再構築には最大でその 10 倍の時間がかかることがあります。 また、アップグレードオプションが [**インポート**] に設定されている場合、フルテキストカタログが使用できない場合は、関連付けられているフルテキストインデックスが再構築されることにも注意してください。 **フルテキスト アップグレード オプション** プロパティの設定の表示と変更については、「 [サーバー インスタンスでのフルテキスト検索の管理と監視](../search/manage-and-monitor-full-text-search-for-a-server-instance.md)」を参照してください。  
  
 アップグレード前のユーザー データベースの互換性レベルが 100 以上の場合は、アップグレード後も互換性レベルは変わりません。 アップグレードされたデータベースの互換性レベルが 90 の場合、互換性レベルは 100 に設定されます。これは、 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]でサポートされている下限の互換性レベルです。 詳細については、「[ALTER DATABASE 互換性レベル &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [デタッチとアタッチを使用してデータベースをアップグレードする &#40;Transact-sql&#41;](upgrade-a-database-using-detach-and-attach-transact-sql.md)   
 [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md)  
  
  
