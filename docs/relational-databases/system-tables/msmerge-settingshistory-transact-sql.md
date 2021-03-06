---
title: MSmerge_settingshistory (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSmerge_settingshistory
- MSmerge_settingshistory_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_settingshistory system table
ms.assetid: 0bdf2d5f-5502-44cd-aa9d-2d5006ad20ce
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9ac532e5212f32e5ee3bda029a2a7fb5a1231974
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82829226"
---
# <a name="msmerge_settingshistory-transact-sql"></a>MSmerge_settingshistory (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSmerge_settingshistory**テーブルは、マージレプリケーションのアーティクルおよびパブリケーションのプロパティに加えられた変更の履歴を保持するために使用され、マージレプリケーショントポロジに対して行われた変更ごとに1行のデータを保持します。 このテーブルには、プロパティの初期設定が行われたタイミングに関する情報も格納されます。 このテーブルは、パブリケーションデータベースとサブスクリプションデータベースに格納されます。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**eventtime**|**datetime**|イベントが発生した日時。|  
|**pubid**|**uniqueidentifier**|指定されたパブリケーションの一意の id 番号です。|  
|**artid**|**uniqueidentifier**|指定されたアーティクルの一意の識別番号。|  
|**eventtype**|**tinyint**|記録されるイベントの種類を指定します。次のいずれかを指定できます。<br /><br /> **1** -パブリケーションレベルのプロパティの初期設定。<br /><br /> **2** -パブリケーションのプロパティを変更します。<br /><br /> **101** -最初のアーティクルプロパティの設定。<br /><br /> **102** -アーティクルのプロパティを変更します。|  
|**propertyname**|**sysname**|設定または変更されたプロパティの名前|  
|**previousvalue**|**sysname**|プロパティが変更された場合は、前のプロパティ値。|  
|**newvalue**|**sysname**|変更後または作成時のプロパティの値。|  
|**eventtext**|**nvarchar (2000)**|イベントを説明する文字列。|  
  
## <a name="see-also"></a>参照  
 [レプリケーションテーブル &#40;Transact-sql&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [レプリケーション ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
