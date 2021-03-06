---
title: Position プロパティ (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Stream::Position
helpviewer_keywords:
- Position property [ADO]
ms.assetid: daa8319a-49aa-4c1c-9af6-0b01e9ab2f9d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5669e22404ab75fc545708e1fc643cfefd3890a
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763353"
---
# <a name="position-property-ado"></a>Position プロパティ (ADO)
[ストリーム](../../../ado/reference/ado-api/stream-object-ado.md)オブジェクト内の現在の位置を示します。  
  
## <a name="settings-and-return-values"></a>設定と戻り値  
 ストリームの先頭からの現在位置のオフセットをバイト数で指定する**Long 型**の値を設定または返します。 既定値は0で、ストリームの最初のバイトを表します。  
  
## <a name="remarks"></a>解説  
 現在の位置は、ストリームの末尾の後の点に移動できます。 ストリームの末尾を越えて現在位置を指定すると、**ストリーム**オブジェクトの[サイズ](../../../ado/reference/ado-api/size-property-ado-stream.md)がそれに応じて大きくなります。 この方法で追加された新しいバイトは null になります。  
  
> [!NOTE]
>  **Position**は常にバイトを測定します。 マルチバイト文字セットを使用したテキストストリームの場合、文字数を決定するために文字サイズで位置を乗算します。 たとえば、2バイト文字セットの場合、最初の文字は0の位置、2番目の文字の位置は2、3番目の文字は4の位置になります。  
  
> [!NOTE]
>  負の値を使用して、**ストリーム**内の現在位置を変更することはできません。 **位置**には正の数値のみ使用できます。  
  
> [!NOTE]
>  読み取り専用の**ストリーム**オブジェクトの場合、**位置**が**ストリーム**の**サイズ**より大きい値に設定されていると、ADO はエラーを返しません。 **ストリーム**のサイズを変更したり、**ストリーム**の内容を変更したりすることはできません。 ただし、これは無意味な**位置**の値になるため、回避する必要があります。  
  
## <a name="applies-to"></a>適用対象  
 [Stream オブジェクト (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>参照  
 [Charset プロパティ (ADO)](../../../ado/reference/ado-api/charset-property-ado.md)
