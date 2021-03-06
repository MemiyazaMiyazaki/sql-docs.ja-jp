---
title: '[SQL 変換先エディター] ([接続マネージャー] ページ) |Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: d3bffc98a14c1a8bc672e9f15a4bad8b6f5a7dbe
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "66055407"
---
# <a name="sql-destination-editor-connection-manager-page"></a>[SQL 変換先エディター] ([接続マネージャー] ページ)
  **[SQL 変換先エディター]** ダイアログ ボックスの **[接続マネージャー]** ページを使用すると、データ ソース情報を指定したり、結果をプレビューしたりできます。 変換[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]先は、 [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]データベース内のテーブルまたはビューにデータを読み込みます。  
  
 SQL Server 変換先の詳細については、「 [SQL Server Destination](data-flow/sql-server-destination.md)」を参照してください。  
  
## <a name="options"></a>オプション  
 **OLE DB 接続マネージャー**  
 一覧から既存の接続を選択するか、 **[新規作成]** をクリックして新しい接続を作成します。  
  
 **新しい**  
 **[OLE DB 接続マネージャーの構成]** ダイアログ ボックスを使用して、新しい接続を作成します。  
  
 **[テーブルまたはビューを使用する]**  
 既存のテーブルまたはビューを一覧から選択するか、 **[新規作成]** をクリックして新しい接続を作成します。  
  
 **新しい**  
 **[テーブルの作成]** ダイアログ ボックスを使用して新しいテーブルを作成します。  
  
> [!NOTE]  
>  [**新規**] をクリック[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]すると、接続されたデータソースに基づいて既定の CREATE TABLE ステートメントが生成されます。 基になるテーブルの列に FILESTREAM 属性が宣言されていても、この既定の CREATE TABLE ステートメントには FILESTREAM 属性が含まれません。 FILESTREAM 属性を使用して [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] コンポーネントを実行するには、まず対象データベースに FILESTREAM ストレージを実装します。 次に、 **[テーブルの作成]** ダイアログ ボックスで CREATE TABLE ステートメントに FILESTREAM 属性を追加します。 詳細については、「[バイナリ ラージ オブジェクト &#40;Blob&#41; データ &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md)」を参照してください。  
  
 **［プレビュー］**  
 **[クエリ結果のプレビュー]** ダイアログ ボックスを使用して、結果をプレビューします。 プレビューでは、最大で 200 行を表示できます。  
  
## <a name="see-also"></a>参照  
 [Integration Services のエラーとメッセージの参照](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [SQL 変換先エディター &#40;マッピングページ&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md)   
 [SQL 変換先エディター &#40;詳細設定ページ&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md)   
 [SQL Server 変換先を使用してデータの一括読み込みを行う](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
