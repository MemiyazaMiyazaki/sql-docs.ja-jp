---
title: pdw_distributions (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 572b5187-9753-4063-adf8-65dea87d11f8
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 7deddb57cdc02410fe161728f45190492ac18a16
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "68127549"
---
# <a name="syspdw_distributions-transact-sql"></a>pdw_distributions (Transact-sql)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  アプライアンス上の分布に関する情報を保持します。 アプライアンスのディストリビューションごとに1つの行が表示されます。  
  
|列名|データ型|説明|範囲|  
|-----------------|---------------|-----------------|-----------|  
|distribution_id|**int**|分布に関連付けられている一意の数値 id。<br /><br /> このビューのキー。|1は、アプライアンス内のコンピューティングノード数に、コンピューティングノードあたりのディストリビューション数を乗算した値です。|  
|pdw_node_id|**int**|このディストリビューションが配置されているノードの ID。|『 [Transact-sql&#41;&#40;dm_pdw_nodes](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)の pdw_node_id を参照してください。|  
|name|**nvarchar(32)**|分散テーブルでサフィックスとして使用される、ディストリビューションに関連付けられた文字列識別子です。|文字列は、' a-z '、' a-z '、' 0-9 '、' _ '、'-' で構成されます。|  
|position|**int**|ノード内の他のディストリビューションに対して、ノード内の分布の位置。|1ノードあたりのディストリビューションの数。|  
  
## <a name="see-also"></a>参照  
 [SQL Data Warehouse and Parallel Data Warehouse Catalog Views (SQL Data Warehouse および Parallel Data Warehouse のカタログ ビュー)](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
