---
title: SQL Server の Latches オブジェクト | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: a6d0d9249a5cfb801e07a85132060bb4d1781346
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "63251100"
---
# <a name="sql-server-latches-object"></a>SQL Server の Latches オブジェクト
  Microsoft **の**SQLServer:Latches[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] オブジェクトには、ラッチという内部 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] リソース ロックを監視するためのカウンターがあります。 ユーザーの利用状況とリソース使用率を調べるために行うラッチの監視は、パフォーマンスのボトルネックを特定するために役立つことがあります。  
  
 次の表では、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** カウンターについて説明します。  
  
|SQL Server Latches カウンター|説明|  
|---------------------------------|-----------------|  
|**Average Latch Wait Time (ms)**|待機しなければならなかったラッチ要求の平均ラッチ待ち時間 (ミリ秒)。|  
|**ラッチ待機数/秒**|直ちに許可できなかったラッチ要求の数。|  
|**Number of SuperLatches**|現在の SuperLatch であるラッチの数。|  
|**SuperLatch Demotions/sec**|最後の 1 秒間に通常のラッチに降格された SuperLatch の数。|  
|**SuperLatch Demotions/sec**|最後の 1 秒間に SuperLatch に昇格されたラッチの数。|  
|**Total Latch Wait Time (ms)**|直前のラッチ要求の合計ラッチ待ち時間 (ミリ秒)。|  
  
## <a name="see-also"></a>参照  
 [リソースの利用状況の監視 &#40;システム モニター&#41;](monitor-resource-usage-system-monitor.md)  
  
  
