---
title: dm_pdw_component_health_alerts (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: 88f05392-1e97-4693-ba60-a4910af3c000
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 25b9274946c5890e5ff688663a0cd3d37cb3850e
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82811398"
---
# <a name="sysdm_pdw_component_health_alerts-transact-sql"></a>dm_pdw_component_health_alerts (Transact-sql)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  以前に発行されたアラートをアプライアンスコンポーネントに格納します。  
  
|列名|データ型|説明|範囲|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|ノードの一意識別子 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id、および alert_instance_id を使用して、このビューのキーを形成します。|NOT NULL|  
|component_id|**int**|コンポーネントの ID。 「 [Sys. pdw_health_components &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md)」を参照してください。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id、および alert_instance_id を使用して、このビューのキーを形成します。|NOT NULL|  
|component_instance_id|**nvarchar(255)**|pdw_node_id、component_id、component_instance_id、alert_id、および alert_instance_id を使用して、このビューのキーを形成します。|NOT NULL|  
|alert_id|**int**|アラートの種類の ID。 「 [Sys. pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md)」を参照してください。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id、および alert_instance_id を使用して、このビューのキーを形成します。|NOT NULL|  
|alert_instance_id|**nvarchar (36)**|指定された警告のインスタンスを識別します。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id、および alert_instance_id を使用して、このビューのキーを形成します。|NOT NULL|  
|previous_value|**nvarchar(255)**|アラートの種類が StatusChange の場合に使用します。 これは、以前のコンポーネントの状態です。 種類がしきい値のアラートの値は NULL です。 アラートの種類の一覧については、「 [pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 」を参照してください。|NULL|  
|current_value|**nvarchar(255)**|アラートの種類が StatusChange の場合に使用します。 これは、現在のコンポーネントのステータスです。 種類がしきい値のアラートの値は NULL です。 アラートの種類の一覧については、「 [pdw_health_alerts &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 」を参照してください。|NULL|  
|create_time|**datetime**|アラートが生成された日時。|NOT NULL|  
  
## <a name="see-also"></a>参照  
 [SQL Data Warehouse および並列データウェアハウスの動的管理ビュー &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
