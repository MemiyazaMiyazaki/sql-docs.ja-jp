---
title: sys.dm_xe_database_session_targets
titleSuffix: Azure SQL Database
ms.date: 06/10/2016
ms.service: sql-database
ms.prod_service: sql-database
ms.reviewer: ''
ms.topic: language-reference
ms.assetid: 7f353e2a-f8fc-4366-97e4-aa1c49eadaf4
author: CarlRabeler
ms.author: carlrab
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.custom: seo-dt-2019
ms.openlocfilehash: ac4b9b01b85b6c8b4832a591ba18654ac58e9125
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82826696"
---
# <a name="sysdm_xe_database_session_targets-azure-sql-database"></a>sys.dm_xe_database_session_targets (Azure SQL Database)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

  セッション ターゲットに関する情報を返します。  
  
||  
|-|  
|**適用対象**: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 および将来のすべてのバージョン。|  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary (8)**|イベントセッションのメモリアドレス。 には、dm_xe_database_sessions との多対一のリレーションシップがあります。 NULL 値は許可されません。|  
|target_name|**nvarchar(60)**|セッション内のターゲットの名前。 NULL 値は許可されません。|  
|target_package_guid|**uniqueidentifier**|ターゲットを含むパッケージの GUID。 NULL 値は許可されません。|  
|execution_count|**bigint**|セッションに対してターゲットが実行された回数。 NULL 値は許可されません。|  
|execution_duration_ms|**bigint**|ターゲットが実行された時間の合計 (ミリ秒単位)。 NULL 値は許可されません。|  
|target_data|**nvarchar(max)**|イベント集計情報など、ターゲットが保持するデータ。 NULL 値が許可されます。|  
  
## <a name="permissions"></a>アクセス許可  
 VIEW DATABASE STATE 権限が必要です。  
  
### <a name="relationship-cardinalities"></a>リレーションシップ基数  
  
|From|終了|リレーションシップ|  
|----------|--------|------------------|  
|dm_xe_database_session_targets。 event_session_address|dm_xe_database_sessions. アドレス|多対一|  
  
  
