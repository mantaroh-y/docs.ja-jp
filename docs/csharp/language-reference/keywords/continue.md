---
title: continue ステートメント (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 37315caf14ba829dfc91da065bc49982f21b947f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861407"
---
# <a name="continue-c-reference"></a>continue (C# リファレンス)

`continue` ステートメントは、それを囲んでいる [while](../../../csharp/language-reference/keywords/while.md)、[do](../../../csharp/language-reference/keywords/do.md)、[for](../../../csharp/language-reference/keywords/for.md)、または [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。

## <a name="example"></a>例

この例では、1 から 10 までカウントするようカウンターが初期化されます。 `continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`for` 本文の `continue` から終わりまでのステートメントがスキップされます。

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# のキーワード](../../../csharp/language-reference/keywords/index.md)  
- [break ステートメント](/cpp/cpp/break-statement-cpp)  
- [ジャンプ ステートメント](../../../csharp/language-reference/keywords/jump-statements.md)