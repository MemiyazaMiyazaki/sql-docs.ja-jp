---
title: データ フロー内のデータ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- comparing data
- data types [Integration Services], data flow
- parsing [Integration Services]
- string comparisons
- data flow [Integration Services], data options
ms.assetid: 8a9d6186-eb52-48e3-997e-021f24d458a3
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 225b6010e5d5a6c45a84d7e22272c4e5242906fd
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62827898"
---
# <a name="data-in-data-flows"></a>データ フロー内のデータ
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] には、データ フローで使用するデータ型のセットが用意されています。  
  
## <a name="data-type-conversion"></a>データ型の変換  
 データ フローに追加する変換元は、変換元のデータを [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] のデータ型に変換します。 後続の変換では、データを別の [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] のデータ型に変換できます。また、データの読み込み先となるデータ ストアの型によっては、変換先は、最後の [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] のデータ型を、変換先のデータ ストアで必要なデータ型に変換します。 詳細については、「 [Integration Services Data Types](integration-services-data-types.md)」を参照してください。  
  
 データを [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] のデータ型に変換するために、データ フロー コンポーネントはデータを解析します。 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] には、高速解析と標準解析という 2 種類のデータ解析が用意されています。 ほとんどのデータ フロー コンポーネントで使用できるのは、標準解析のみです。ただし、フラット ファイルの変換元とデータ変換の変換では、高速解析と標準解析のどちらも使用できます。 詳細については、「 [データの解析](parsing-data.md)」を参照してください。  
  
## <a name="data-type-comparison"></a>データ型の比較  
 多くの変換は、データ値を比較します。 たとえば、集計変換はデータ行セットの値を集計する目的で値を比較し、並べ替え変換は値を並べ替える目的で値を比較します。また、参照変換は、データ値を別の参照テーブルにある値と比較します。 文字列を比較する方法を指定するため、変換には比較オプションのセットが含まれています。比較オプションには、大文字と小文字を区別するかどうか、日本語テキストでかなの種類をどのように処理するのか、文字列内の空白文字を無視するかどうか、などを指定するオプションがあります。 詳しくは、「 [Comparing String Data](comparing-string-data.md)」をご覧ください。  
  
 式エバリュエーターも、変数、優先順位制約、および変換が使用する式を評価する際に、データ値を比較します。  
  
## <a name="data-flow-troubleshooting"></a>データ フローのトラブルシューティング  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] カタログにパッケージを配置したら、実行時にパッケージのデータ フローを分析して、パフォーマンスを確認したり、他の問題を見つけたりすることができます。 パッケージの状態と履歴を表示できる標準レポートを利用できます。また、パッケージ実行に関する詳細情報を提供するデータベース ビューに対してクエリを実行することもできます。 実行時にデータ タップを動的に追加および削除して、パッケージの特定のコンポーネントをターゲットとすることもできます。 詳細については、「 [データ フローの解析](data-flow.md)」を参照してください。  
  
  
