---
title: "アーキテクチャの原則"
description: "ASP.NET Core と Azure での最新の Web アプリケーションを設計 |アーキテクチャの原則"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 20524c8aa0e64fd40a1a4a6811063557f74074d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
#<a name="architectural-principles"></a>アーキテクチャの原則

> "ビルダー建物をビルドする場合は方法プログラマは、プログラムを記述しに付属している最初の woodpecker は文明を破棄します。"  
> _\-ジェラルド Weinberg_

## <a name="summary"></a>概要

設計し、保守容易性を念頭にソフトウェア ソリューションを設計する必要があります。 このセクションで説明した原則進めることができます、クリーンで保守性の高いアプリケーションの原因となるアーキテクチャ上の決定に向けたです。 一般に、これらの原則に従って、アプリケーションの他の部分に密結合されていないが、明示的なインターフェイス経由で通信ではなく、独立したコンポーネントからアプリケーションを構築またはメッセージング システムの方向。

## <a name="common-design-principles"></a>一般的なデザインの原則

### <a name="separation-of-concerns"></a>関心の分離

開発するときの基本原則が**関心の分離**です。 この原則をアサート ソフトウェアを区切る必要がありますで実行される処理の種類に基づいてします。 たとえば、アプリケーション、ユーザーに表示する項目が注目すべきことを識別するためのロジックが含まれているとする形式などのアイテムでよりわかるように、特定の方法を検討してください。 これらが互いに関連するのみ偶然にも別の問題であるため、アイテムの書式設定を担当する動作とは別の書式を設定する項目の選択を担当の動作を注意してください。

アーキテクチャ上、インフラストラクチャとユーザー インターフェイス ロジックをコア ビジネスの動作を区切ることによってこの原則に従うアプリケーションを論理的に構築できます。 理想的には、ビジネス ルールとロジックは、アプリケーションの他のプロジェクトに依存しないように、独立したプロジェクトに存在する必要があります。 これにより、ビジネス モデルを簡単にテストし、低レベルの実装の詳細に密結合されているせずに改善できます。 関心の分離は、アプリケーション アーキテクチャ内のレイヤーの使用の背後にある主な考慮事項です。

### <a name="encapsulation"></a>カプセル化

アプリケーションのさまざまな部分を使用する必要があります**カプセル化**アプリケーションの他の部分から分離します。 アプリケーション コンポーネントとレイヤーは外部の契約に違反しない限り、共同作業者を分断することがなく、内部の実装を調整できる必要があります。 カプセル化の適切な使用により、同じインターフェイスが保持されるよう、オブジェクトおよびパッケージを別の実装に置き換えられますできるために、疎結合と、アプリケーション デザインのモジュール性を実現できます。

クラスでは、カプセル化は、クラスの内部状態へのアクセスの外部に制限することによって実現されます。 外部アクターは、オブジェクトの状態を操作する場合、その要求を実行、適切に定義された関数 (またはプロパティ set アクセス操作子) で、オブジェクトのプライベート状態への直接アクセスではなくです。 同様に、アプリケーション コンポーネントとアプリケーション自体によって、適切に定義されたインターフェイスを直接変更する、状態を許可するのではなく、使用、共同作業者が公開する必要があります。 これにより、心配する必要を行うのため中断されますの共同作業者のパブリック コントラクトが保持される限り、時間の経過と共に変化するアプリケーションの内部設計が解放されます。

### <a name="dependency-inversion"></a>依存関係の反転

アプリケーション内の依存関係の方向は、抽象化、いないの実装の詳細の方向にする必要があります。 ほとんどのアプリケーションは、コンパイル時の依存関係がランタイムの実行の方向にフローするように書き込まれます。 これには、直接の依存関係グラフが生成されます。 つまり、モジュール、C でし、コンパイル時間 A が関数を呼び出す B、モジュールの関数の呼び出しをモジュール A が図 4-1 に示すようには、C に依存している B に依存かどうか。

![](./media/image4-1.png)

**図 4-1。** 直接の依存関係グラフ。

依存関係の逆転原則を適用する許可できるようにする A に B を呼び出し、実行時に、B を実装する抽象型でメソッドを呼び出す A が b をインターフェイスに依存するによって制御 A コンパイル時に (つまり、*反転*一般的なコンパイル時の依存関係)。 実行時に、プログラムの実行フローが変更されないが、インターフェイスの概要では、これらのインターフェイスのさまざまな実装簡単に接続することを意味します。

![](./media/image4-2.png)

**図 4-2 です。** 反転された依存関係グラフ。

**依存関係の逆転**疎結合アプリケーションの構築に依存し、その逆ではなくより高いレベルの抽象化を実装する実装の詳細を書き込むための重要な部分です。 結果として得られるアプリケーションは、その結果、テスト可能で、モジュール、保守も容易です。 推奨事項*依存性の注入*依存関係の逆転という原則に従って、によって可能になりますがします。

### <a name="explicit-dependencies"></a>明示的な依存関係

**メソッドとクラスは、明示的に正しく機能するために必要なすべての共同作業オブジェクトを要求します。** クラスのコンス トラクターは、クラスと適切に機能する有効な状態にするために必要であることを確認する機会を提供します。 これらのクラスがされている場合、これはのみ正しく機能が設定されている特定のグローバルまたはインフラストラクチャのコンポーネントを構築されと呼ばれることができますが、クラスを定義すると、*悪意を持つ*クライアントとします。 コンス トラクターのコントラクトを認証するには、クライアントにのみ必要な (可能性のある場合、何もクラスは既定のコンス トラクターだけを使用して)、指定されたものですが、結局のところ、オブジェクトの実行時に実際に必要でした別のものです。

明示的な依存関係の原則では、クラスとメソッドはされている正直でも機能するために必要な情報については、そのクライアント。 これにより、コードの詳細を自己文書化し、コーディング コントラクトよりわかりやすいユーザーがメソッドの形式で必要なものを提供する限りを信頼するようになるまたはコンス トラクターのパラメーターを使用するオブジェクトの動作正しく実行時にします。

### <a name="single-responsibility"></a>1 つの責任

1 つの責任の原則は、オブジェクト指向デザインに適用されますが、関心の分離と同様のアーキテクチャ原則とも考えられます。 オブジェクトは 1 つだけの責任である必要がありする必要がありますを変更する 1 つだけの理由を示します。 具体的には、その 1 つの役割を実行する方法を更新する必要がありますが、オブジェクトが変更する必要がありますのみ状況です。 この原則に続いて複数生成するために役立ちます疎結合し、モジュール式のシステムでは、さまざまな種類の新しい動作以降を実装する既存のクラスに追加の役割を追加することによってではなく、新しいクラスとして。 新しいクラスを追加するコードがないため、既存のクラスを変更するよりも安全では常にまだ、新しいクラスに依存します。

モノリシックなアプリケーションでは、アプリケーション内のレイヤーに高レベルで 1 つの責任の原則を適用おできます。 プレゼンテーション責任 UI プロジェクトのままにする、責任をインフラストラクチャ プロジェクト内で保持するかデータにアクセスします。 ビジネス ロジックは、ここで簡単にテストすることができ、その他の役割から個別に展開できるアプリケーション コア プロジェクトでは注意してください。

この原則はアプリケーションのアーキテクチャに適用され、その論理エンドポイントに要した、microservices を取得します。 指定されたマイクロ サービスは、単一の役割が必要です。 システムの動作を拡張する必要がある場合は、既存の責任を追加することによってではなく、追加の microservices を追加することによって行う通常お勧めします。

[Microservices アーキテクチャの詳細を表示します](http://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>自分で (ドライ) 繰り返さない

アプリケーションでは、これは、頻繁にエラーの原因としては、複数の場所で特定の概念に関連する動作を指定することを避ける必要があります。 ある時点で、要件の変更が必要になりますこの問題および可能性の変更を更新するに少なくとも 1 つの動作のインスタンスは失敗のシステム一貫性のない動作が発生します。

ロジックを複製するのではなくプログラミング構成要素でこれをカプセル化します。 この動作を 1 つの権限を構築し、この動作は、新しいコンス トラクターを使用してを必要とするアプリケーションの他の部分があるようにされます。

> [!NOTE]
> バインディングは、偶然にも繰り返しのみ動作では一緒にしないでください。 たとえば、両方が 2 つの異なる定数は、同じ値を持つからといってことを意味して 1 つだけの定数を持つ必要があります概念的には、さまざまなを参照する場合。

### <a name="persistence-ignorance"></a>永続性の無視

**持続性の無視が適用**(PI) を指す型永続化する必要があるが、そのコードが永続化テクノロジの選択による影響はありません。 .NET では、このような型とも呼ば Plain Old CLR Object (した poco から)、特定の基本クラスを継承または特定のインターフェイスを実装する必要がないためです。 持続性の無視が適用は、同じビジネス モデルをアプリケーションにさらに高い柔軟性を提供する複数の方法で永続化できるため重要です。 永続化の選択肢が、別の 1 つのデータベース テクノロジからの時間の経過と共に変更可能性がありますまたは永続化の追加フォームが任意のアプリケーションの開始だけでなく必要な可能性があります (たとえば、Redis キャッシュまたはに加え、Azure DocumentDb を使用して、リレーショナル データベース)。

この原則に反したのいくつかの例は次のとおりです。

-   必要な基本クラス

-   必要なインターフェイスの実装

-   自体 (有効なレコードのパターン) などの保存を担当するクラス

-   必要な既定のコンス トラクター

-   Virtual キーワードを必要とするプロパティ

-   永続化に固有の必要な属性

クラスがある上記の機能や動作のいずれかの要件は、永続化するために、型や、選択した後で新しいデータ アクセス方法を採用することが難しくなります、永続化テクノロジ間の結合を追加します。

### <a name="bounded-contexts"></a>範囲指定されたコンテキスト

**コンテキストの境界を付けられた**ドメイン デザインから中央、パターンには、します。 概念の個別のモジュールに分割する、大規模なアプリケーションや組織にへの対応の複雑さの機能を提供します。 各概念モジュールが、他のコンテキストから分離されているコンテキストを表します (このため、制限される)、し、個別に展開できます。 各境界のあるコンテキストでは、空き、内の概念に関する独自の名前を選択することが理想的で、独自の永続化ストアに排他アクセス権限が必要です。

少なくとも、個々 の web アプリケーションは必要があるデータベースを共有する他のアプリケーションとのではなく、そのビジネス モデルの独自の永続化ストアで、独自の境界のあるコンテキストに努めています。 これにより、ビジネス ロジックの共有データベースではなくプログラム インターフェイスは、使用に範囲指定されたコンテキスト間の通信が発生しをイベントが行われる変更に合わせて配置します。 また、独自の個々 の境界のあるコンテキストとして実装されることをお勧め microservices にコンテキストのマップを密接に制限されます。

> ### <a name="references--modern-web-applications"></a>参照: 最新の Web アプリケーション
> - **関心の分離**  
> <http://deviq.com/separation-of-concerns/>
> - **カプセル化** <http://deviq.com/encapsulation/>
> - **依存関係の逆転原則**  
> <http://deviq.com/dependency-inversion-principle/>
> - **明示的な依存関係の原則**  
> <http://deviq.com/explicit-dependencies-principle/>
> - **自分で繰り返さない**  
> <http://deviq.com/don-t-repeat-yourself/>
> - **永続性の無視**  
> <http://deviq.com/persistence-ignorance/>
> - **範囲指定されたコンテキスト**  
> <https://martinfowler.com/bliki/BoundedContext.html>

> [!div class="step-by-step"]
[前](choose-between-traditional-web-and-single-page-apps.md) [次へ] (共通-web-アプリケーション-architectures.md)