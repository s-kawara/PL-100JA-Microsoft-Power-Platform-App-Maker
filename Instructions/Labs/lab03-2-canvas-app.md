---
lab:
    title: 'Lab 03.2: Canvas app'
    module: 'Module 03: Create a canvas app'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# ラボ03.2：Canvasアプリ

このモジュールでは、会社の従業員が問題レポートを送信するためのキャンバスアプリを設計および構築します。

## あなたが学ぶこと

  - ビルド済みのコンポーネントライブラリをインポートして使用する
  - Power Apps のキャンバスアプリを作成する
  - データソースに接続する
  - データをフィルタリングする
  - データ行を作成する
  - データ行のある画像を使用する
  - Canvas PowerアプリをMicrosoft Teamsに埋め込む

## 高レベルのラボ手順

  - 会社のコンポーネントをインポートする
  - アプリとレイアウトのメイン画面（アイテムのリストを含む）を作成します
  - 新しいレポートを送信する
  - テスト
  - Microsoft Teamsにキャンバスアプリを埋め込む

## 前提条件

* **ラボ02.1：データモデルとモデル駆動型アプリ**を完了している必要があります

## 詳細な手順

  ### 演習1：キャンバスアプリケーションを作成する

この演習では、共有コンポーネントを使用してソリューションをインポートし、問題レポートテーブルのビューを作成して、キャンバスアプリケーションを作成します。

#### タスク1：コンポーネントライブラリソリューションをインポートする

このタスクでは、共有コンポーネントソリューションを環境にインポートします。 この共有コンポーネントライブラリは、会社の別のチームによって作成されました。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、**Import** をクリックします。

![A Screenshot with an arrow pointing to the import button](03-2/media/image1.png)

3.  **Browse** をクリックします。

4.  コースリソースフォルダに移動し、**Shared components** ソリューションを選択して、**Open** をクリックします。

5.  **Next** をクリックします。

6.  **Import** をクリックして、インポートが完了するのを待ちます。

7.  **Publish All Customizations** をクリックして、公開が完了するのを待ちます。

8.  インポートした **Shared components** ソリューションが表示されます。 クリックして、**Shared components** ソリューションを開きます。

9. ソリューションには1つの項目が含まれている必要があります。（**Lamna Healthcare Shared Components**）

![A screenshot of the shared components window with the Lamna Healthcare shared components item](03-2/media/image2.png)

> [!IMPORTANT]
> ソリューションの一部としてアプリをインポートしても、コンポーネントライブラリにアプリが追加されない場合があるという問題があります。 次の手順は、問題を解決するために設計されています。

10. **Apps** に移動し、**Lamna Healthcare Shared Components App** を選択します。

![A Screenshot with an arrow pointing to the edit button](03-2/media/image2-1.png)

12. **Region/Country** を選択し、プロンプトが表示されたら **Get started** をクリックします。
    
    > [!Note]
    >
    > アプリが編集モードで開いている場合、プリローダーコンポーネントには読み込みアイコンが表示されますが、実際には何かが読み込まれるのを待っていないため、次の手順に進みます。
13. アプリが開いたら、**File** > **Save As** をクリックします。
14. アプリを **Lamna Healthcare Share Components A** として保存します。

![A screenshot with a border around the app name saved as Lamna Healthcare Shared Components A](03-2/media/image2-2.png)

14. **OK** をクリックします。
15. ブラウザの **Lamna Healthcare Shared Components** タブを閉じます。

#### タスク2：ビューを作成する

このタスクでは、現在のユーザーのProblem Reportを表示するビューを作成します。 後で、このビューをキャンバスアプリのフィルター機能で使用します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **Problem Reports** テーブルを探し、開きます。

4.  **Views** タブを選択し、クリックして **Active Problem Reports** ビューを開きます。

![A Screenshot with an arrow pointing to the active problem reports view button](03-2/media/image3.png)

5.  **Edit filters** をクリックします。

![A Screenshot with an arrow pointing to the edit filters button](03-2/media/image4.png)

6.  フィルタを **Created By Equals current user** に変更し、**OK** をクリックします。

![A screenshot of the edit filters window](03-2/media/image5.png)

7.  Save ボタンの横にある山形ボタンをクリックして、**Save As** を選択します。

![A Screenshot with an arrow pointing to the save as button](03-2/media/image6.png)

8.  **Name** に **My Reports** と入力し、**Save** をクリックします。

9.  **Publish** をクリックして、公開が完了するのを待ちます。

10. ブラウザタブの **Back** ボタンをクリックして、Problem Report テーブルの詳細に戻ります。

#### タスク3：ユーザーアプリケーションを作成する

このタスクでは、電話のフォームファクターを使用してキャンバスアプリケーションを作成します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **+ New | App | Canvas app** をクリックします。

![A Screenshot with an arrow pointing to the new button with the drop down menu under app upon and a border around the canvas app button](03-2/media/image7.png)

4.  **Company 311 Phone App** と入力し、フォーマットとして **Phone** を選択して、**Create** をクリックします。

5.  **Skip** を選択します。

6.  ツリービューに移動し、**Screen1**　をダブルクリックします。

![A Screenshot with an arrow pointing to the screen 1 button](03-2/media/image9.png)

10. 画面の名前を **Main Screen** に変更します。 画面に意味のある名前を付けることは常に良い考えです。

![A screenshot with the Screen 1 name highlighted and renamed Main Screen](03-2/media/image10.png)

11. **Main Screen** を選択し、**挿入** をクリックします。

![A Screenshot with an arrow pointing to the plus icon for insert](03-2/media/image11.png)

12. **Get more Components** を選択します。

![A screenshot with a border around the get more components button](03-2/media/image12-1.png)

13.  **Lamna Healthcare Shared Components A** ライブラリを展開し、**Header** と **Tab Control** を選択して、**Import** をクリックします。

![A screenshot of the import components window with Ta control and header selected](03-2/media/image12-2.png)

14.  **Library components** を展開し、**Header Control** と **Tab Control** を選択します。 これらは両方とも、ラボで以前にインポートしたライブラリのコンポーネントです。

![A screenshot with a border around the library components Header and Tab control](03-2/media/image12-3.png)

15. **Tab Control** を画面の下部に移動し、**Header Contro** を画面の上部に移動します。

16. **Header Control** を選択し、**Text** の値を **Company 311** に変更します。

![A screenshot of a border around the expression tab with the text value set to company 311](03-2/media/image13.png)

17. **Header Control** の**Height** を **75** に設定します。

    ![Set Height - Header](03-2/media/image37.png)

18. メイン画面を右クリックして、**Duplicate screen** を選択します。

![A screenshot with a border around the duplicate screen button](03-2/media/image14.png)

18. 新しい画面の名前を **New Reports Screen** に変更します。

19. **Tree view** を選択し、**App** を選択して、**OnStart** の値を次の式に変更します。 この数式は、My Tabs という名前の新しい変数を作成し、それをタブアイテムのテーブルに設定します。

```javascript
Set('My Tabs', Table( {
	Label: "My Reports",
	Screen: 'Main Screen',
	Icon: "",
	SelectedIcon:""
},
{
	Label: "New Report",
	Screen: 'New Reports Screen',
	Icon: "",
	SelectedIcon:""
}
))
```

> [!IMPORTANT]
> 式がコピーされると、引用符と二重引用符は、数式では無効な「スマート」な対応物に置き換えられることがあります。 上記の式をコピーして貼り付ける場合は、結果の数式にエラーが含まれていないことを確認してください。

![A screenshot of the copied expression into the expression tab](03-2/media/image15.png)

20. **Main Screen** で **Tab Control** を選択し、**Items** の値を **'My Tabs'** に変更します。

![A screenshot of the items value set to my tabs for Tab control](03-2/media/image16.png)

21. **SelectedColor ** の値を **WhiteSmoke** に変更します。

22. **New Report Screen** 内の **Tab Control** を選択し、アイテムの値を **'My Tabs'** に設定します。

23. **SelectedColor** の値を **WhiteSmoke** に変更します。

24. **App** の **…** ボタンをクリックし、**Run OnStart** を選択します。

![A screenshot of the run on start button coming from the ellipsis icon for see more under the app button](03-2/media/image17.png)

25. これで、追加した2つのタブがタブに表示されます。

![A screenshot of the two tabs you added](03-2/media/image18.png)

26. **File** をクリックしてから、**Save** をクリックします。
27. **<- back** ボタンをクリックします。

28. このページから離れないでください。

### 演習2：私のレポート

この演習では、現在ログインしているユーザーによって作成されたレポートを表示するギャラリーを追加します。

#### タスク1：ギャラリーを追加する

1.  **Main Screen** を選択し、**Insert** タブに移動し、**Gallery** をクリックして、**Vertical** を選択します。

![A Screenshot with an arrow pointing to the vertical gallery option](03-2/media/image19.png)

2.  新しいギャラリーの名前を**My Reports Gallery** に変更します。

3.  **My Reports Gallery** のサイズと位置を変更し、画面が下の画像のようになっていることを確認します。

![A screenshot of the my reports gallery selected](03-2/media/image20.png)

4.  **My Reports Gallery** を選択し、**Properties** ペインに移動して、**Data Source** に **Problem Reports** を選択します。 Problem Reportが表示されない場合は、**See all tables** または **Search** をクリックしてテーブルを検索してください。

![A screenshot of the my reports gallery window and the properties pane with problem reports selected for data source](03-2/media/image21.png)

5.  **View** 用に作成した**My Reports** ビューを選択します。

6.  **Edit fields** をクリックします。 

![A Screenshot with an arrow pointing to the edit button](03-2/media/image22.png)

7.  Subtitle1を **statuscode** に変更します。 これはステータス理由の列です。

![A screenshot of a border around subtitle 1 changed to the correct name](03-2/media/image23.png)

8.  **File** をクリックしてから、**Save** をクリックします。

9.  **<- Back** ボタンをクリックします。

10. このページから離れないでください。

### 演習3：レポートの削除を許可する

この演習では、割り当てられていないレポートを削除できるようにします。 これにより、ユーザーは誤って作成されたレポートを簡単に削除できます。

#### タスク1：削除を許可する

1.  **My Reports Gallery** を展開します。

2.  **My Reports Gallery** 内の **Icon** を選択します。

![A screenshot of the arrow icon inside the my reports gallery](03-2/media/image24.png)

3.  **Icon** の値を **Icon.Trash** に変更します。

![A screenshot of icon.trash typed into the expression tab](03-2/media/image25.png)

4.  **Visible** の値を次の式に変更します。 ステータスの理由が「新規」でない場合、この式はアイコンを非表示にします。

`If(Text(ThisItem.'Status Reason') = "New", true, false)`

![A screenshot of the expression tab with the relevant command pasted in](03-2/media/image26.png)

5.  アイコンがまだ選択されていることを確認してください。 **OnSelect** の値を次の式に変更します。 この式は、データソースからアイテムを削除します。

`Remove('Problem Reports', ThisItem)`

6.  **File** をクリックしてから、**Save** をクリックします。

7.  **<-** **Back** ボタンをクリックします。

8.  このページから離れないでください。

### 演習4：新しいレポートを追加する

この演習では、新しい問題レポートを送信するためのフォームを追加します。

#### タスク1：新しいレポートフォームを追加する

1.  **New Report Screen** を選択し、**Insert** タブに移動し、**Form** をクリックして、**Edit** を選択します。

![A screenshot of the inset tab and forms button selected](03-2/media/image27.png)

2.  フォームの名前を **New Report Form** に変更します。

3.  **New Report Form** を選択し、**Properties** ペインに移動して、**Data Source** の **Problem Report** を選択します。

4.  **Edit fields** をクリックします。

![A Screenshot with an arrow pointing to the edit fields button](03-2/media/image28.png)

5.  **Status Reason** 列を削除します。

![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the remove button](03-2/media/image29.png)

6.  **Created On** 列を削除します。

7.  **Location** 列を削除します。

8.  **+ Add field** をクリックします。

9.  **Details**、**Building**、**Department**、**Photo** を選択し、**Add** をクリックします。

![A screenshot of photo, details, building, and location selected in the fields window](03-2/media/image30.png)

10. フォームのサイズと位置を変更して、ページの大部分を占め、下部にボタンを配置するのに十分なスペースを残します。

![A screenshot of the form resized and reposition for room at the bottom for a button](03-2/media/image31.png)

11. **New Report Screen** を選択します。

12. **Insert** タブに移動し、**Button** を選択します。

13. ボタンの名前を **Submit Report** に変更します。

14. フォームの下にボタンを配置し、画面全体に広げます

15. **Submit Report** ボタンの **Text** プロパティを **Submit** に変更します。

16. Submit Report ボタンを選択し、**OnSelect** の値を次の式に変更します。 この式は、問題レポートテーブルに新しい行を作成します。

`SubmitForm('New Report Form') `

17. **New Report Form** を選択します。

18. **OnSuccess** の値を次の式に変更します。 この式は、新しい行が作成された後に通知を表示し、レコードの作成が成功するとフォームをクリアします。

`Notify("Created new problem report row");NewForm('New Report Form')`

19. **New Report Screen** を選択します。

20. **OnVisible** の値を次の式に設定します。 この数式は、画面が表示されたときに新しいフォームを作成します。

`NewForm('New Report Form')`

21. **File** をクリックしてから、**Save** をクリックします。
22. **Publish** をクリックします。
23. **Publish this version** をクリックして、公開が完了するのを待ちます。
24. **<-** **Back** ボタンをクリックします。
25. このページから離れないでください。


### 演習5：アプリケーションをテストする

この演習では、問題レポートを送信して作成したキャンバスアプリケーションをテストします。

#### タスク1：アプリケーションをテストする

1.  **Main Screen** を選択し、**Preview the app** をクリックします。

![A Screenshot with an arrow pointing to the play icon to preview the app](03-2/media/image32.png)

2.  アプリケーションが読み込まれ、作成したすべてのレポートがリストに表示されます。

![A screen of your loaded application](03-2/media/image33.png)

3.  **New Report** タブを選択します。 

4.  **New Report Form** が読み込まれます。 フォームに記入し、**Photo** 列をクリックします。

5.  画像を選択します。

6.  **Submit** をクリックします。

7.  行が正常に作成され、成功メッセージが表示されます。

![A screen of the success message reading "created new problem report record"](03-2/media/image38.png)

8.  **My Reports** タブを選択します。

9.  作成した新しいレポートが表示されます。 **Delete** をクリックして削除をテストします。

![A Screenshot with an arrow pointing to the trash can icon to delete](03-2/media/image35.png)

10. 行を削除して、リストから削除する必要があります。

![A screenshot of the row deleted and removed from the list](03-2/media/image36.png)

11. プレビューを**閉じる**。
12. ブラウザタブを閉じて、アプリスタジオを**閉じます**。

### 演習6：Microsoft Teamsにキャンバスアプリを埋め込む

この演習では、スタッフがチーム内で直接問題をログに記録できるようにする方法として、以前に作成したCompany 311 Phone アプリを Microsoft Teams に追加します。

#### タスク1：会社311チームをセットアップする

このタスクでは、Lamna HealthcareCompanyの **Microsoft Teams** チームをセットアップします（これまでにセットアップしたことがない場合）。

1.  [Microsoft Teams](https://teams.microsoft.com) に移動し、以前に使用していたのと同じ資格情報でサインインします。 

2.  ようこそ画面で **Use the web app instead** を選択します。

![A screenshot of the Microsoft Teams web browser landing page with a border around the use the web app instead button](03-2/media/image-3-teams.png)

3.  Microsoft Teamsウィンドウが開いたら、ウェルカムメッセージを閉じます。

4.  **Teams** を選択します。
5.  左下隅で、**Join or create a teams** を選択します。

6.  **Create a teams** を選択します。

![A screenshot of a border around the join or create a team button and another border around the create a team button](03-2/media/image-3-createteam.png)

6.  **From scratch** を押します。 

7.  **Public** を選択します。

8.  チーム名に **Company 311** と入力し、**Create** を選択します。

9.  Company 311 にメンバーを追加するで **Skip** を選択します。
10. このページから離れないでください。


#### タスク2：チームにキャンバスアプリを追加する

1.  **Company 311** チームの **General** チャネルを選択します。

2.  ページの上部にある **+** 記号を押して、新しいタブを追加します。

![A screenshot of a border around the plus icon to add a new tab](03-2/media/image-3-addpowerbitab.png)

4.  **power** を検索し、結果から **Power Apps** を選択します。

5.  Power Appsをチームに追加するには、**Add** を選択します。

![A screenshot of the prompt to add Power Apps to Teams](03-2/media/image-3-powerappsteams.png)

6. このラボで以前に作成した **Company 311 Phone App** を選択します。

> [!IMPORTANT]
> アプリが表示されない場合は、アプリエディターに戻ってアプリを公開する必要があります

7. **Save** を選択します。

8. **Company 311** アプリが Microsoft Teams のタブに表示されます。

![A screenshot of the company 311 app appearing on a tab in Microsoft Teams](03-2/media/image-3-powerappinteams.png)



### 演習7：モデル駆動型アプリにキャンバスを埋め込む

この演習では、キャンバスアプリケーションを作成し、それをモデル駆動型アプリケーションに追加します。

#### タスク1：フォームにキャンバスアプリを追加する

1. [Power Apps maker portal](https://make.powerapps.com/) に移動し、練習環境にいることを確認します。 
2. **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。
3. **Building** テーブルを探し開きます。
4. **Forms** タブを選択し、クリックして、**Main** タイプの **Information** フォームを開きます。

![A Screenshot with an arrow pointing to the word information with a border around the form type being main](03-2/media/opentableform.png)

5. **form section** を選択します。
6. プロパティペインに移動し、クリックして **Formatting** を展開します。
7. **Columns** の値を **2** に変更します。

![A screenshot with a border around the number of columns](03-2/media/formsectioncolumns.png)

8. セクションがまだ選択されていることを確認してください。 **Table columns** タブを選択します。
9. **Show only unused table columns** チェックボックスをオフにして、**Name** 列をクリックします。

![A Screenshot with an arrow pointing to the name button](03-2/media/addcolumntoform.png)

10. これで、セクションの右側の列に列が表示されます。 フォームの **Name** 列を選択します。
11. **Hide label** チェックボックスをオンにして、**Save** をクリックします。

![A Screenshot with an arrow pointing to the save button](03-2/media/saveform.png)

12.  **Switch to classic** ボタンをクリックします。 プロンプトが表示されたら、**Skip** を選択します。

![A Screenshot with an arrow pointing to the switch to class button](03-2/media/switchtoclassic.png)

13.   フォームに追加した **Name** 列をダブルクリックします。
14.   **Controls** タブを選択し、**Add control** をクリックします。

![A Screenshot with an arrow pointing to the add control button](03-2/media/ex_7_addcontrol.png)

15.   **Canvas app** を選択し、**Add** をクリックします。
16.   **Customize** をクリックします。

![A Screenshot with an arrow pointing to the customize button](03-2/media/ex_7_customizeapp.png)

17.   新しいブラウザウィンドウまたはタブが開き、アプリスタジオが読み込まれます。
18.   このページから離れないでください。

#### タスク2：アプリをカスタマイズする

1.  **Form1**　を右クリックし、**Delete** を選択します。

![A screenshot with a border around the delete button](03-2/media/ex_7_deleteform.png)

2.  **File** をクリックします。
4.  **The cloud** を選択し、名前に **Model embed app** と入力して、**Save** をクリックします。

![A screenshot of the Save As prompt](03-2/media/ex_7_saveapp.png)

5.  **Settings** を選択します。
6.  **Display** を選択します。
7.  Width に **400** を入力します。

![A screenshot with a border around the width changed to 400](03-2/media/ex_7_displaywidth.png)

8.   ポップアップで **Apply** をクリックします。
9.   Width に **500** を入力します。
10.  ポップアップで **Apply** をクリックします。
11.  Settings ポップアップウィンドウを閉じます。
12.  ツリービューから **App** オブジェクトを選択します。
13.  **App** オブジェクトの **OnStart** を選択し、以下の式に設定します。 この数式は、レポートテーブルの現在のインデックスを追跡するための変数と、現在のアイテム行を追跡するための変数の2つを作成します。

```Set(currentIndex,1);Set(CurrentItem, Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex)))```

![A screenshot with a border around the app object changed to onstart and set to the aforementioned formula. There is also another border around the app button selected](03-2/media/ex_7_apponstart.png)

14.  **Insert** 挿入タブを選択し、**Media** をクリックして、**Image** を選択します。

![A screenshot of a border around the image button](03-2/media/ex_7_insertimage.png)

15.  追加した画像を選択し、**Image** の値を次の式に設定します。

```CurrentItem.Photo```

16.   **App** オブジェクトの **...** ボタンをクリックし、**Run OnStart** を選択します。

![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the run on start button](03-2/media/ex_7_runonstart.png)

17.  写真が見えるはずです。 ツリービューから**Image control** を選択します。

![A screenshot of an icon of a broken door](03-2/media/ex_7_imagephoto.png)

18. 画像の **X** 値を **0** に設定します。
19. 画像の **Y** 値を **0** に設定します。
20. 画像の **Width** 値を次の式に設定します。

```Parent.Width```

21. 画像の **Height** 値を次の式に設定します。

```Parent.Height```

22. **Properties** ペインに移動し、**Image position** に **Fill** を選択します。

![A Screenshot with an arrow pointing to the the file tab](03-2/media/ex_7_imageposition.png)

23. **File** をクリックし、**Save** をクリックして進行状況を保存します。
24. **<-** **Back** ボタンをクリックします。
25. このページから離れないでください。


#### タスク3：コントロールを追加する

1.  **Insert** タブを選択し、**Label** をクリックします。
2.  追加したラベルを選択し、**Text** 値を次の式に設定します。

```CurrentItem.Title```

3.  ラベルの **Height** 値を **60** に設定します。
4.  ラベルの **X** 値を **0 ** に設定します。
5.  ラベルの **Y** 値を次の式に設定します。

```Parent.Height -Self.Height```

6.  ラベルの **Width** 値を次の式に設定します。

```Parent.Width```

7.  ラベルの **Fill** 値を **RGBA（0、108、191、.5）** に設定します。
8.  ラベルの **Color** 値を **RGBA(255, 255, 255, 1)** に設定します。
9.  ラベルの **Align** 値を次の式に設定します。

```Align.Center```

10. これで、ラベルは次の画像のようになります。 タイトルが表示されない場合は、**App** オブジェクトの **...** ボタンをクリックして、**Run OnStart** をもう一度クリックします。

![A screenshot of the broken door icon now with a label](03-2/media/ex_7_resizedlabel.png)

11.  **Insert** タブで、**Icons** をクリックし、**Next** を選択します。
12.  追加したアイコンをダブルクリックして、名前を **Next Icon** に変更します。
13.  **Insert** タブで、**Icons** をクリックし、**Back** を選択します。
14.  追加した2番目のアイコンをダブルクリックし、名前を **Back icon** に変更します。
15.  ラベルの右側の上に **Next icon** をドラッグして配置します。
16.  ラベルの左側の上に **Back icon** をドラッグして配置します。
17.  アイコンは下の画像のようになります。

![A screenshot of the broken door icon with the next and back icons](03-2/media/ex_7_iconlocation.png)

18.  **Next icon** を選択し、**OnSelect** の値を次の式に設定します。

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex +1)```

19.  **Next icon** の **DisplayMode** 値を次の式に設定します。

```If(currentIndex = CountRows([@ModelDrivenFormIntegration].Item.'Problem Reports'), DisplayMode.Disabled, DisplayMode.Edit)```

20.  **Back icon** を選択し、**OnSelect** の値を次の式に設定します。

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex -1);```

21.  **Back icon** の **DisplayMode** 値を次の式に設定します。

```If(currentIndex > 1, DisplayMode.Edit, DisplayMode.Disabled)```

22. **File** をクリックしてから、**Save** をクリックします。

23. 新しいブラウザタブを開き、[Power Apps maker portal](https://make.powerapps.com/) ページに移動して、正しい環境にいることを確認します。

24. **Apps** を選択し、クリックして**Company 311 Admin** アプリケーションを起動します。

25. **Change Area** をクリックし、**Settings** を選択します。

![Change sitemap area - screenshot](03-2/media/image39.png)

26. **Buildings** を選択します。 

27. **Created On** 列の Buildings行を **Oldest to Newest** の順序で並べ替えます。 最も古いレコードをメモしておきます。

28. **Change Area** をクリックし、**Manage Problems** を選択します。

29. **Problem Reports** を選択します。 

30. **+New** をクリックします。

31. 名前に **Broken Tap** と入力し、**Building** 列で最も古い建物を選択して、詳細 列に**The Tap is broken and the water is continuously flowing.** と入力します。 **Photo** 列に任意の画像を追加します。

32. **Save** をクリックします。

33. **+New** をクリックします。

34. 名前に **Roof Leaks** と入力し、**Building** 列で最も古い建物を選択し、Details 列に**Water is seeping through the ceiling.** と入力します。 **Photo** 列に任意の画像を追加します。

35. **Save** をクリックして、モデル駆動型アプリのブラウザタブを閉じます。

36. **Model embed app** アプリケーションのCanvasAppEditorを開きます。 左側のメニューで**Data**アイコンを選択します。

    ![Select Data - screenshot](03-2/media/image40.png)

37. **Problem Reports** を見つけて**ellipsis** をクリックし、次に **Refresh** をクリックします。

38. **App** オブジェクトの **...** ボタンをクリックし、**Run OnStart** を選択します。

39. 左側のメニューから **Tree View** を選択し、**FormScreen** 画面を選択します。

40. **Play** をクリックします。

41. 次と戻るアイコンをクリックして、画像が変わることを確認します。

42. プレビューを閉じます。

43. **File** をクリックします。

44. **Save** をクリックします。

45. **Publish** をクリックします。

46. **Publish this version** をクリックして、公開が完了するのを待ちます。

47. アプリスタジオのブラウザウィンドウまたはタブを閉じます。

48. これで、**Field Properties** に戻るはずです。 **Web, Phone, Tablet** を選択し、**OK** をクリックします。

![A screenshot with a border around the canvas app item under control with web, phone, and tablet selected. There is also an arrow pointing to the ok button at the bottom of the window](03-2/media/ex_7_fieldproperties.png)

49. クラシックフォームエディタで **Save** をクリックします。
50. クラシックフォームエディタのブラウザウィンドウまたはタブを閉じます。
51. これで、最新のフォームエディタに戻るはずです。 **<-** **Back** ボタンをクリックします。

![A Screenshot with an arrow pointing to the back button](03-2/media/ex_7_backtomaker.png)

52. **Solutions** を選択します。
53. **Publish all customizations** をクリックして、公開が完了するのを待ちます。


#### タスク4：アプリをテストする

1. **Apps** を選択し、クリックして **Company 311 Admin** アプリケーションを起動します。

   ![A Screenshot with an arrow pointing to the company 311 admin application](03-2/media/ex_7_launchmodelapp.png)

2. **Problem reports** を選択し、クリックして問題レポート行の1つを開きます。
3. 問題に写真があることを確認し、**Building** ルックアップをクリックします。

   ![A Screenshot with an arrow pointing to the building lookup](03-2/media/ex_7_lookup.png)

4. Canvasアプリは、モデル駆動型アプリケーション内に読み込まれる必要があります。 [次へ] / [戻る]アイコンをクリックして、アプリケーションが期待どおりに動作することを確認します。

   ![A screenshot of the broken door icon in the context of the canvas app inside the Model-Driven Application](03-2/media/ex_7_canvasinmodel.png)

