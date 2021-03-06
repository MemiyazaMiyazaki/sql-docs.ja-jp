---
title: コレクション セット レポートの表示 (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 898dd309dae82818b60332b29c14f785c18b173b
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62873063"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a>コレクション セット レポートの表示 (SQL Server Management Studio)
  管理データ ウェアハウスを構成した後、コレクション セットのレポートを [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]で表示できます。 セットアップ中にインストールされるシステム データ コレクション セットについては、レポートが用意されています。 レポートには、次のものが含まれます。  
  
-   ディスク使用量の概要  
  
-   クエリ統計の履歴  
  
-   サーバーの利用状況の履歴  
  
 この手順では、 **[ディスク使用量]** コレクション セットのレポートを表示します。 同様の一般的な手順を使用して、他のシステム データ コレクション セットのレポートを表示できます。  
  
### <a name="to-view-a-collection-set-report"></a>コレクション セットのレポートを表示するには  
  
1.  レポートのテーブルは、収集したデータの初回アップロード時に作成されます。 この初回アップロード以前にレポートを表示しようとするとエラーが発生し、レポートは表示されません。 ディスク使用量コレクション セットのデータをアップロードするには、オブジェクト エクスプローラーで、 **[管理]** フォルダー、 **[データ コレクション]** 、 **[システム データ コレクション セット]** の順に展開し、 **[ディスク使用量]** コレクション セットを右クリックして、 **[今すぐ収集してアップロード]** をクリックします。  
  
2.  レポートを表示するには、オブジェクト エクスプローラーで、 **[管理]** フォルダーを展開し、 **[データ コレクション]** を右クリックします。次に、 **[レポート]** 、 **[管理データ ウェアハウス]** の順にポイントし、 **[ディスク使用量の概要]** をクリックします。  
  
    > [!NOTE]  
    >  一部のレポートでは、データ コレクション タイムラインの下にカレンダーのボタンが表示される場合があります。 このボタンをクリックして、 **データ コレクション レポート カレンダー**にアクセスします。  
  
#### <a name="data-collection-report-calendar"></a>データ コレクション レポート カレンダー  
 このダイアログ ボックスを使用すると、レポート対象にするデータの開始日、開始時刻、および実行時間を指定できます。 たとえば、先週の水曜日の特定の 12 時間におけるサーバーのディスク利用状況をレポート対象とすることができます。  
  
 **開始日**  
 レポート データの開始日を入力するか、カレンダーから開始日を選択します。  
  
 **[開始時刻]**  
 レポート データの開始時刻を入力するか、矢印をクリックして開始時刻を指定します。  
  
 **Duration**  
 レポートに含める時間範囲を指定します。 既定値は 240 分です。 選択できる値は、15 分、60 分、240 分 (4 時間)、720 分 (12 時間)、および 1440 分 (24 時間) です。  
  
## <a name="see-also"></a>参照  
 [[データ コレクション]](data-collection.md)   
 [Management Studio におけるカスタム レポート](../../ssms/object/custom-reports-in-management-studio.md)   
 [管理データ ウェアハウスの構成 &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
