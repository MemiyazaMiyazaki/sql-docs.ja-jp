---
title: Oracle データの SQL Server への移行 (OracleToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Oracle Data Migration, Client-Side Migration
- Oracle Data Migration,Server-Side Migration
ms.assetid: e23c5268-41ed-4e55-9fe7-a11376202a13
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: c37f9c8e39a8a9dd87eabecba445b5ce7cef9028
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68264679"
---
# <a name="migrating-oracle-data-into-sql-server-oracletosql"></a>SQL Server (OracleToSQL) に Oracle のデータの移行
変換されたオブジェクトとを正常に[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]同期したら、データを Oracle から[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]に移行できます。  
  
> [!IMPORTANT]  
> 使用されているエンジンがサーバー側のデータ移行エンジンである場合は、データを移行する前に、ssma for Oracle 拡張パックと Oracle プロバイダーを SSMA を実行しているコンピューターにインストールする必要があります。 SQL Server エージェントサービスも実行されている必要があります。 拡張機能パックをインストールする方法の詳細については、「[サーバーコンポーネントのインストール」 (OracleToSQL)](https://msdn.microsoft.com/33070e5f-4e39-4b70-ae81-b8af6e4983c5)を参照してください。  
  
## <a name="setting-migration-options"></a>移行オプションの設定  
にデータを[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]移行する前に、[**プロジェクトの設定**] ダイアログボックスでプロジェクトの移行オプションを確認します。  
  
-   このダイアログボックスを使用すると、移行バッチサイズ、テーブルロック、制約チェック、null 値処理、id 値の処理などのオプションを設定できます。 プロジェクトの移行設定の詳細については、「[プロジェクトの設定 (移行)」 (OracleToSQL)](https://msdn.microsoft.com/fcd6b988-633b-4b2b-9f36-6368b5e86b60)を参照してください。  
  
-   [**プロジェクトの設定**] ダイアログボックスの**移行エンジン**を使用すると、ユーザーは2種類のデータ移行エンジンを使用して移行プロセスを実行できます。  
  
    1.  クライアント側のデータ移行エンジン  
  
    2.  サーバー側のデータ移行エンジン  
  
**クライアント側のデータ移行:**  
  
-   クライアント側でデータ移行を開始するには、[**プロジェクトの設定**] ダイアログボックスで [**クライアント側のデータ移行エンジン**] オプションを選択します。  
  
-   [**プロジェクトの設定**] で、[**クライアント側のデータ移行エンジン**] オプションが設定されています。  
  
    > [!NOTE]  
    > **クライアント側のデータ移行エンジン**は ssma アプリケーション内に存在するため、拡張パックの可用性には依存しません。  
  
**サーバー側のデータ移行:**  
  
-   サーバー側のデータ移行中に、エンジンはターゲットデータベースに配置されます。 拡張機能パックを使用してインストールされます。 拡張機能パックをインストールする方法の詳細については、「 [SQL Server でのサーバーコンポーネントのインストール](installing-ssma-components-on-sql-server-oracletosql.md)」を参照してください。  
  
-   サーバー側で移行を開始するには、[**プロジェクトの設定**] ダイアログボックスで [**サーバー側のデータ移行エンジン**] オプションを選択します。  
  
## <a name="migrating-data-to-sql-server"></a>SQL Server へのデータの移行  
データの移行は、Oracle テーブルからのデータ行をトランザクション内のテーブルに[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]移動する一括読み込み操作です。 各トランザクションでに[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]読み込まれる行の数は、プロジェクトの設定で構成されます。  
  
移行メッセージを表示するには、[出力] ウィンドウが表示されていることを確認します。 それ以外の場合は、[**表示**] メニューの [**出力**] を選択します。  
  
**データを移行するには**  
  
1.  次の点を確認します。  
  
    -   Oracle プロバイダーは、SSMA を実行しているコンピューターにインストールされます。  
  
    -   変換されたオブジェクトを[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]データベースと同期しました。  
  
2.  Oracle メタデータエクスプローラーで、移行するデータを含むオブジェクトを選択します。  
  
    -   すべてのスキーマのデータを移行するには、[**スキーマ**] の横にあるチェックボックスをオンにします。  
  
    -   データを移行するか、個々のテーブルを省略するには、まずスキーマを展開し、[**テーブル**] を展開して、テーブルの横にあるチェックボックスをオンまたはオフにします。  
  
3.  データを移行するには、次の2つのケースが発生します。  
  
    **クライアント側のデータ移行:**  
  
    -   **クライアント側のデータ移行**を実行するには、[**プロジェクトの設定**] ダイアログボックスで [**クライアント側のデータ移行エンジン**] オプションを選択します。  
  
    **サーバー側のデータ移行:**  
  
    -   サーバー側でデータ移行を実行する前に、次のことを確認してください。  
  
        1.  SSMA for Oracle 拡張パックは、の[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]インスタンスにインストールされます。  
  
        2.  SQL Server エージェントサービスは SQL Server のインスタンスで実行されています。  
  
    -   **サーバー側のデータ移行**を実行するには、[**プロジェクトの設定**] ダイアログボックスで [**サーバー側のデータ移行エンジン**] オプションを選択します。  
  
4.  Oracle メタデータエクスプローラーで [**スキーマ**] を右クリックし、[**データの移行**] をクリックします。 また、個々のオブジェクトまたはオブジェクトのカテゴリのデータを移行することもできます。オブジェクトまたはその親フォルダーを右クリックします。[**データの移行**] オプションを選択します。  
  
    > [!NOTE]  
    > SSMA for Oracle 拡張パックがの[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]インスタンスにインストールされておらず、**サーバー側のデータ移行エンジン**が選択されている場合、ターゲットデータベースにデータを移行しているときに、次のエラーが発生します: ' ssma データ移行コンポーネントが SQL Server に見つかりませんでした。サーバー側のデータ移行は実行できません。 拡張パックが正しくインストールされているかどうかを確認してください。 [**キャンセル**] をクリックして、データ移行を終了します。  
  
5.  [ **Oracle への接続**] ダイアログボックスで、接続の資格情報を入力し、[**接続**] をクリックします。 Oracle への接続の詳細については、「 [Connect To oracle &#40;OracleToSQL](../../ssma/oracle/connect-to-oracle-oracletosql.md) 」を参照してください&#41;  
  
    ターゲットデータベース[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]に接続するには、[ **SQL Server への接続**] ダイアログボックスに接続資格情報を入力し、[**接続**] をクリックします。 へ[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の接続の詳細については、「 [Connect to SQL Server](https://msdn.microsoft.com/bb8c4bde-cfc2-4636-92ae-5dd24abe9536) 」を参照してください。  
  
    メッセージが [**出力**] ウィンドウに表示されます。 移行が完了すると、**データ移行レポート**が表示されます。 データが移行されなかった場合は、エラーが含まれている行をクリックし、[**詳細**] をクリックします。 レポートの作成が完了したら、[**閉じる**] をクリックします。 データ移行レポートの詳細については、「[データ移行レポート (SSMA Common)](https://msdn.microsoft.com/bbfb9d88-5a98-4980-8d19-c5d78bd0d241) 」を参照してください。  
  
> [!NOTE]  
> ターゲットデータベースとして SQL Express edition を使用すると、クライアント側のデータの移行のみが許可され、サーバー側のデータ移行はサポートされません。  
  
## <a name="see-also"></a>参照  
[Oracle データベースの SQL Server &#40;OracleToSQL&#41;への移行](../../ssma/oracle/migrating-oracle-databases-to-sql-server-oracletosql.md)  
  
