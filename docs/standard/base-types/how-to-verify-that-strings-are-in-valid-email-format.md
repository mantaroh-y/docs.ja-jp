---
title: "方法 : 文字列が有効な電子メール形式であるかどうかを検証する | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "正規表現、例"
  - "ユーザー入力、例"
  - "Regex.IsMatch メソッド"
  - "正規表現 [.NET Framework]、例"
  - "例 [Visual Basic]、文字列"
  - "IsValidEmail"
  - "検証、電子メールの文字列"
  - "入力、確認"
  - "文字列 [.NET Framework]、例 [Visual Basic]"
  - "電子メール [.NET Framework]、検証"
  - "IsMatch メソッド"
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
caps.latest.revision: 30
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 30
---
# 方法 : 文字列が有効な電子メール形式であるかどうかを検証する
正規表現を使用して文字列の形式が有効な電子メール形式であるかどうかを検証する例を次に示します。  
  
## 使用例  
 次の例では、`IsValidEmail` メソッドを定義します。このメソッドは、文字列に有効な電子メール アドレスが含まれている場合に `true` を返し、含まれていない場合に `false` を返します。それ以外の動作は行いません。  
  
 電子メール アドレスが有効であることを確認するため、`IsValidEmail` メソッドは <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=fullName> メソッドを呼び出し、`(@)(.+)$` の正規表現パターンを指定して、電子メール アドレスからドメイン名を切り離します。 3 番目のパラメーターは、一致したテキストを操作また置換するメソッドを表す <xref:System.Text.RegularExpressions.MatchEvaluator> デリゲートです。 正規表現パターンは次のように解釈されます。  
  
|パターン|説明|  
|----------|--------|  
|`(@)`|@ 文字と一致します。 これが最初のキャプチャ グループです。|  
|`(.+)`|任意の文字の 1 回以上の出現に一致します。 これが 2 番目のキャプチャ グループです。|  
|`$`|入力文字列の末尾で照合を終了します。|  
  
 ドメイン名は @ 文字と合わせて `DomainMapper` メソッドに渡されます。このメソッドは <xref:System.Globalization.IdnMapping> クラスを使用して、US\-ASCII 文字の範囲に含まれない Unicode 文字を Punycode に変換します。 また、このメソッドは、`invalid` メソッドがドメイン名に無効な文字を検出すると、`True` フラグを <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=fullName> に設定します。 このメソッドは、Punycode ドメイン名の前に @ 記号を付けて、これを `IsValidEmail` メソッドに返します。  
  
 次に、`IsValidEmail` メソッドは <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=fullName> メソッドを呼び出して、電子メール アドレスが正規表現パターンに準拠するかどうかを確認します。  
  
 `IsValidEmail` メソッドは、認証によって電子メール アドレスを検証するわけではありません。 電子メール アドレスの形式として有効かどうかを判断しているだけです。 さらに、`IsValidEmail` メソッドは、最上位ドメイン名が [IANA ルート ゾーン データベース](https://www.iana.org/domains/root/db)に掲載されている有効なドメイン名であることを確認しません \(これには検索操作が必要です\)。 代わりに、正規表現によって単に最上位ドメイン名が 2 ～ 24 文字の ASCII 英数字で構成されており、最初の文字と末尾の文字は英数字、その他の文字は英数字またはハイフン \(\-\) であることを確認します。  
  
 [!code-csharp[RegularExpressions.Examples.Email#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#7)]
 [!code-vb[RegularExpressions.Examples.Email#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#7)]  
  
 この例の正規表現パターン `^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$` の意味を次の表に示します。 正規表現のコンパイルでは、<xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> フラグが使用されることに注意してください。  
  
|パターン|説明|  
|----------|--------|  
|`^`|文字列の先頭から照合を開始します。|  
|`(?(")`|最初の文字が引用符であるかどうかを確認します。`(?(")` は代替構成体の開始位置です。|  
|`(?("")("".+?(?<!\\)""@)`|最初の文字が引用符である場合、始まりの引用符に続く 1 つ以上の任意の文字と終わりの引用符に一致します。 終わりの引用符の前には円記号 \(\\\) を使用できません。`(?<!` はゼロ幅の否定先読みアサーションの開始です。 文字列はアット マーク \(@\) で終わる必要があります。|  
|`&#124;(([0-9a-z]`|最初の文字が引用符でない場合は、a ～ z または A ～ Z の任意の英字または 0 ～ 9 の任意の数字と一致します \(比較では大文字小文字は区別されません\)。|  
|`(\.(?!\.))`|次の文字がピリオドの場合は、その文字と一致します。 ピリオドでない場合は、次の文字を先読みして照合を継続します。`(?!\.)` は、2 つの連続するピリオドが電子メール アドレスのローカル部分に出現することを防ぐゼロ幅の負の先読みアサーションです。|  
|`&#124;[-!#\$%&'\*\+/=\?\^`\{\}\&#124;~\w]`|次の文字がピリオドでない場合は、任意の単語文字または \-\!\#$%'\*\+\=?^\`{}&#124;~ のいずれかの文字と一致します。|  
|`((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^`\{\}\&#124;~\w])*`|0 回以上の代替パターン \(ピリオドとそれに続くピリオド以外の文字、または複数の文字のうちのいずれかの 1 文字\) と一致します。|  
|`@`|@ 文字と一致します。|  
|`(?<=[0-9a-z])`|@ 文字の前にくる文字が A ～ Z、a ～ z、または 0 ～ 9 である場合に照合を継続します。`(?<=[0-9a-z])` 構成体は、ゼロ幅の正の後読みアサーションを定義します。|  
|`(?(\[)`|@ に続く文字が左角かっこかどうかを確認します。|  
|`(\[(\d{1,3}\.){3}\d{1,3}\])`|左角かっこの場合は、左角かっこ、それに続く IP アドレス \(各セットがピリオドで区切られた、4 セットの 1 ～ 3 桁の数字\)、および右角かっこと一致します。|  
|`&#124;(([0-9a-z][-\w]*[0-9a-z]*\.)+`|@ に続く文字が左角かっこでない場合は、値が A ～ Z、a ～ z、または 0 ～ 9 の 1 つの英数字の後に、単語文字またはハイフンの 0 回以上の出現、A ～ Z、a ～ z、または 0 ～ 9 の値の 0 個または 1 つの英数字、さらにピリオドが続くパターンと一致します。 このパターンは 1 回以上繰り返すことができ、後ろに最上位ドメイン名が続く必要があります。|  
|`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`|最上位ドメイン名では、最初の文字と最後の文字が英数字文字 \(a ～ z、A ～ Z、0 ～ 9\) である必要があります。 また、0 ～ 22 文字の ASCII 文字 \(英数字またはハイフン\) を含めることができます。|  
|`$`|入力文字列の末尾で照合を終了します。|  
  
> [!NOTE]
>  電子メール アドレスの検証に正規表現を使用する代わりに、<xref:System.Net.Mail.MailAddress?displayProperty=fullName> クラスを使用できます。 電子メール アドレスが有効であるかどうかを判別するには、電子メール アドレスを<xref:System.Net.Mail.MailAddress.%23ctor%28System.String%29?displayProperty=fullName> クラス コンストラクターに渡します。  
  
## コードのコンパイル  
 `IsValidEmail` メソッドと `DomainMapper` メソッドは、正規表現ユーティリティ メソッドのライブラリに含めることができるほか、アプリケーション クラス内のプライベートな静的メソッドやインスタンス メソッドとして含めることもできます。  
  
 これらを正規表現ライブラリに含めるには、Visual Studio のクラス ライブラリ プロジェクトにコードをコピーして貼り付けるか、コードをテキスト ファイルにコピーして貼り付けて、次のようなコマンドでコマンド ラインからコンパイルします \(ソース コード ファイルの名前を RegexUtilities.cs または RegexUtilities.vb と仮定しています\)。  
  
```csharp  
csc /t:library RegexUtilities.cs  
```  
  
```vb  
vbc /t:library RegexUtilities.vb  
```  
  
 また、<xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName> メソッドを使用して、この正規表現を正規表現ライブラリに追加できます。  
  
 正規表現ライブラリ内で使用した場合は、次のようなコードを使用して呼び出すことができます。  
  
 [!code-csharp[RegularExpressions.Examples.Email#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#8)]
 [!code-vb[RegularExpressions.Examples.Email#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#8)]  
  
 電子メール検証の正規表現を含む RegexUtilities.dll という名前のクラス ライブラリを作成してあると仮定した場合、この例は次の方法のいずれかでコンパイルできます。  
  
-   Visual Studio では、コンソール アプリケーションを作成して、RegexUtilities.dll への参照をプロジェクトに追加します。  
  
-   コマンド ラインからは、ソース コードをテキスト ファイルにコピーして貼り付け、次のようなコマンドでコンパイルします \(ソース コード ファイルの名前を Example.cs または Example.vb と仮定しています\)。  
  
    ```csharp  
    csc Example.cs /r:RegexUtilities.dll  
    ```  
  
    ```vb  
    vbc Example.vb /r:RegexUtilities.dll  
    ```  
  
## 参照  
 [.NET Framework の正規表現](../../../docs/standard/base-types/regular-expressions.md)