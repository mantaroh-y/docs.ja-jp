---
title: '|| 演算子 (C# リファレンス)'
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 58e5fd72a3748e7af0894093fc461c4efb543608
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925541"
---
# <a name="-operator-c-reference"></a>|| 演算子 (C# リファレンス)
条件付き OR 演算子 (`||`) では、`bool` オペランドの論理 OR が実行されます。 最初のオペランドが `true` と評価されると、2 番目のオペランドは評価されません。 最初のオペランドが `false` と評価されると、2 番目の演算子は、OR 式を、全体として、`true` または `false` に評価するかどうかを判断します。  
  
## <a name="remarks"></a>コメント  
 次の演算は、  
  
```csharp  
x || y  
```  
  
 次の演算に対応しています。  
  
```csharp  
x | y  
```  
  
 ただし `x` が `true` の場合、OR 演算は `y` の値に関係なく `true` となるため、`y` は評価されません。 この概念は、"ショートサーキット" 評価と呼ばれます。  
  
 条件付き OR 演算子はオーバーロードできませんが、通常の論理演算子、[true](../../../csharp/language-reference/keywords/true.md) 演算子、[false](../../../csharp/language-reference/keywords/false.md) 演算子のオーバーロードは、一定の制約内で、条件付き論理演算子のオーバーロードとも見なされます。  
  
## <a name="example"></a>例  
 次の例では、`||` が使用されている式は、最初のオペランドだけを評価します。 `|` が使用されている式は、両方のオペランドを評価します。 2 番目の例では、両方のオペランドが評価されると、実行時例外が発生します。  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>参照

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# 演算子](../../../csharp/language-reference/operators/index.md)
