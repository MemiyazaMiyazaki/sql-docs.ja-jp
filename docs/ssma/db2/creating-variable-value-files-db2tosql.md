---
title: 変数値ファイルの作成 (DB2ToSQL) |Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 122f3fbe-46a0-40df-ac3b-d43bf33d96ba
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 945b7e86641c796e79bfb87b8b7b5de25949e4c2
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "67989772"
---
# <a name="creating-variable-value-files-db2tosql"></a>変数値ファイルの作成 (DB2ToSQL)
変数値ファイルは、などのコマンドのパラメーター値を構成する XML ファイルです。サーバーの移行から別のサーバーへの移行に頻繁に変更される転送元または転送先のサーバー名を指定します。 多数のデータベースの移行が行われると、各ソースサーバーの値を格納するための複数の変数ファイルが作成され、コマンドラインで **-v**スイッチを使用してマスタースクリプトファイルに参照されます。 これにより、複数の変数ファイルの変数値を使用して、いくつかのスクリプトファイルで静的な値を保持することができます。  
  
> [!NOTE]  
> 1.  変数名の先頭には $ (ドル) 記号が付きます。 変数に変数値ファイルの値が割り当てられていない場合、スクリプトファイルの解析中にエラーが発生し、コンソールの実行プロセスが停止します。  
> 2.  の**$** エスケープ文字は**$$** です。 パラメーターの変数または静的な値に (ドル) **$** 記号が含まれている**$$** 場合は、を変数ではなく文字として扱うように指定する必要があります。  
> 3.  保守性を確保するために、ユーザー `'variable-group'`定義変数を論理的に分離するために、要素内で変数を宣言できます。  この要素の使用は必須ではありません。  
  
**例:**  
  
**例 1:**  
  
```  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="ProjectSpecs">  
  
    <variable name="$project_folder$" value="<project-folder>"/>  
  
    <variable name="$project_name$" value="<project-name>"/>  
  
    <variable name="$project_overwrite$" value="<true/false>"/>  
  
    <variable name="$project_type$" value="<project-type>"/>  
  
  </variable-group>  
  
</variables>  
```  
**例 2:**  
  
```  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="SQLServerParams">  
  
    <variable-group name="SqlServerConnectionParams">  
  
      <variable name="$TargetServerName$" value="<server-name>"/>  
  
      <variable name="$TargetDB$" value="<database-name>"/>  
  
      <variable name="$TargetUserName$" value="<user-name>"/>  
  
      <variable name="$TargetPassword$" value="<password>"/>  
  
      <variable name="$TrustedConnection$" value="<true/false>"/>  
  
    </variable-group>  
  
    <variable-group name="SqlServerObjectParams">  
  
      <variable name="$ObjectName1$" value="<object-name>"/>  
  
      <variable name="$ObjectName2$" value="<object-name>"/>  
  
    </variable-group>  
  
  </variable-group>  
  
</variables>  
```  
  
## <a name="next-step"></a>次の手順  
コンソールを操作する次の手順では、[サーバー接続ファイル &#40;DB2ToSQL&#41;作成し](../../ssma/db2/creating-the-server-connection-files-db2tosql.md)ます。  
  
## <a name="see-also"></a>参照  
[サーバー接続ファイルの作成](../oracle/creating-the-server-connection-files-oracletosql.md)  
  
