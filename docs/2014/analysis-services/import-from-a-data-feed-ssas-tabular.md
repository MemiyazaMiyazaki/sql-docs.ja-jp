---
title: データフィードからのインポート (SSAS テーブル) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0686e519-67c2-4f9b-8cd2-84a4871499ee
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: bcb3a1cbcabc66492bbd780be4716ce69f15de37
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "66080566"
---
# <a name="import-from-a-data-feed-ssas-tabular"></a>データ フィードからのインポート (SSAS テーブル)
  データ フィードは、オンライン データ ソースから生成され、宛先のドキュメントやアプリケーションに送信される 1 つ以上の XML データ ストリームです。 テーブルのインポート ウィザードを使用して、データ フィードからモデルにデータをインポートできます。  
  
 このトピックには、次のセクションが含まれます。  
  
-   [データ フィードからのインポートについて](#prereq)  
  
-   [Azure DataMarket データセットからのデータのインポート](#azure)  
  
-   [パブリックまたは企業データのソースからのデータ フィードのインポート](#importdata)  
  
-   [SharePoint リストからのデータ フィードのインポート](#importlist)  
  
-   [Reporting Services レポートからのデータ フィードのインポート](#importreport)  
  
##  <a name="understanding-import-from-a-data-feed"></a><a name="prereq"></a>データフィードからのインポートについて  
 次の種類のデータ フィードからテーブル モデルにデータをインポートできます。  
  
 **Reporting Services レポート**  
 モデル内のデータ ソースとして SharePoint サイトまたはレポート サーバーにパブリッシュされた Reporting Services レポートを使用できます。 Reporting Services レポートからデータをインポートするときは、データ ソースとしてレポート定義 (.rdl) ファイルを指定する必要があります。  
  
 **Azure DataMarket データセット**  
 Azure DataMarket は、クラウド サービスとして情報の 1 つのマーケットプレースと配信チャネルを提供するサービスです。 Azure DataMarket データセットでは、Windows ユーザー アカウントではなくアカウント キーが必要です。  
  
 **Atom フィード**  
 フィードは Atom フィードである必要があります。 RSS フィードはサポートされていません。 フィードが一般公開されているか、現在ログインしている Windows アカウントでそのフィードに接続するための権限を持っている必要があります。  
  
 インポート時に、データ フィードからのデータがモデルに 1 回追加されます。 フィードから更新済みデータを取得するには、モデル デザイナーからデータを更新するか、Analysis Services の実稼動インスタンスに配置後にモデルのデータ更新スケジュールを構成するかします。 詳細については、「 [データの処理 (SSAS テーブル)](process-data-ssas-tabular.md)」を参照してください。  
  
##  <a name="import-data-from-an-azure-datamarket-dataset"></a><a name="azure"></a>Azure DataMarket データセットからのデータのインポート  
 モデル内のテーブルとして Azure DataMarket からデータをインポートできます。  
  
#### <a name="to-import-data-from-an-azure-datamarket-dataset"></a>Azure DataMarket データセットからデータをインポートするには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]で **[モデル]** メニューをクリックし、 **[データ ソースからのインポート]** をクリックします。 テーブルのインポート ウィザードが表示されます。  
  
2.  **[データ ソースへの接続]** ページの **[データ フィード]** で、 **[Azure DataMarket データセット]** をクリックしてから **[次へ]** をクリックします。  
  
3.  **[表示名]** の **[Azure DataMarket データセットへの接続]** ページに、アクセスするフィードに付けるわかりやすい名前を入力します。 複数のフィードまたはデータ ソースをインポートする場合、接続を表す名前を使用すると、接続の使用方法の識別に役立ちます。  
  
4.  **[データ フィード URL]** にデータ フィードのアドレスを入力します。  
  
5.  **[アカウント キー]** の **[セキュリティ設定]** にアカウント キーを入力します。 アカウント キーは、Analysis Services が DataMarket サブスクリプションにアクセスするときに使用されます。  
  
6.  **[接続テスト]** をクリックして、フィードが使用可能であることを確認します。 または、 **[詳細設定]** をクリックして、ベース URL またはサービス ドキュメント URL に、フィードを提供するクエリまたはサービス ドキュメントが含まれていることを確認することもできます。  
  
7.  インポートを続行するには、 **[次へ]** をクリックします。  
  
8.  **[権限借用情報]** ページで、データを更新するときに Analysis Services がデータ ソースへの接続に使用する資格情報を指定し、 **[次へ]** をクリックします。 これらの資格情報はアカウント キーとは異なります。  
  
9. ウィザードの **[テーブルとビューの選択]** ページの **[表示名]** フィールドに、インポート後にこのデータを含むテーブルを識別するわかりやすい名前を入力します。  
  
10. **[プレビューとフィルター]** をクリックしてデータを確認し、列の選択を変更します。 レポートのデータ フィードでインポートされる行を制限することはできませんが、チェック ボックスをオフにすることで列を削除できます。 **[OK]** をクリックします。  
  
11. **[テーブルとビューの選択]** ページで、 **[完了]** をクリックします。  
  
##  <a name="import-data-feeds-from-public-or-corporate-data-sources"></a><a name="importdata"></a>パブリックまたは企業のデータソースからデータフィードをインポートする  
 パブリック フィードにアクセスするか、または専用または従来のデータベース システムから Atom フィードを生成するカスタム データ サービスを作成できます。  
  
#### <a name="to-import-data-from-public-or-corporate-data-feeds"></a>パブリックまたは企業データ フィードからデータをインポートするには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]で **[モデル]** メニューをクリックし、 **[データ ソースからのインポート]** をクリックします。 テーブルのインポート ウィザードが表示されます。  
  
2.  **[データ ソースへの接続]** ページの **[データ フィード]** で、 **[他のフィード]** をクリックしてから **[次へ]** をクリックします。  
  
3.  **[データ フィードへの接続]** ページに、アクセスするフィードに付けるわかりやすい名前を入力します。 複数のフィードまたはデータ ソースをインポートする場合、接続を表す名前を使用すると、接続の使用方法の識別に役立ちます。  
  
4.  **[データ フィード URL]** にデータ フィードのアドレスを入力します。 有効な値は次のとおりです。  
  
    1.  Atom データを含む XML ドキュメント。 たとえば、次の URL は Open Government Data Initiative Web サイトのパブリック フィードを指します。  
  
        ```  
        http://ogdi.cloudapp.net/v1/dc/banklocations/  
        ```  
  
    2.  1 つ以上のフィードを指定する .atomsvc ドキュメント。 .atomsvc ドキュメントは、1 つ以上のフィードを提供するサービスまたはアプリケーションを指します。 各フィードは、結果セットを返すベース クエリとして指定されます。  
  
         Web サーバー上の .atomsvc ドキュメントに対する URL アドレスを指定するか、またはコンピューター上の共有フォルダーまたはローカル フォルダーからファイルを開くことができます。 Reporting Services レポートをエクスポートしている間にコンピューターに保存した .atomsvc ドキュメント、または SharePoint サイトに対して作成されたデータ フィード ライブラリ内の .atomsvc ドキュメントが存在する可能性があります。  
  
        > [!NOTE]  
        >  URL アドレスまたは共有フォルダーを介してアクセスできる .atomsvc ドキュメントを指定することをお勧めします。これは、SharePoint へのブックのパブリッシュ後に、後でブックの自動データ更新を設定するオプションが提供されるためです。 コンピューター上のローカルな場所でない場所が指定されていれば、サーバーは、同じ URL アドレスまたはネットワーク フォルダーを再使用してデータを更新できます。  
  
5.  **[接続テスト]** をクリックして、フィードが使用可能であることを確認します。 または、 **[詳細設定]** をクリックして、ベース URL またはサービス ドキュメント URL に、フィードを提供するクエリまたはサービス ドキュメントが含まれていることを確認することもできます。  
  
6.  インポートを続行するには、 **[次へ]** をクリックします。  
  
7.  **[権限借用情報]** ページで、データを更新するときに Analysis Services がデータ ソースへの接続に使用する資格情報を指定し、 **[次へ]** をクリックします。  
  
8.  ウィザードの **[テーブルとビューの選択]** ページの **[表示名]** フィールドで、データ フィード コンテンツを、インポート後にこのデータが格納されるテーブルを表す名前に置き換えます。  
  
9. **[プレビューとフィルター]** をクリックしてデータを確認し、列の選択を変更します。 レポートのデータ フィードでインポートされる行を制限することはできませんが、チェック ボックスをオフにすることで列を削除できます。 **[OK]** をクリックします。  
  
10. **[テーブルとビューの選択]** ページで、 **[完了]** をクリックします。  
  
##  <a name="import-data-feeds-from-sharepoint-lists"></a><a name="importlist"></a>SharePoint リストからデータフィードをインポートする  
 (SharePoint) リボンに **[データ フィードとしてエクスポート]** ボタンを持つ SharePoint リストをインポートできます。 このボタンをクリックすると、リストをフィードとしてエクスポートできます。  
  
#### <a name="to-import-data-feeds-from-a-sharepoint-list"></a>SharePoint リストからデータ フィードをインポートするには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]で **[モデル]** メニューをクリックし、 **[データ ソースからのインポート]** をクリックします。  
  
2.  **[データ ソースへの接続]** ページの **[データ フィード]** で、 **[他のデータ フィード]** をクリックしてから **[次へ]** をクリックします。  
  
3.  **[データ フィードへの接続]** ページに、アクセスするフィードに付けるわかりやすい名前を入力します。 複数のフィードまたはデータ ソースをインポートする場合、接続を表す名前を使用すると、接続の使用方法の識別に役立ちます。  
  
4.  [データフィード URL] ボックスに、リストデータサービスのアドレスを入力\<します。次に、サーバー名> を実際の SharePoint サーバーの名前に置き換えます。  
  
    ```  
    http://<server-name>/_vti_bin/listdata.svc  
    ```  
  
5.  **[接続テスト]** をクリックして、フィードが使用可能であることを確認します。 または、 **[詳細設定]** をクリックして、サービス ドキュメント URL に、リスト データ サービスのアドレスが含まれていることを確認することもできます。  
  
6.  インポートを続行するには、 **[次へ]** をクリックします。  
  
7.  **[権限借用情報]** ページで、データを更新するときに Analysis Services がデータ ソースへの接続に使用する資格情報を指定し、 **[次へ]** をクリックします。  
  
8.  ウィザードの **[テーブルとビューの選択]** ページで、インポートするリストを選択します。  
  
    > [!NOTE]  
    >  列を含むリストのみをインポートできます。  
  
9. **[プレビューとフィルター]** をクリックしてデータを確認し、列の選択を変更します。 レポートのデータ フィードでインポートされる行を制限することはできませんが、チェック ボックスをオフにすることで列を削除できます。 **[OK]** をクリックします。  
  
10. **[テーブルとビューの選択]** ページで、 **[完了]** をクリックします。  
  
##  <a name="import-data-feeds-from-reporting-services-reports"></a><a name="importreport"></a>Reporting Services レポートからのデータフィードのインポート  
 [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Reporting Services を配置している場合は、Atom 表示拡張機能を使用して既存のレポートからデータ フィードを生成できます。  
  
#### <a name="to-import-report-data-from-a-published-reporting-services-report"></a>パブリッシュされた Reporting Services レポートからレポート データをインポートするには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]で **[モデル]** メニューをクリックし、 **[データ ソースからのインポート]** をクリックします。  
  
2.  **[データ ソースへの接続]** ページの **[データ フィード]** で、 **[レポート]** をクリックしてから **[次へ]** をクリックします。  
  
3.  [Microsoft SQL Server Reporting Services レポートへの接続] ページで、[接続の表示名] に、アクセスするフィードに付けるわかりやすい名前を入力します。 複数のデータ ソースをインポートする場合、接続を表す名前を使用すると、接続の使用方法の識別に役立ちます。  
  
4.  **[参照]** をクリックし、レポート サーバーを選択します。  
  
     特定のレポート サーバーに関するレポートを定期的に使用している場合は、 **[最近使ったサイトとサーバー]** にそのサーバーが表示される可能性があります。 それ以外の場合は、レポート サーバーのアドレスを [名前] に入力し、 **[開く]** をクリックして、レポート サーバー サイトのフォルダーを参照します。 レポートサーバーのアドレスの例としては\<、http://computername>/reportserverなどがあります。  
  
5.  レポートを選択し、**[開く]** をクリックします。 代わりに、 **[名前]** ボックスに完全パスとレポート名を含むレポートへのリンクを貼り付けることもできます。 テーブルのインポート ウィザードによってレポートに接続され、プレビュー領域にそれが表示されます。  
  
     レポートでパラメーターが使用されている場合は、パラメーターを指定しないとレポート接続を作成できません。 パラメーターを指定すると、そのパラメーター値に関連する行だけがデータ フィードでインポートされます。  
  
    1.  レポートのリスト ボックスまたはコンボ ボックスを使用してパラメーターを選択します。  
  
    2.  **[レポートの表示]** をクリックしてデータを更新します。  
  
        > [!NOTE]  
        >  レポートを表示すると、選択したパラメーターがデータ フィードの定義と共に保存されます。  
  
     必要に応じて **[詳細設定]** をクリックし、プロバイダー固有のプロパティを設定できます。  
  
6.  **[接続テスト]** をクリックして、レポートがデータ フィードとして使用可能であることを確認します。 または、 **[詳細設定]** をクリックして、データ フィード接続を指定する埋め込み XML が **[Inline Service Document]** プロパティに含まれていることを確認します。  
  
7.  インポートを続行するには、 **[次へ]** をクリックします。  
  
8.  **[権限借用情報]** ページで、データを更新するときに Analysis Services がデータ ソースへの接続に使用する資格情報を指定し、 **[次へ]** をクリックします。  
  
9. ウィザードの **[テーブルとビューの選択]** ページで、データとしてインポートするレポート パーツの横にあるチェック ボックスをオンにします。  
  
     レポートによっては、テーブル、一覧、グラフなど、複数のパーツが含まれていることがあります。  
  
10. **[表示名]** ボックスに、データ フィードを保存するモデルのテーブルの名前を入力します。  
  
     名前が割り当てられていない場合、既定では Reporting Services のコントロールの名前 (Tablix1、Tablix2 など) が使用されます。 インポートされたデータ フィードのソースを簡単に識別できるように、インポート時にこの名前を変更することをお勧めします。  
  
11. **[プレビューとフィルター]** をクリックしてデータを確認し、列の選択を変更します。 レポートのデータ フィードでインポートされる行を制限することはできませんが、チェック ボックスをオフにすることで列を削除できます。 **[OK]** をクリックします。  
  
12. **[テーブルとビューの選択]** ページで、 **[完了]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [SSAS 表形式&#41;&#40;サポートされるデータソース](tabular-models/data-sources-supported-ssas-tabular.md)   
 [SSAS 表形式&#41;&#40;サポートされているデータ型](tabular-models/data-types-supported-ssas-tabular.md)   
 [SSAS の &#40;の権限借用表形式&#41;](tabular-models/impersonation-ssas-tabular.md)   
 [SSAS 表形式&#41;&#40;データを処理する](process-data-ssas-tabular.md)   
 [データのインポート &#40;SSAS テーブル&#41;](import-data-ssas-tabular.md)  
  
  
