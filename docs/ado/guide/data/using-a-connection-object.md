---
title: 接続オブジェクトを使用する |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
ms.assetid: 4b34f971-5699-43e7-9b15-137d334fa66e
author: rothja
ms.author: jroth
ms.openlocfilehash: ba23a9584e94df817e55b710ddadb073313e865b
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82750196"
---
# <a name="using-a-connection-object"></a>接続オブジェクトを使用する
**接続**オブジェクトを開く前に、データソースと接続の種類に関する特定の情報を定義する必要があります。 この情報の大部分は、 **connection**オブジェクトの[Open メソッド](../../../ado/reference/ado-api/open-method-ado-connection.md)の*Connectionstring*パラメーター、または**接続**オブジェクトの[connectionstring プロパティ](../../../ado/reference/ado-api/connectionstring-property-ado.md)によって保持されます。 接続文字列は、セミコロンで区切られた引数と値のペアのリストで構成され、値は単一引用符で囲まれています。 次に例を示します。  
  
```  
Dim sConn As String  
sConn = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _  
             "Initial Catalog='Northwind';Integrated Security='SSPI';"  
```  
  
> [!NOTE]
>  接続文字列で ODBC データソース名 (DSN) またはデータリンク (UDL) ファイルを指定することもできます。 Dsn の詳細については、「ODBC プログラマリファレンス」の「[データソースの管理](../../../odbc/admin/managing-data-sources.md)」を参照してください。 UDLs の詳細については、OLE DB プログラマーリファレンス』の「[データリンク API の概要](https://msdn.microsoft.com/95c180ea-bd4f-4dca-b95a-576afd135bbc)」を参照してください。  
  
 通常、接続は、適切な*接続文字列*をパラメーターとして使用して Open メソッドを呼び出すことによって確立します **。** 次の Visual Basic コードスニペットに例を示します。  
  
```  
Dim oConn As ADODB.Connection  
Dim oRs As ADODB.Recordset  
Dim sConn As String  
Dim sSQL as String  
  
' Open a connection.  
Set oConn = New ADODB.Connection  
.Open   
  
' Make a query over the connection.  
sSQL = "SELECT ProductID, ProductName, CategoryID, UnitPrice " & _  
             "FROM Products"  
Set oRs = New ADODB.Recordset  
oRs.Open sSQL, , adOpenStatic, adLockBatchOptimistic, adCmdText  
  
MsgBox oRs.RecordCount  
  
' Close the connection.  
oConn.Close  
Set oConn = Nothing  
  
```  
  
 ここでは、 *ActiveConnection*パラメーターの値として**接続**オブジェクト (*oconn*) 変数を受け取り**ます。** また、**接続. カーソルの場所**プロパティでは、 **aduseserver**の既定値が想定されます。 これを、前のセクションの[HelloData](../../../ado/guide/data/hellodata-a-simple-ado-application.md)の例と比較します。 次の命令を実行すると、実行時エラーが発生します。  
  
```  
oRs.MarshalOptions = adMarshalModifiedOnly  
' Disconnect the Recordset.  
Set oRs.ActiveConnection = Nothing  
```
