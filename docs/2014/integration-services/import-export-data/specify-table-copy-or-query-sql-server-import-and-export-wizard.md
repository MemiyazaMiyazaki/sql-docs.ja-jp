---
title: テーブルのコピーまたはクエリの指定 (SQL Server インポートおよびエクスポート ウィザード) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.specifytablecopyorquery.f1
ms.assetid: 08aa7158-40e6-4ef3-84d3-1265a8ba194c
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 524e878933652699bef6e31da42d3a784b54df7c
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62892644"
---
# <a name="specify-table-copy-or-query-sql-server-import-and-export-wizard"></a>[テーブルのコピーまたはクエリの指定] \(SQL Server インポートおよびエクスポート ウィザード)
  [**テーブルのコピーまたはクエリの指定**] ページを使用すると、データのコピー方法を指定できます。 グラフィカル インターフェイスを使用して、コピーする既存データベースを選択したり、Transact-SQL を使用してさらに複雑なクエリを作成したりできます。  
  
 このウィザードの詳細については、「 [SQL Server インポートおよびエクスポートウィザード](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)」を参照してください。 ウィザードを起動するためのオプション、およびウィザードを正常に実行するために必要な権限の詳細については、「 [run the SQL Server Import And Export wizard](start-the-sql-server-import-and-export-wizard.md)」を参照してください。  
  
 SQL Server インポートおよびエクスポート ウィザードの目的は、変換元から変換先にデータをコピーすることです。 また、このウィザードでは、変換先データベースと変換先テーブルも作成できます。 ただし、複数のデータベースやテーブルまたは他の種類のデータベース オブジェクトをコピーする必要がある場合は、データベース コピー ウィザードを使用してください。 詳細については、「 [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md)」を参照してください。  
  
## <a name="options"></a>オプション  
 **1つ以上のテーブルまたはビューからデータをコピーする**  
 **[コピー元のテーブルおよびビューを選択**] ダイアログボックスを使用して、選択したコピー元のテーブルおよびビューから、指定した変換先にフィールドをコピーします。 レコードのフィルター選択や並べ替えを実行せず、コピー元のすべてのデータをコピーする場合に、このオプションを使用します。  
  
 データプロバイダーを使用[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]してデータソースに接続する場合、[ **1 つ以上のテーブルまたはビューからデータをコピー**する] オプションが使用できないことがあります。 このオプションは、ProviderDescriptors.xml ファイルに ProviderDescription セクションがあるプロバイダーでのみ使用できます。 各 ProviderDescription セクションには、対応するプロバイダーからメタデータを取得するのに必要な情報が含まれています。 既定では、ProviderDescriptors.xml ファイルには、次のプロバイダーの ProviderDescription セクションのみが含まれています。  
  
-   System.Data.SqlClient  
  
-   System.Data.OracleClient  
  
-   System.Data.OleDb  
  
-   System.Data.Odbc  
  
 追加のプロバイダーに対して [ **1 つ以上のテーブルまたはビューからデータをコピー**する] オプションを使用できるようにするために、サードパーティは独自の providerdescriptor セクションを providerdescriptor .xml ファイルに追加できます。 既定では、このファイルは\<*ドライブ*> にあります。 (&)。 ProviderDescriptor セクションの要件については、ProviderDescriptors.xsd スキーマ ファイルを参照してください。既定では、このファイルは、ProviderDescriptors.xml ファイルと同じフォルダーに格納されています。  
  
 **転送するデータを指定するクエリを記述する**  
 [基になる**クエリの指定**] ダイアログボックスを使用して、行を取得する SQL ステートメントを作成します。 コピー操作中にコピー元データを変更したり、制限したりする場合に、このオプションを使用します。 選択条件に一致する行のみをコピーできます。  
  
  
