---
title: .NET Framework から .NET Core への移植
description: 移植プロセスを理解し、.NET Framework プロジェクトを .NET Core に移植する際に役立つツールを確認します。
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.openlocfilehash: d273b3abe46de59aa55b5b9a531d3c572a065124
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48835393"
---
# <a name="porting-to-net-core-from-net-framework"></a>.NET Framework から .NET Core への移植

.NET Framework で実行されているコードがある場合は、.NET Core 1.0 でコードを実行することに関心があるかもしれません。  この記事では、移植プロセスの概要と、.NET Core に移植するときに役立つツールの一覧を示します。

## <a name="overview-of-the-porting-process"></a>移植プロセスの概要

移植の推奨プロセスでは、次の一連の手順に従います。  プロセスのこれらの各部分については、他の記事で詳しく説明します。

1. サードパーティの依存関係を識別し、理解します。

   このプロセスでは、サードパーティの依存関係がどのようなものか、それらにどのように依存しているか、それらが .NET Core でも実行されるかどうかを確認する方法、および実行されない場合に従う手順について理解します。
   
2. ターゲットの .NET Framework 4.6.2 に移植するすべてのプロジェクトをターゲットとして再指定します。

   これにより、.NET Core が特定の API をサポートできない場合に、.NET Framework 固有のターゲットに対して API の代替を確実に使用できます。
   
3. [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)使用して、アセンブリを分析し、その結果に基づいて移植を行う計画を作成します。

   API Portability Analyzer ツールは、コンパイル済みアセンブリを分析し、レポートを生成します。このレポートには、移植性の概要と、.NET Core ではサポートされていない使用中の各 API の内訳が示されます。  このレポートをコードベースの分析と共に使用して、コードを移植する方法の計画を作成します。
   
4. テスト コードを移植します。

   .NET Core への移植はコードベースにとって大きな変更となるため、コードの移植時にテストを実行できるように、テスト コードを移植することが推奨されます。  現在、MSTest、xUnit、および NUnit は .NET Core 1.0 をサポートしています。
   
6. 移植の計画を実行します。

## <a name="tools-to-help"></a>役立つツール

役立つツールの簡単な一覧を次に示します。

* NuGet - [Nuget クライアント](https://dist.nuget.org/index.html)または [NuGet パッケージ エクスプローラー](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)。 .NET 実装用の Microsoft のパッケージ マネージャー。
* Api Portability Analyzer - [コマンドライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)または [Visual Studio 拡張機能](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)。アセンブリごとの問題の内訳を含む、.NET Framework と .NET Core の間のコードの移植性に関するレポートを生成できるツール チェーンです。  「[Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/)」 (作業に役立つツール) を参照してください。
* Reverse Package Search - 型を検索し、その型を含むパッケージを検索するための[便利な Web サービス](https://packagesearch.azurewebsites.net)。

## <a name="next-steps"></a>次の手順

[サードパーティの依存関係の分析](third-party-deps.md)
   
