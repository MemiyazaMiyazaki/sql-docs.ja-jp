---
title: レポート ページでの Tablix データ領域の表示の制御 | Microsoft Docs
ms.date: 03/07/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: f81c48cc-f038-4f57-988d-e9a3cbb46424
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e87bea9a9bd4807b1d91735cc5a620ac3242de73
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "65581526"
---
# <a name="controlling-the-tablix-data-region-display-on-a-report-page"></a>レポート ページでの Tablix データ領域の表示の制御
[!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] のページ分割されたレポートでテーブル、マトリックス、または一覧のデータ領域に設定して、レポートを表示するときのそれらの外観を変更できるプロパティについて説明します。  
   
## <a name="controlling-the-appearance-of-data"></a>データの外観の制御  
テーブル、マトリックス、および一覧のデータ領域はすべて、 *Tablix* データ領域の例です。 次の機能を使用して、Tablix データ領域の外観を制御できます。  
  
-   **データの書式設定:** テーブル、マトリックス、または一覧のデータを書式設定するには、セル内のテキスト ボックスの書式設定のプロパティを設定します。 複数のセルのプロパティを同時に設定できます。 グラフ内のデータを書式設定するには、系列の書式設定のプロパティを設定します。 詳細については、「[レポート アイテムの書式設定 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/formatting-report-items-report-builder-and-ssrs.md)」と「[グラフの書式設定 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)」を参照してください。  
  
-   **式を作成する。** 詳細については、「[レポートでの式の使用 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)」および「[式の例 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)」を参照してください。  
  
-   **並べ替え順序を制御する。** 並べ替え順序を制御するには、データ領域の並べ替え式を定義します。 グループに関連付けられている行と列の並べ替え順序を制御するには、グループ (詳細グループを含む) の並べ替え式を定義します。 ユーザーが Tablix データ領域またはそのグループを並べ替えることができるように対話的な並べ替えボタンを追加することもできます。 詳細については、「[データ領域内のデータの並べ替え &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/sort-data-in-a-data-region-report-builder-and-ssrs.md)」を参照してください。  
  
-   **データが存在しない場合にメッセージを表示する。** 実行時にレポート データセットのデータが存在しない場合、データ領域に代わりに表示する独自のメッセージを記述できます。 詳細については、「[データ領域にデータがないことを示すメッセージの設定 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-data/set-a-no-data-message-for-a-data-region-report-builder-and-ssrs.md)」を参照してください。  
  
-   **条件付きでデータを非表示にする。** データ領域全体またはその一部の表示と非表示を条件付きで制御するには、Hidden プロパティを **True** または式に設定します。 式には、レポート パラメーターへの参照を含めることができます。 詳細データを表示するかどうかをユーザーが決定できるように、切り替えアイテムを指定することもできます。 詳細については、「[ドリルダウン アクション &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/drilldown-action-report-builder-and-ssrs.md)」を参照してください。  
  
-   **セルを結合する。** テーブル内の複数の連続するセルを 1 つのセルに結合できます。 これは、列の結合またはセルの結合と呼ばれています。 セルは水平方向または垂直方向にのみ結合できます。 セルを結合する場合、最初のセルのデータのみが保持されます。 その他のセル内のデータは削除されます。 結合されたセルは、元の列に分割できます。 詳細については、「[データ領域内のセルの結合 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/merge-cells-in-a-data-region-report-builder-and-ssrs.md)」を参照してください。  
  
## <a name="controlling-tablix-data-region-position-and-expansion-on-a-page"></a>ページ上の Tablix データ領域の位置および拡張の制御  
 次の機能を使用して、表示されたレポートにおける Tablix データ領域の表示方法を制御できます。  
  
-   **その他のレポート アイテムに対する Tablix データ領域の位置を制御する。** Tablix データ領域は、レポート デザイン画面上のその他のレポート アイテムの上、横、または下に配置できます。 実行時に、Tablix データ領域は、リンクされたデータセット用に取得されたデータに応じて [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] によって拡張され、必要に応じてピア レポート アイテムが移動します。 Tablix を別のレポート アイテムの横に固定するには、レポート アイテムをピアとして設定して、それらの相対的位置を調整します。 詳しくは、「[レンダリングの動作 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/rendering-behaviors-report-builder-and-ssrs.md)」をご覧ください。  
  
-   **拡張方向を変更する。** Tablix データ領域がページの左から右 (LTR) に拡張するのか、右から左 (RTL) に拡張するのかを制御するには、[プロパティ] ウィンドウからアクセスできる Direction プロパティを使用します。 詳細については、「[データ領域の表示 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/rendering-data-regions-report-builder-and-ssrs.md)」を参照してください。  
  
## <a name="controlling-how-a-tablix-data-region-renders-on-a-page"></a>ページ上の Tablix データ領域の表示方法の制御  
 次の方法で、レポートにおける Tablix データ領域の表示方法を制御できます。  
  
-   **ページングを制御する。** 各レポート ページに表示されるデータの量を制御するには、データ領域で改ページを設定します。 改ページは、グループに対しても設定できます。 改ページを設定すると、各ページ上で処理する必要のあるデータの量が少なくなり、オンデマンド表示パフォーマンスに影響を与える場合があります。 詳細については、「[Reporting Services の改ページ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/pagination-in-reporting-services-report-builder-and-ssrs.md)」および「[改ページの追加 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/add-a-page-break-report-builder-and-ssrs.md)」を参照してください。  
  
-   **行ヘッダーの右側または左側にデータを表示する。** 行ヘッダーは Tablix データ領域の横以外にも表示できます。 行ヘッダーを列の間に移動して、データ列を行ヘッダーの前に表示することもできます。 そのためには、マトリックスの GroupsBeforeRowHeaders プロパティを変更します。 このプロパティは、[プロパティ] ウィンドウからアクセスできます。 このプロパティの値には、整数値を使用します。たとえば、この値に 2 を指定すると、行ヘッダーを含む列の前にデータ領域列データの 2 つのグループ インスタンスが表示されます。  
  
## <a name="controlling-how-tablix-row-and-column-groups-render"></a>Tablix の行グループおよび列グループの表示方法の制御  
 Tablix データ領域のグループの表示を制御する方法は、グループ構造によって異なります。 Tablix データ領域には、次の図に示すように 4 つの領域を含めることができます。  
  
 ![Tablix データ領域部分](../../reporting-services/report-design/media/rs-tablixareas.gif "Tablix データ領域部分")  
  
 行グループ領域と列グループ領域にはグループ ヘッダーがあります。 Tablix データ領域にグループ ヘッダーがある場合、 **[Tablix のプロパティ]** ダイアログ ボックスの **[全般]** ページのプロパティを設定することにより、行と列の繰り返し方法を制御します。  
  
 Tablix データ領域に Tablix 本体領域しかない場合、グループ ヘッダーはありません。 静的および動的な Tablix メンバーだけになります。 静的メンバーは、Tablix の行グループまたは列グループに対して 1 回表示されます。 動的メンバーは、一意のグループ値ごとに 1 回表示されます。 たとえば、販売注文を表示する Tablix データ領域の場合、販売注文の列名は静的行メンバーで表示できます。 販売注文の各行は、動的行メンバーで表示されます。  
  
 Tablix メンバーの表示方法は、プロパティ ペインでプロパティを設定することによって制御できます。 詳細については、「[グループ化ペイン &#40;レポート ビルダー&#41;](../../reporting-services/report-design/grouping-pane-report-builder.md)」の「詳細設定モード」を参照してください。  
  
 次の方法で、レポートにおける Tablix データ領域の表示方法を制御できます。  
  
-   **複数ページで行および列のヘッダーを繰り返して表示する。** Tablix データ領域にまたがる各ページに、行および列ヘッダーを表示できます。 詳細については、「[複数のページへの行および列ヘッダーの表示 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md)」を参照してください。  
  
-   **スクロール時に行および列ヘッダーを固定する。** ブラウザーを使用してレポートをスクロールする際に、ビューの行および列ヘッダーを固定するかどうかを制御できます。 詳細については、「[レポートのスクロール時にヘッダーを表示したままにする &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)」を参照してください。  
  
 別の形式にレポートをエクスポートすることが、ページ上の Tablix データ領域の表示に与える影響の詳細については、「[レンダリングの動作 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/rendering-behaviors-report-builder-and-ssrs.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [同じデータセットへの複数のデータ領域のリンク &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)   
 [入れ子になったデータ領域 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/nested-data-regions-report-builder-and-ssrs.md)   
 [合計、集計、および組み込みコレクションの式のスコープ &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/expression-scope-for-totals-aggregates-and-built-in-collections.md)   
 [改ページ、見出し、列、および行の制御 (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md)   
 [Tablix データ領域 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/tablix-data-region-report-builder-and-ssrs.md)   
 [テーブル &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/tables-report-builder-and-ssrs.md)   
 [マトリックスを作成する](../../reporting-services/report-design/create-a-matrix-report-builder-and-ssrs.md)   
 [一覧がある請求書とフォームを作成する](../../reporting-services/report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)   
 [テーブル、マトリックス、および一覧 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
