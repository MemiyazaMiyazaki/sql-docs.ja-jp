---
title: trigger_event_types (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- trigger_event_types_TSQL
- sys.trigger_event_types_TSQL
- sys.trigger_event_types
- trigger_event_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.trigger_event_types catalog view
ms.assetid: 054aed54-7151-4760-934a-149fa434f1ae
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 152fd6ca2798b9866b9a6fe9b439bfcc2c4d6a77
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82828124"
---
# <a name="systrigger_event_types-transact-sql"></a>sys.trigger_event_types (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  トリガーを起動できるイベントまたはイベントグループごとに1行の値を返します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**type**|**int**|トリガーを起動するイベントまたはイベント グループの種類。|  
|**type_name**|**nvarchar (64)**|イベントまたはイベントグループの名前。 これは、 [CREATE TRIGGER](../../t-sql/statements/create-trigger-transact-sql.md)ステートメントの FOR 句で指定できます。|  
|**parent_type**|**int**|イベントまたはイベントグループの親であるイベントグループの種類。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [オブジェクトカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
