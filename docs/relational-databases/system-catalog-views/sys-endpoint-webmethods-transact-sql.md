---
title: endpoint_webmethods (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.endpoint_webmethods_TSQL
- sys.endpoint_webmethods
- endpoint_webmethods_TSQL
- sys.http_soap_methods_TSQL
- endpoint_webmethods
- sys.http_soap_methods
dev_langs:
- TSQL
helpviewer_keywords:
- sys.endpoint_webmethods catalog view
ms.assetid: 7dad0cf6-eafa-47cf-98cc-75ba8d3c7959
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1d3d9c528b7fd74055e5a98348b9766af320b7d7
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82829720"
---
# <a name="sysendpoint_webmethods-transact-sql"></a>sys.endpoint_webmethods (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 SOAP 対応 HTTP エンドポイントで定義されている SOAP メソッドごとに1行の値を格納します。 endpoint_id 列と namespace 列の組み合わせは一意です。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|endpoint_id|**int**|Web メソッドが定義されているエンドポイントの ID です。|  
|namespace|**nvarchar (384)**|Webmethod の名前空間。|  
|method_alias|**nvarchar (64)**|メソッドのエイリアス。<br /><br /> 注: [!INCLUDE[tsql](../../includes/tsql-md.md)] 識別子では、WSDL メソッド名の中で有効でない文字を使用できます。<br /><br /> エイリアスは、エンドポイントの WSDL の説明で公開されている名前を、webmethod が呼び出されたときに呼び出される、基になる実際の実行可能オブジェクトにマップするために使用され [!INCLUDE[tsql](../../includes/tsql-md.md)] ます。|  
|object_name|**nvarchar (776)**|NAME = オプションで指定された、Web メソッドのリダイレクト先のオブジェクト名です。 名前の部分はピリオド (.) で区切られ、角かっこを使用して区切られ `[``]` ます。<br /><br /> オブジェクト名は WSDL オプションで指定されている、3 つの部分から成る名前でなければなりません。|  
|result_schema|**tinyint**|XSD (ある場合) を応答と共に返送するかどうかを指定するオプションです。<br /><br /> 0 = なし<br /><br /> 1 = 標準<br /><br /> 2 = 既定値|  
|result_schema_desc|**nvarchar(60)**|XSD (ある場合) を応答と共に返送するかどうかを指定するオプションの説明です。<br /><br /> NONE<br /><br /> STANDARD<br /><br /> DEFAULT|  
|result_format|**tinyint**|応答において結果をどのようにフォーマットするかを指定するオプションです。<br /><br /> 1 = ALL_RESULTS<br /><br /> 2 = ROWSETS_ONLY<br /><br /> 3 = なし|  
|result_format_desc|**nvarchar(60)**|応答での結果の書式設定方法を決定するオプションの説明。<br /><br /> ALL_RESULTS<br /><br /> ROWSETS_ONLY<br /><br /> NONE|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [エンドポイントのカタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql.md)   
 [カタログ ビュー &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
