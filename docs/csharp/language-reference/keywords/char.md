---
title: char キーワード (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 95ecfaaf1397f7a4598faba6528b38170062145a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43742027"
---
# <a name="char-c-reference"></a>char (C# リファレンス)

`char` キーワードは、Unicode 文字を表すために .NET Framework によって使用される <xref:System.Char?displayProperty=nameWithType> 構造体のインスタンスを宣言するときに使用されます。 `Char` オブジェクトの値は、16 ビット数 (序数) 値です。

 Unicode 文字は、世界各国の文字言語の大半を表すために使用されます。

|型|範囲|サイズ|.NET 型|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 ～ U+FFFF|Unicode 16 ビット文字|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>リテラル

`char` 型の定数は、文字リテラル、16 進数のエスケープ シーケンス、または Unicode 表現として記述できます。 また、整数の文字コードをキャストすることもできます。 次の例では、4 つの `char` 変数が `X` という同じ文字で初期化されています。

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>変換

`char` は、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md)、または [decimal](../../../csharp/language-reference/keywords/decimal.md) に暗黙的に変換できます。 ただし、他の型から `char` 型へと暗黙的に変換することはできません。

<xref:System.Char?displayProperty=nameWithType> 型では、`char` 値を操作するための静的メソッドがいくつか提供されています。

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- <xref:System.Char>  
- [C# リファレンス](../../../csharp/language-reference/index.md)  
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [C# のキーワード](../../../csharp/language-reference/keywords/index.md)  
- [整数型の一覧表](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [組み込み型の一覧表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [暗黙的な数値変換の一覧表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [明示的な数値変換の一覧表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Null 許容型](../../../csharp/programming-guide/nullable-types/index.md)  
- [文字列](../../../csharp/programming-guide/strings/index.md)