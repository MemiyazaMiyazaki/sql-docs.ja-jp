---
title: グレゴリオ暦 | の制約Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data types [ODBC], Gregorian calendar
- Gregorian calendar [ODBC]
ms.assetid: 70667410-c582-4369-8e06-9d98e21cd2bf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f88842c7426e17af1fdc0533b8b97e2c559de237
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81284762"
---
# <a name="constraints-of-the-gregorian-calendar"></a>グレゴリオ暦カレンダーの制限
日付と時刻のデータ型、および interval データ型の末尾のフィールドは、グレゴリオ暦の制約に準拠している必要があります。 これらの制約は次のとおりです。  
  
-   Month フィールドの値は1から12までの範囲で指定する必要があります。  
  
-   [日] フィールドの値は、1から、月の日数までの範囲で指定する必要があります。 月の日数は、年と月のフィールドの値によって決まります。28、29、30、または31のいずれかを指定できます。 (月の日数は、うるう年かどうかによっても異なります)。  
  
-   時間フィールドの値は 0 ~ 23 の範囲で指定する必要があります。  
  
-   分のフィールドの値は 0 ~ 59 の範囲で指定する必要があります。  
  
-   Interval データ型の末尾の秒のフィールドでは、秒の値は 0 ~ 59.9 (*n*) の範囲で指定する必要があります。ここで、 *n*は秒の小数部の有効桁数です。  
  
-   Datetime データ型の末尾の秒のフィールドの場合、秒の値は 0 ~ 61.9 (*n*) の範囲で指定する必要があります。ここで、 *n*は "9" 桁の数字、 *n*の値は秒の小数部の有効桁数です。 (秒の範囲では、sidereal time の同期を維持するために、2つのうるう秒を指定できます)。
