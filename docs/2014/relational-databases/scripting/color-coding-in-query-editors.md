---
title: クエリ エディターでのコードの色分け
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 840096c197a2e827281bb0023ad03a6d407f3758
ms.sourcegitcommit: b72c9fc9436c44c6a21fd96223c73bf94706c06b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82704052"
---
# <a name="color-coding-in-query-editors"></a>クエリ エディターでのコードの色分け
  コード エディターで入力されたテキストにはカテゴリが割り当てられ、それぞれのカテゴリが色分けされます。 色分けによってコード内のテキストをすばやく見つけることができます。 たとえば、濃い緑を使用してコメントが目立つようにします。 次の表では、最も一般的な色を示します。 **[ツール]** の **[オプション]** メニューを使用して、色とカテゴリの完全な一覧を表示して、独自の配色を構成できます。 既定の色を変更する方法の詳細については、「 [フォントの色、サイズ、およびスタイルを変更する方法](change-font-color-size-and-style.md)」を参照してください。  
  
## <a name="default-code-colors"></a>コードの既定の色分け  
  
|Color|カテゴリ|  
|-----------|--------------|  
|[赤]|SQL 文字列|  
|緑|解説|  
|黒 (背景は銀色)|SQLCMD コマンド|  
|赤紫|システム関数|  
|[緑]|システム テーブル、ビュー、またはテーブル値関数。 sys および INFORMATION_SCHEMA のすべてのシステム スキーマ。|  
|青|Keyword|  
|青緑|行番号またはテンプレート パラメーター|  
|茶色|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ストアド プロシージャ (stored procedure)|  
|灰色|オペレーター|  
  
## <a name="status-bar"></a>ステータス バー  
 オブジェクト エクスプローラーで、登録済みサーバーまたは [!INCLUDE[ssDE](../../includes/ssde-md.md)] サーバーが [!INCLUDE[ssDE](../../includes/ssde-md.md)] クエリ エディターのステータス バーに別の色で表示されるように構成することができます。 そうすることで、多くのウィンドウを同時に開いているときに、各エディター ウィンドウがどのサーバーに接続しているかを識別しやすくなります。 ステータス バーの色の設定の詳細については、「[ステータス バー &#40;データベース エンジン クエリ エディター&#41;](status-bar-database-engine-query-editor.md)」を参照してください。  
  
 エディターの種類によっては、ステータス バーが表示されない場合や、複数の色がサポートされていない場合があります。  
  
  
