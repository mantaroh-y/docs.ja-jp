---
title: "IEnumIDENTITY_ATTRIBUTE インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumIDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords: IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f88e400556421e0908e0a0b115f66ec3221124c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="ienumidentityattribute-interface"></a>IEnumIDENTITY_ATTRIBUTE インターフェイス
現在のスコープ内のコード オブジェクトの属性の列挙子として機能します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|新しいインターフェイス ポインターを取得`IEnumIDENTITY_ATTRIBUTE`これと同じメンバーを格納している`IEnumIDENTITY_ATTRIBUTE`です。|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|この要素に含まれるデータを書き込みます`IEnumIDENTITY_ATTRIBUTE`指定されたデータ バッファーにします。|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|指定した数の現在の位置以降にある属性を取得します。|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|これの先頭に、命令ポインターを移動`IEnumIDENTITY_ATTRIBUTE`です。|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|指定した数の現在位置の要素では、命令ポインターを前方を移動します。|  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Isolation.h  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [Fusion インターフェイス](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)