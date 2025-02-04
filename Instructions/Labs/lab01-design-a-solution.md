---
lab:
    title: 'Lab 01: Design the solution'
    module: 'Module 01: Introduction to Power Platform'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# ラボ01：ソリューションを設計する

このラボでは、PowerPlatformに実装できるものにアイデアを形作ります。 その一環として、組織内の他の人と会って、アイデアをどのように実装できるかをより明確にします。 この情報を使用して、構築する必要のあるアプリケーションと自動化を特定します。

## あなたが学ぶこと

  - アイデアのギャップと要件を特定する方法

  - 問題のあるドメインをPowerPlatformにマッピングする方法

  - データモデルに必要なテーブルを決定する方法

## 高レベルのラボ手順

  - 演習1 - シナリオの概要

  - 演習2 - 同僚や施設のスタッフへのインタビューからニーズを抽出する

  - 演習3 - データモデルを設計する

  - 演習4 - 必要なアプリと自動化を特定する

  - 演習5 - ユーザーストーリー、アプリUIのモックアップ

## 詳細な手順

### 演習1：シナリオの概要

この演習では、この一連のラボで構築するシナリオについて理解します。

#### タスク1：シナリオを読む

次のシナリオを読み、後で重要になると思われる重要なポイントをメモします。

> あなたはLamnaHealthcare Companyの従業員であり、請求部門で働いています。
> 
> 仕事から車に向かって歩いていると、出口のそばにある会社のデジタル署名がまだ2019年の大会の参加者を歓迎していることに気づきました。 あなたは誰かに言うでしょう、しかしあなたは誰に言うべきか分かりません。 ですから、あなたはあなたの会社で修正されるべきであるが誰にも言う方法がない何かを見つけることがよくあります。 
> 
> あなたが交通の中で座って家に帰っていたとき、あなたは考えを持っていました。 このようなことを報告するために使用できるアプリがあったとしたらどうでしょうか。 場所、カテゴリ、さらには問題の写真を報告して、誰かが簡単に見つけて修正できるようにすることができます。 唯一の問題は、聞いている人に報告してもらうかどうかでした。
> 
> 翌日、あなたは施設部門で友人と会い、アイデアを共有しました。 今日、彼女がこれらのような問題を報告して修正することができる調整された方法がないので、彼女も興奮していました。 彼女は、それらがさまざまな部門に関与する頻度を説明し、ステータスを確認するためにルーティングおよびフォローアップする必要があります。 彼女は商用オプションを検討していましたが、それらは複雑すぎて柔軟性がなく、過剰に設計されており、高価でした。 ただし、彼女は、市民が問題を報告するために都市で使用されている311システムの例を示しました。 その例に基づいて、Company311と呼ぶことにしました。

### 演習2：インタビューからニーズを抽出する

この演習では、数人の同僚とのインタビューのテキストを確認します。 これらのインタビューのそれぞれで、Company 311ソリューションのアイデアを共有し、同僚からフィードバックを得ました。 この情報を使用して、ソリューション設計を形成する必要があります。

#### タスク1：面接\#1メモ

同僚との次のディスカッションを確認し、やり取りから学んだ重要なことをメモします。 このインタビューは、あなたが友達である同じ部門の同僚からのものです。

> **You**:   私たちが話し合った311社のアイデアについてあなたの考えを聞きたいと思いました。 そのアプリの作成を始めようと思っています。 問題報告を提出する際に何を含める必要があると思いますか？
> 
> **Coworker**: 問題がどこにあるかを把握する必要があります。建物がたくさんあります。 どの部門がそれを修正する必要があります。 ああ、そして写真。
> 
> **You**: 問題がどこにあるかを特定するには、建物で十分だと思いますか？
> 
> **Coworker**: たぶん、彼らが建物のどこにいるのかを説明できるように...
> 
> **You**: 問題を報告した後、何が起こると思いますか？
> 
> **Coworker**: もちろんそれを修正するためにそれら\!  
> 
> **You**: いいえ、アプリでは、[問題の送信]をクリックすると何が表示されますか？
> 
> **Coworker**: 誰かがそれを手に入れ、それが作業中であり、いつ修正されるのか知りたいです。 実際、常にではありませんが、ほとんどの場合...通知を受け取ることを選択させてください。
> 
> **You**: それで、おそらくあなたの提出されたすべてのアイテムのリスト？
> 
> **Coworker**: うん、それは素晴らしいだろう\! 
> 
> **You**: 完璧です、アプリを試すことができるときにお知らせします\! 

これを読み終えたら、メモを次のタスクのメモと比較して、何か見落としがないかどうかを確認します。

#### タスク2：面接\#1メモ

このタスクでは、インタビューからのメモを比較します\#1メモ

以下はインタビュー\#1からのメモです

  - 問題ごとに建物を選択できる必要があります

  - 問題を提出するときに、どの部門がそれを修正する必要があるかを把握する必要があります

  - 問題の写真が必要

  - 建物内の問題の場所の自由形式のテキスト説明が必要です

  - 完了時に通知を受け取るかどうかを示す方法が必要

  - 提出したすべての問題とそのステータスを確認する必要があります

#### タスク3：面接\#2

同僚との次のディスカッションを確認し、やり取りから学んだ重要なことをメモします。 このインタビューは、あなたが友達である施設管理の同僚からのものです。 あなたは問題報告のほとんどが彼らによって処理されると信じています。

> **You**: 私たちが話し合った311社のアイデアについてあなたの考えを聞きたいと思いました。 そのアプリの作成を始めようと思っています。 人々が問題報告を提出するときに何を含める必要があると思いますか？
> 
> **Coworker**: できるだけ詳細に、写真がいいでしょう。 多くの場合、問題の非常に漠然とした兆候であるレポートを受け取ります。写真があれば、1000倍鮮明になるということです。
> 
> **You**: 問題を解決すると思われる部門を選択できるようにすることについてどう思いますか？
> 
> **Coworker**: 今それは面白いです\! ほとんどの人は誰がそれを修正するのかわからず、それはただの魔法だと思います。 部門なしで問題レポートを提出するだけで、施設の担当者の1人が問題に対処するために必要な部門を割り当てることをお勧めします。
> 
> **You**: 完全\! 報告されるすべての問題を修正しましたか？
> 
> **Coworker**: それらの多くは重複しており、修正されません。 他の人はコストがかかりすぎて、マネージャーの承認を得る必要があります。 それらが承認されない場合、それらは修正されません。
> 
> **You**: 今日、その承認をどのように行いますか？
> 
> **Coworker**: 費用がかかると思われるものを入手した場合は、承認を得るためにマネージャーを追跡する必要があります。すぐに入手できない場合は、覚えるまで取っておかれることがあります。
> 
> **You**: わかりました。役立つ可能性のある承認を含めることができれば。 アプリを試すことができたらお知らせします\!

これを読み終えたら、メモを次のタスクのメモと比較して、何か見落としがないかどうかを確認します。

#### タスク4：インタビュー\#2メモ

このタスクでは、インタビュー\#2のメモを私たちのメモと比較します。

以下はインタビューからの\#2メモ

  - 写真を持っていると役に立ちます

  - 部門はユーザーが提供するのではなく、送信後に割り当てる必要があります

  - 特定の金額を超える承認が必要です。自動化に役立ちます

### 演習3：データモデルを設計する

この演習では、構築するアプリをサポートするデータモデルを作成します。

#### タスク1：データについてすでに知っていることを評価する

このタスクでは、提案されたソリューションに関してすでに収集した情報を評価し、必要なデータテーブルとそれらがどのように関連しているかを特定しようとします。 必要に応じて、データモデルを描画する次のタスクと同時にこのタスクを実行できます。

  - ソリューションによって管理される主なデータを特定します。 これは通常、1つまたは2つのテーブルになり、作成するアプリの焦点になります。 他のデータは通常、これらのテーブルに関連し、これらのテーブルをサポートします。

  - シナリオをサポートするために必要な関連テーブルを特定します。

  - リレーションシップを使用してテーブルを接続する方法を特定します。
  
  - 何が列で何がテーブルであるかを評価します。 たとえば、写真をどのように保存するか、建物内の場所をどのように保存する必要がありますか？

#### タスク2：ドラフトデータモデルを描画する

利用可能なツールを使用してください。 ホワイトボード、Visio、PowerPoint、OneNoteを使用することも、紙とペンを使用することもできます。 ここでの目標は、完璧な画像ではなく、データモデルがどのように見えるかを考え、他の人と共有してアイデアを得ることができるようにすることです。 このデータモデルは通常、メーカーポータルでテーブルを作成する際のガイドになります。 もちろん、ポータルでテーブルの作成を開始することもできますが、図を作成すると、より慎重に計画を立てることができます。

1.  関係や関係の振る舞いを含むデータモデルを描画します。 図面は次の例のようになりますが、Company311ソリューション用である必要があります。
    
    ![Whiteboard drawing of an example data model containing entities Course and Module and 1:N parental raltionship from Course to Module](01/media/image1.png)


#### タスク3：データモデルを比較する

1.  前のタスクで作成したデータモデルを、準備したデータモデルと比較します。 大きな違いがある場合は、インストラクターと話し合う必要があります。

![A close up of text on a whiteboard with a data model showing problem report, department and building](01/media/image2.png)

### 演習4：必要なアプリと自動化を特定する

この演習では、収集した情報を確認し、ソリューションを実装するために必要なアプリと自動化を決定します。 目標は、アプリケーションまたは自動化のすべての機能を特定することではなく、1つのアプリまたは10のアプリが必要かどうか、およびそれらがどのスタイルのアプリであるかを特定することです。

#### タスク1：必要なアプリを評価する

このタスクでは、ユーザーがアプリケーションをどのように操作するかを確認し、1つまたは複数のアプリケーションが必要かどうか、およびそれらがどのスタイルになるか（つまり、キャンバスまたはモデル駆動）を決定します。 これを実現する方法に対する正しい答えは1つではありませんが、正しい質問をすることで、ユーザーにとってより良いソリューションを設計できます。 次の手順を実行するときに、Company 311ソリューションについてメモを取ります。

1.  アプリを使用するユーザーを特定します。

2.  ユーザーの各セットがアプリにアクセスする方法を特定します。 それは主にモバイルデバイスまたはデスクトップ用ですか？

3.  提供する全体的な機能のうち、一部のユーザーが常に使用する特定のサブセットはありますか？

4.  あるタイプのアプリケーションと別のタイプのアプリケーションに適したデバイスの使用法はありますか？

5.  モデル駆動型アプリはデータ管理に最適です。 モデル駆動型アプリにより適した機能はありますか？

6.  上記の質問への回答を考慮して、作成するアプリの数、アプリの種類、各アプリの機能と使用者をメモします。

#### タスク2：アプリに関するメモを比較する

このタスクでは、前のタスクのメモを準備したメモと比較する必要があります。 大きな違いがある場合は、インストラクターと話し合う必要があります。

1.  アプリを使用するユーザーを特定する:
    
      - グループ1 - 会社のすべての従業員
    
      - グループ2 - 施設のスタッフと問題を解決するさまざまな部門の人

2.  ユーザーのセットごとに、主にモバイルデバイスまたはデスクトップからアクセスしますか？
    
      - グループ1 - おそらく主にモバイルデバイス上
    
      - グループ2 - 主にデスクトップ上にありますが、モバイル上にある場合もあります

3.  提供する全体的な機能のうち、一部のユーザーが常に使用する特定のサブセットはありますか？
    
      - グループ1 – 最も重要な機能は、問題レポートの送信です。建物や部門のリストを管理するために何もしません。
    
      - グループ2 - 最も重要な機能は、問題レポートのルーティングと解決、および建物とアパートに関連する参照データの管理です。

4.  あるタイプのアプリケーションと別のタイプのアプリケーションに適したデバイスの使用法はありますか？
    
      - モバイルデバイスからのカメラまたは写真のアップロードの簡単な使用

5.  モデル駆動型アプリに適したデータ管理機能はありますか？
    
      - 建物やアパートの参照データの管理は、モデル駆動型アプリで簡単に実行できます。
    
      - さまざまなユーザーへの問題レポートのルーティングと割り当ては、モデル駆動型アプリで簡単に処理できます。

6.  上記の質問への回答を考慮して、作成するアプリの数、アプリの種類、各アプリの機能と使用方法をメモします。
    
      - アプリ1 - Company 311 - これは、新しい問題レポートを送信し、送信された問題レポートのリストを表示するために使用されるキャンバスアプリケーションになります。
    
      - アプリ2 – Company 311 Admin – これは、問題レポートをルーティングおよび解決するすべてのユーザーが使用するモデル駆動型アプリケーションになります。 このアプリケーションは、建物や部門リストなどのすべての参照データも管理します。

### 演習5：ユーザーストーリー、アプリUIモックアップ

この演習では、ユーザーがアプリを操作して問題レポートを送信することを説明するユーザーストーリーを確認します。

#### タスク1：ユーザーストーリー

次のユーザーストーリーを確認する:

> ユーザーとして、アプリをすばやく開いて問題レポートを送信できるようにしたいと考えています。 私は建物を選び、問題がどこにあるかを説明する場所を与えることができるはずです。 アプリでは、1行のタイトルと問題の詳細を提供できるはずです。 オプションで写真を提供できるはずです。 簡単に切り替えて、すでに送信した問題のリストとそのステータスを確認できるはずです。

1.  ホワイトボード、Visio、OneNote、さらには紙とペンなど、利用可能なツールのいずれかを使用して、上記のユーザーストーリーを満たすためにユーザーインターフェイスのモックアップを描画します。

2.  モックアップの描画が完了したら、次のタスクに進み、提供されているタスクと比較します。

#### タスク2：モックアップを比較する

以下は、新しいアイテムの追加とマイレポートリストの両方を示すUIモックアップの例です。 これがどのように見えるべきかについての単一の答えはありません、そしてあなたが思いつくことができる多くの例があるかもしれません。 UIマークアップの目標は、実際にビルドしなくても、ビルドしたいものをすばやくデモンストレーションして誰かに見せることができるようにすることです。 使用したツールによっては、モックアップを進化させながらすばやく変更を加えることができます。 マークアップは、手間をかけずに実際のアプリケーション画面をすばやく構築するために使用されます。

![A close up of text on a whiteboard showing a UI mockup of the add and my reports list](01/media/image3.png)
