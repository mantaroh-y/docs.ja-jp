---
title: '方法: ステート マシン ワークフローを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8098ab4b056ad6375c248e803134c35d67e3f27b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519822"
---
# <a name="how-to-create-a-state-machine-workflow"></a>方法: ステート マシン ワークフローを作成する
ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。 など両方の組み込みのアクティビティを使用するワークフローを作成する手順をこのトピックで、<xref:System.Activities.Statements.StateMachine>アクティビティ、およびカスタム アクティビティ、前の[方法: アクティビティ作成](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)トピック。 このワークフローは、数値推測ゲームをモデル化しています。  
  
> [!NOTE]
>  チュートリアル入門の各トピックは、前のトピックに応じて異なります。 このトピックを完了する必要がありますを完了して[方法: アクティビティ作成](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)です。  
  
> [!NOTE]
>  このチュートリアルの完成版をダウンロードするを参照してください。 [Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。  
  
### <a name="to-create-the-workflow"></a>ワークフローを作成するには  
  
1.  右クリック**NumberGuessWorkflowActivities**で**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の**します。  
  
2.  **インストール済み**、**一般的な項目**ノードの **ワークフロー**します。 選択**アクティビティ**から、**ワークフロー**一覧。  
  
3.  型`StateMachineNumberGuessWorkflow`に、**名前**ボックスし、をクリックして**追加**します。  
  
4.  ドラッグ、 **StateMachine**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベルをワークフロー デザイン サーフェイス。  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>ワークフロー変数および引数を作成するには  
  
1.  ダブルクリック**StateMachineNumberGuessWorkflow.xaml**で**ソリューション エクスプ ローラー**まだ表示されていない場合に、デザイナーでワークフローを表示します。  
  
2.  クリックして**引数**を表示するワークフロー デザイナーの左下で、**引数**ウィンドウ。  
  
3.  クリックして**引数の作成**です。  
  
4.  型`MaxNumber`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、 **Int32** から**引数の型**ドロップダウン リスト、および引数を保存するには ENTER キーを押します。  
  
5.  クリックして**引数の作成**です。  
  
6.  型`Turns`に、**名前**新しく追加された下にあるボックス`MaxNumber`引数で、**アウト**から、**方向**選択ドロップダウンリスト**Int32**から、**引数の型**ドロップダウン リスト、および ENTER キーを押します。  
  
7.  クリックして**引数**を閉じるアクティビティ デザイナーの左下で、**引数**ウィンドウ。  
  
8.  クリックして**変数**を表示するワークフロー デザイナーの左下で、**変数**ウィンドウ。  
  
9. クリックして**変数作成**です。  
  
    > [!TIP]
    >  ない場合は**変数の作成**ボックスが表示されたら、をクリックして、<xref:System.Activities.Statements.StateMachine>ことを選択するには、ワークフロー デザイナー画面上のアクティビティ。  
  
10. 型`Guess`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。  
  
11. クリックして**変数作成**です。  
  
12. 型`Target`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。  
  
13. クリックして**変数**を閉じるアクティビティ デザイナーの左下で、**変数**ウィンドウ。  
  
### <a name="to-add-the-workflow-activities"></a>ワークフロー アクティビティを追加するには  
  
1.  クリックして**State1**をオンにします。 **プロパティ ウィンドウ**、変更、 **DisplayName**に`Initialize Target`します。  
  
    > [!TIP]
    >  場合、**プロパティ ウィンドウ**が表示されている、選択**プロパティ ウィンドウ**から、**ビュー**メニュー。  
  
2.  新しく名前を変更 をダブルクリックします**Initialize Target**ワークフロー デザイナーの展開の状態。  
  
3.  ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**エントリ**状態のセクション。 型`Target`に、**に**ボックスし、次の式を**c# 式を入力します**または**VB の式を入力します。** ボックス。  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  場合、**ツールボックス**ウィンドウが表示されない場合、選択**ツールボックス**から、**ビュー**メニュー。  
  
4.  全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。  
  
5.  ドラッグ、**状態**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**ワークフロー デザイナーにそのポインターを合わせると、 **Initialize Target**状態。 周囲に 4 つの三角形が表示されることに注意してください、 **Initialize Target**新しい状態が上にあるときの状態。 すぐ下にある三角形の新しい状態をドロップ、 **Initialize Target**状態。 これは、ワークフローの新しい状態しからの移行を作成、 **Initialize Target**新しい状態を状態。  
  
6.  をクリックして**State1**ことを選択するには、変更、 **DisplayName**に`Enter Guess`、ワークフロー デザイナーの展開の状態をダブルクリックします。  
  
7.  ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**エントリ**状態のセクション。  
  
8.  次の式を入力、**テキスト**プロパティ ボックスの**WriteLine**します。  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**終了**状態のセクション。  
  
10. 型`Turns`に、**に**ボックスと`Turns + 1`に、 **c# 式を入力します**または**VB の式を入力します。** ボックス。  
  
11. 全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。  
  
12. ドラッグ、 **FinalState**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**、上にマウス ポインター、 **Enter Guess**状態、および削除右側に表示される三角形に、 **Enter Guess**状態間の遷移が作成されるように**Enter Guess**と**FinalState**します。  
  
13. 遷移の既定の名前は**T2**します。 それを選択し、設定するには、ワークフロー デザイナーで遷移をクリックします。 その**DisplayName**に**Guess Correct**します。 クリックし、選択、 **FinalState**、2 つの状態のどちらにも重ならずに表示される完全な遷移名用の空きができるように、右にドラッグします。 これにより、チュートリアルの残りの手順をより簡単に実行できます。  
  
14. 新しく名前を変更 をダブルクリックします**Guess Correct**して展開ワークフロー デザイナーで遷移します。  
  
15. ドラッグ、 **ReadInt**からのアクティビティ、 **NumberGuessWorkflowActivities**のセクション、**ツールボックス**にドロップし、**トリガー**セクション移行。  
  
16. **プロパティ ウィンドウ**の**ReadInt**アクティビティで、「`"EnterGuess"`に引用符を含む、 **BookmarkName**プロパティ値ボックス、および種類`Guess`に、**結果**プロパティ値ボックス  
  
17. 次の式を入力、 **Guess Correct**遷移の**条件**プロパティ値ボックス。  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. 全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。  
  
    > [!NOTE]
    >  トリガー イベントが受け取られ、<xref:System.Activities.Statements.Transition.Condition%2A> (存在する場合) が `True` と評価される場合に遷移が発生します。 この遷移で場合、ユーザーの`Guess`ランダムに生成されたと一致する`Target`に制御が渡されます。 その後、 **FinalState** 、ワークフローが完了するとします。  
  
19. 推定値が正しいかどうか、によって、ワークフローが遷移するか、 **FinalState**またはに戻す、 **Enter Guess**もう一度実行状態。 両方の遷移は、ユーザーの推定値経由で受信を待機するのと同じトリガーを共有、 **ReadInt**アクティビティ。 これは、共有遷移と呼ばれます。 共有遷移を作成するには、開始を示す円をクリックします。、 **Guess Correct**移行し、目的の状態にドラッグします。 自己の遷移を遷移がここでは、そのための開始点をドラッグ、 **Guess Correct**の一番下にドロップしつつ、移行、 **Enter Guess**状態。 遷移を作成した後、ワークフロー デザイナーで選択し、設定、 **DisplayName**プロパティを**Guess Incorrect**します。  
  
    > [!NOTE]
    >  共有遷移も作成できますから、遷移デザイナー内をクリックして**追加共有トリガー遷移**から目的のターゲットの状態を選択し、遷移デザイナーの下部にある、 **使用可能な状態の接続に**ドロップダウンします。  
  
    > [!NOTE]
    >  遷移の <xref:System.Activities.Statements.Transition.Condition%2A> が `false` と評価された場合 (またはトリガーを共有する遷移すべての状態が `false` と評価された場合)、遷移は行われず、その状態からのすべての遷移のすべてのトリガーが再スケジュールされます。 このチュートリアルでは、条件の構成方法 (推定値が正しいか間違っているかを判断する特定のアクションが用意されています) により、この状況は発生しません。  
  
20. ダブルクリックして、 **Guess Incorrect**して展開ワークフロー デザイナーで遷移します。 なお、**トリガー**は既に同じに設定**ReadInt**アクティビティで使用された、 **Guess Correct**遷移します。  
  
21. 次の式を入力、**条件**プロパティ値ボックス。  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. ドラッグ、**場合**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**アクション**遷移のセクション。  
  
23. 次の式を入力、**場合**アクティビティの**条件**プロパティ値ボックス。  
  
    ```
    Guess < Target  
    ```  
  
24. 2 つをドラッグして**WriteLine**アクティビティから、**プリミティブ**のセクション、**ツールボックス**で 1 つがされるようにドロップし、**し**のセクション**場合**、もう 1 つは、 **Else**セクション。  
  
25. をクリックして、 **WriteLine**内のアクティビティ、**し**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。  
  
    ```
    "Your guess is too low."  
    ```  
  
26. をクリックして、 **WriteLine**内のアクティビティ、 **Else**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。  
  
    ```
    "Your guess is too high."  
    ```  
  
27. 全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。  
  
     次の例は完成したワークフローを示しています。  
  
     ![完成したステート マシン ワークフロー](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>ワークフローをビルドするには  
  
1.  Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。  
  
     ワークフローを実行する方法について、次のトピックをご覧ください[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)します。 既に完了している場合、[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)さまざまなスタイルのワークフロー ステップ、状態マシン ワークフローは、この手順を使用してを実行してに進んで、 [のアプリケーションをビルドして、実行](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)の[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation プログラミング](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [ワークフローの設計](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [チュートリアル入門](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [アクティビティを作成する方法](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [ワークフローを実行する方法](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
