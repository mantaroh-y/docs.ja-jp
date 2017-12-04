---
title: "ICorProfilerCallback::ClassLoadFinished メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3f321849c62ffd653ffa174ff91447a2c8eec73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>ICorProfilerCallback::ClassLoadFinished メソッド
クラスの読み込みが完了したことをプロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `classId`  
 [in]既に読み込まれているクラスを識別します。  
  
 `hrStatus`  
 [in]クラスが正常に読み込まれたかどうかを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 値`classId`まで情報の要求に対して無効です、`ClassLoadFinished`メソッドが呼び出されます。  
  
 クラスの読み込みの一部が後に続ける可能性があります、`ClassLoadFinished`コールバック。 失敗を示す HRESULT で`hrStatus`は失敗を示します。 ただし、成功 HRESULT で`hrStatus`のみに、クラスの読み込みの最初の部分が成功したことを示します。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ClassLoadStarted メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)