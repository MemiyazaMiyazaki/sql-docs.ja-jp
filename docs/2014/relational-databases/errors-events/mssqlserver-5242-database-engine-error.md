---
title: MSSQLSERVER_5242 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: baf35c096ec552c39b70729470263765570e79dd
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "62913633"
---
# <a name="mssqlserver_5242"></a>MSSQLSERVER_5242
    
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|SQL Server|  
|イベント ID|5242|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|SQLEngine|  
|シンボル名||  
|メッセージ テキスト|データベース '%.*ls'(ID:%d) のページ %S_PGID で内部操作中に、一貫性が損なわれていることが検出されました。 テクニカル サポートにお問い合わせください。 参照番号 %ld。|  
  
## <a name="explanation"></a>説明  
 エラー メッセージで参照されているデータベース ページで構造の一貫性が損なわれています。  
  
## <a name="see-also"></a>参照  
 [DBCC CHECKDB &#40;Transact-sql&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)   
 [データベース ファイルとファイル グループ](../databases/database-files-and-filegroups.md)  
  
  
