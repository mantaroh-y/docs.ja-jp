---
title: .NET Framework のバージョンおよび依存関係
ms.custom: updateeachrelease
ms.date: 07/25/2018
helpviewer_keywords:
- versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c18659fa3db1f2e7e047f1bbdc4f75ba6e96f0c6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252448"
---
# <a name="net-framework-versions-and-dependencies"></a>.NET Framework のバージョンおよび依存関係
.NET Framework の各バージョンには、共通言語ランタイム (CLR)、基底クラス ライブラリ、およびその他のマネージド ライブラリが含まれています。 このトピックでは、.NET Framework の各バージョンの主要な機能について説明し、基になっている CLR のバージョンおよび関連する開発環境に関する情報と、Windows オペレーティング システムでインストールされる .NET Framework のバージョンを示します。  
  
> [!NOTE]
>  .NET Framework のダウンロードとインストールの詳細については、「[開発者向けの .NET Framework のインストール](../../../docs/framework/install/guide-for-developers.md)」を参照してください。  
  
 次の表に、.NET Framework のバージョン履歴を要約し、各バージョンと Visual Studio、Windows、および Windows Server との関係を示します。 Visual Studio ではマルチターゲット機能が提供されているため、記載されている .NET Framework のバージョンに限定される必要はありません。  
  
 新しい各バージョンの .NET Framework には、1 つ前のバージョンの機能が含まれると共に、新機能が追加されています。 CLR は独自のバージョン番号で識別されます。 .NET Framework のバージョン番号はリリースごとにインクリメントされますが、CLR のバージョンは必ずしもインクリメントされるわけではありません。 たとえば、.NET Framework 4、4.5、およびそれ以降のリリースには CLR 4 が含まれますが、.NET Framework 2.0、3.0、3.5 には CLR 2.0 が含まれます。 (CLR の Version 3 はありません)。  
  
 サポートされるオペレーティング システムの全一覧については、[システム要件](../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。 ダウンロードについては、「[開発者向けの .NET Framework のインストール](../../../docs/framework/install/guide-for-developers.md)」を参照してください。 コンピューターにインストールされている .NET Framework のバージョンを確認する方法については、「[方法: インストールされている .NET Framework バージョンを確認する](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)」を参照してください。  
  
 次の表の "**このバージョンを含む/インストール可能な Windows**" 列および "**このバージョンを含む/インストール可能な Windows Server**" 列に ✓マークが付いているオペレーティング システム バージョンにインストールされている .NET Framework のバージョンを、[コントロール パネルで有効にする](../../../docs/framework/install/dotnet-35-windows-10.md) (Windows の場合) かサーバー マネージャーで有効にする (Windows Server の場合) 必要があります。  
  
|.NET Framework のバージョン|CLR バージョン|このバージョンを含む製品<br /> Visual Studio<br/>version|✓ このバージョンを含む製品<br />+ インストール可能<br />Windows|✓ このバージョンを含む製品<br />+ インストール可能<br />Windows Server|インストールされた .NET バージョンを確認するには|  
|----------------------------|-----------------|--------------|---------------------------------------|----------------------------------------------------|-----------------------------------------------------------|-----------------------------------------| 
|4.7.2<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-472)<br/><br/>[アクセシビリティの新機能](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-the-net-framework-472)|4| |✓  10 April 2018 Update (バージョン 1803) <br/><br/> + 10 Fall Creators Update (バージョン 1709) <br/> <br/> + 10 Creators Update (バージョン 1703) <br/> + 10 Anniversary Update (バージョン 1607) <br/> + 8.1 <br/> +7 | ✓ Windows Server、バージョン 1803 <br/> + Windows Server、バージョン 1709 <br/> + 2016 <br/> + 2012 R2 <br/> + 2012 <br/> + 2008 R2 SP1 |`Release` DWORD を使用:<br/><br/> - 461808 (Windows 10 April 2018 Update および Windows Server、バージョン 1803) <br/> - 461814 (その他すべての OS バージョン) <br/><br/> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|
|4.7.1<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-471)<br/><br/>[アクセシビリティの新機能](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-the-net-framework-471)|4| | ✓  10 Fall Creators Update (バージョン 1709) <br/> <br/> + 10 Creators Update (バージョン 1703) <br/> + 10 Anniversary Update (バージョン 1607) <br/> + 8.1 <br/> +7| + Windows Server、バージョン 1803 <br/> ✓ Windows Server、バージョン 1709 <br/> + 2016 <br/> + 2012 R2 <br/> + 2012 <br/> + 2008 R2 SP1 |`Release` DWORD を使用:<br/><br/> - 461308 (Windows 10 Creators Update と Windows Server、バージョン 1709)  <br/> - 461310 (その他すべての OS バージョン) <br/><br/> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)| 
|4.7<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-47)|4| | ✓  10 Creators Update (バージョン 1703) <br/> <br/> + 10 Anniversary Update (バージョン 1607) <br/> + 8.1 <br/> +7| + 2016 <br/> + 2012 R2 <br/> + 2012 <br/> + 2008 R2 SP1 |`Release` DWORD を使用:<br/><br/> - 460798 (Windows 10 Creators Update) <br/> - 460805 (その他すべての OS バージョン) <br/><br/> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照) |  
|4.6.2<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-462)|4||✓  10 Anniversary Update (バージョン 1607) <br /><br /> + 10 November Update (バージョン 1511) <br/> + 10 <br/> + 8.1<br />+ 7|✓ 2016<br /><br /> + 2012 R2<br />+ 2012<br />+ 2008 R2 SP1|`Release` DWORD を使用:<br /><br /> -394802 (Windows 10 Anniversary Update および Windows Server 2016) <br />- 394806 (その他すべての OS バージョン)<br /><br /> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4.6.1<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-461)|4||✓  10 November Update (バージョン 1511) <br /><br /> + 10<br />+ 8.1<br />+ 8<br />+ 7|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1|`Release` DWORD を使用:<br /><br /> - 394254 (Windows 10 November Update)<br />- 394271 (その他すべての OS バージョン)<br /><br /> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4.6<br/><br/>[新機能](../whats-new/index.md#whats-new-in-net-2015)|4|2015|✓ 10<br />+ 8.1<br />+ 8<br />+ 7<br />+ Vista|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD を使用:<br /><br /> - 393295 (Windows 10)<br />- 393297 (その他すべての OS バージョン)<br /><br /> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4.5.2<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-452)|4|-|+ 8.1<br />+ 8<br />+ 7<br />+ Vista|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD を使用:<br /><br /> 379893<br /><br />([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4.5.1<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-451)|4|2013|✓ 8.1<br />+ 8<br />+ 7<br />+ Vista|✓ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD を使用:<br /><br /> - 378675 (Windows 8.1)<br />- 378758 (その他)<br /><br /> ([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4.5<br/><br/>[新機能](../whats-new/index.md#whats-new-in-the-net-framework-45)|4|2012|✓ 8<br />+ 7<br />+ Vista|✓ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD を使用:<br /><br /> 378389<br /><br />([手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照)|  
|4<br/><br/>[新機能](../whats-new/index.md)|4|2010|+ 7<br />+ Vista|+ 2008 R2 SP1<br />+ 2008 SP2<br />+ 2003|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  
|3.5<br/><br/>[新機能](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms171868\(v=vs.90\))|2.0|2008|✓ 10\*<br/>✓ 8.1\*<br />✓ 8\*<br />✓ 7<br />+ Vista|✓2008 R2 SP1\*<br />+ 2012 R2\*<br />+ 2012\*<br />+ 2008 SP2<br />+ 2003|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  
|3.0<br/><br/>新規 : <br/>WPF、WCF、WF、CardSpace|2.0|-|✓ Vista|✓ 2008 R2 SP1*<br />✓ 2008 SP2\*<br />+ 2003|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  
|2.0<br/><br/>[新機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/ms229284\(v%3dvs.80\))|2.0|2005|-|✓ 2008 R2 SP1<br />✓ 2008 SP2<br />✓ 2003|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  
|1.1<br/><br/>[新機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/9wtde3k4\(v%3dvs.71\))|1.1|2003|-|✓ 2003|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  
|1|1|Visual Studio .NET|-|-|[手順](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)に関するページを参照|  

**ノート**

<sup>\*</sup>&nbsp;&nbsp;このオペレーティング システムで [[コントロール パネル] (Windows の場合) または [サーバー マネージャー] (Windows Server の場合)](../install/dotnet-35-windows-10.md#enable-the-net-framework-35-in-control-panel) を使用して、.NET Framework を有効にする必要があります。

 一般に、コンピューターにインストールされている .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが特定のバージョンに依存しており、バージョンが削除されると破損する可能性があるからです。 1 台のコンピューターに複数バージョンの .NET Framework を同時に読み込むことができます。 これは、以前のバージョンをアンインストールすることなく、.NET Framework をインストールできることを意味します。 詳細については、[概要](../../../docs/framework/get-started/index.md)に関するページを参照してください。

## <a name="targeting-and-running-net-framework-apps-for-version-45-and-later"></a>.NET Framework 4.5 以降のバージョンをターゲットにして実行する  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] はコンピューターの [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] を置き換えるインプレース更新であり、.NET Framework 4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、4.7.2 は [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] のインプレース更新です。つまり、同じバージョンのランタイム バージョンを使用しますが、アセンブリのバージョンが更新され、新しい型とメンバーが含まれます。 これらの更新プログラムのいずれかをインストールした後、[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] アプリ、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] アプリ、NET Framework 4.6 アプリ、.NET Framework 4.7 アプリは再コンパイルせずに実行を継続します。 ただし、逆はできません。 .NET Framework の新しいバージョンをターゲットとするアプリを .NET Framework の以前のバージョンで実行することは推奨されていません。 たとえば、[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] をターゲットとするアプリを [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] で実行することは推奨されていません。 次のガイドラインが適用されます。  
  
-   Visual Studio で、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] をプロジェクトのターゲット フレームワークとして選択して (これにより <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType> プロパティが設定されます)、プロジェクトを [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] アセンブリまたは実行可能ファイルとしてコンパイルできます。 このアセンブリまたは実行可能ファイルは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1、4.7.2 がインストールされているコンピューターで使用できます。  
  
-   Visual Studio で、[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] をプロジェクトのターゲット フレームワークとして選択して (これにより <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType> プロパティが設定されます)、プロジェクトを [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] アセンブリまたは実行可能ファイルとしてコンパイルできます。 このアセンブリまたは実行可能ファイルは [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] かそれ以降のバージョンの .NET Framework がインストールされているコンピューターでのみ実行する必要があります。 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] を対象とする実行可能ファイルは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] など、初期バージョンの .NET Framework のみがインストールされたコンピューターでは実行がブロックされ、ユーザーに [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] のインストールを求めるメッセージが表示されます。 また、[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] アセンブリは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] など、初期バージョンの .NET Framework を対象とするアプリから呼び出さないでください。  
  
     ここで使用されている [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] と [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] は単なる例にすぎません。 この原則は、実行されているシステムにインストールされているものより新しい .NET Framework のバージョンをターゲットにするアプリに適用されます。  
  
 .NET Framework の変更により、アプリケーション コードの変更が必要な場合があります。既存のアプリケーションを [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] またはそれ以降のバージョンで実行する前に、[アプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility.md)に関するページを参照してください。 現行バージョンのインストールについては、「[開発者向けの .NET Framework のインストール](../../../docs/framework/install/guide-for-developers.md)」を参照してください。 .NET Framework のサポートの詳細については、Microsoft サポート オンラインの [Microsoft .NET Framework のサポート ライフサイクル ポリシー](https://go.microsoft.com/fwlink/?LinkId=196607)に関するページを参照してください。  
  
## <a name="targeting-and-running-apps-for-older-versions"></a>以前のバージョンのアプリの対象化と実行  
 .NET Framework 2.0、3.0 および 3.5 は、同じバージョンの CLR (CLR 2.0) でビルドされています。 これらのバージョンは 1 つのインストールの連続したレイヤーを表します。 各バージョンは、以前のバージョンの上にインクリメンタル方式でビルドされます。 コンピューターでバージョン 2.0、3.0、および 3.5 を side-by-side で実行することはできません。 バージョン 3.5 をインストールすると、2.0 と 3.0 のレイヤーが自動的に取得され、バージョン 2.0、3.0、および 3.5 を対象としてビルドされたアプリケーションはすべて、バージョン 3.5 で実行できます。 ただし、.NET Framework 4 でこのレイヤーによる方法は終了し、以降のリリース (.NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1 および 4.7.2) も単独インストールの連続するレイヤーを表します。  NET Framework 4 以降では、インプロセスの side-by-side ホスティングを使用して、1 つのプロセスで複数のバージョンの CLR を実行できます。 詳細については、「[アセンブリと side-by-side 実行](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)」を参照してください。  
  
 さらに、アプリケーションがバージョン 2.0、3.0、または 3.5 を対象とする場合、ユーザーがアプリケーションを実行する前に、Windows 8、Windows 8.1、または Windows 10 のコンピューター上で .NET Framework 3.5 を有効にするように求められる場合があります。 詳細については、[Windows 10、Windows 8.1、Windows 8 への .NET Framework 3.5 のインストール](../../../docs/framework/install/dotnet-35-windows-10.md)に関するページを参照してください。  
  
## <a name="next-steps"></a>次の手順  
  
-   .NET Framework を初めて使用する場合は、[概要](../../../docs/framework/get-started/overview.md)に関するページを参照して、主な概念と機能の概要を確認してください。  
  
-   [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] とポイント リリースでの新機能と機能強化については、「[.NET Framework の新機能](../../../docs/framework/whats-new/index.md)」を参照してください。  
  
-   .NET Framework 4 から [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] およびそのポイント リリースへのアプリの移行の詳細については、[移行ガイド](../../../docs/framework/migration-guide/index.md)に関するページを参照してください。  
  
-   コンピューターにどのバージョンまたは更新プログラムがインストールされているかを判別する方法については、「[方法: インストールされている .NET Framework バージョンを確認する](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)」と「[方法: インストールされている .NET Framework の更新プログラムを確認する](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

[バージョンの互換性](../../../docs/framework/migration-guide/version-compatibility.md)   
[Microsoft .NET Framework のサポート ライフサイクル ポリシー](https://go.microsoft.com/fwlink/?LinkId=196607)   
[.NET Framework のインストールおよびアンインストールのブロックのトラブルシューティング](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
