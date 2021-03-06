---
title: SQLCloseCursor_ODBC |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLCloseCursor function [ODBC], ODBC
ms.assetid: 5e47e3f7-e1b8-451f-bf75-daa19b7c7271
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e1b61267d093e11bf7ea25158f5dc6a29ccba6a1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "81296302"
---
# <a name="sqlclosecursor_odbc"></a>SQLCloseCursor_ODBC
> [!IMPORTANT]  
>  この機能は、今後のバージョンの Windows では削除される予定です。 新しい開発作業ではこの機能の使用を避け、現在この機能を使用しているアプリケーションの変更を検討してください。 Microsoft では、ドライバーのカーソル機能を使用することをお勧めします。  
  
 このトピックでは、カーソルライブラリでの**Sqlcloの**使用方法について説明します。 **Sqlcloに**関する一般的な情報については、「 [Sqlcloの機能](../../../odbc/reference/syntax/sqlclosecursor-function.md)」を参照してください。  
  
 カーソルライブラリでは、カーソルを開かずに**Sqlcloを**呼び出すことはできません。 これを試みると、SQLSTATE 24000 (無効なカーソル状態) が返されます。 カーソルが開いていないときに SQL_CLOSE の*オプション*を指定して**SQLFreeStmt**を呼び出すと、カーソルライブラリでサポートされます。
