---
lab:
    title: 'Lab 03.1: Create apps in Teams'
    module: 'Module 03: Create a canvas app'
---

> [!NOTE]
> Effective November 2020:
>
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>

ラボ03.1：チームでアプリを作成する
=================================

## Scenario

組織が未使用のコンピュータ周辺機器、電源コード、その他の電子機器を蓄積することは珍しくありません。 あなたの組織は、新しい機器を注文する前に、既存のデバイスとコンピュータ周辺機器を再利用するための措置を講じています。

You are asked to create an application where users can post devices they no longer need and browse through what their colleagues posted.

## 要件

1)	アプリケーションは Dataverse for Teamsを使用する必要があります。
2)	ユーザーは、新しいアイテムを作成したり、作成したアイテムを編集したり、他のユーザーが作成したアイテムを表示したりできる必要があります。
3)	アイテムが利用できなくなった場合は、リストから削除する必要があります。
4)  ユーザーがアイテムを予約できるようにします。
5)  ユーザーがアイテムをピックアップ用にマークできるようにします。
6)  アイテムが予約されている場合、予約されたユーザーのみがピックアップされたアイテムにマークを付けることができます。
7)  ユーザーはアイテムを検索できる必要があります。

## あなたが学ぶこと

1)	Dataverse for Teamsを使用してアプリケーションを作成する方法。
2)	アプリケーションを公開する方法。
3)	他のユーザーにアプリケーションへのアクセス許可を与える方法。

## 詳細な手順

### Exercise 1: Get started with Microsoft Dataverse for Teams

この演習では、新しいチームを作成し、Power Apps forTeamsをインストールします。

#### タスク1：チームを作成する
このタスクでは、新しいチームを作成します

1. [Microsoft Teams](https://teams.microsoft.com) に移動します。 
2. **Teams** を選択し、**Join or create a team** をクリックして、**Create Team** をクリックします。

![A screenshot with a box around the teams button on the left side of the window and an arrow pointing to the create team button](03-1/media/ex1-t1-image1.png)

3. **From scratch** を選択します。
4. **Public** を選択します。
5. チーム名に **Green** を入力し、**Create** をクリックします。

![A screenshot with the word green in the team name field](03-1/media/ex1-t1-image2.png)

6. **Skip** をクリックします。
7. これで、**Green** という名前の新しいチームができました。

![A screenshot of the microsoft teams page with your new team named green now under your teams](03-1/media/ex1-t1-image3.png)

8. このページから離れないでください。

#### タスク2：PowerAppsをインストールする
このタスクでは、Power Apps forTeamsをインストールします。

1.  **... More added apps** をクリックし、Power Appsを検索して、**Power Apps** を選択します。

![A Screenshot with an arrow pointing to the ellipsis icon for more added apps on the left side of the page and a box around power apps button](03-1/media/ex1-t2-image1.png)

2.  **Add** をクリックします。

3.  ower Apps タブを右クリックして、**Pin** を選択します。

![A Screenshot with an arrow pointing to the power apps icon and a box around the pin button](03-1/media/ex1-t2-image2.png)


### 演習2：アプリケーションを作成する
この演習では、アプリケーションを作成してチーム用のDataverseをプロビジョニングし、列を含むDataverseテーブルも作成します。

#### タスク1：アプリケーションを作成する
このタスクでは、アプリケーションを作成して、Dataverse forTeamsをプロビジョニングします。
1. [Microsoft Teams](https://teams.microsoft.com) に移動します。

2. Power Appsを選択し、**Start now** をクリックします。

![A screenshot of the power apps home page](03-1/media/ex2-t1-image1.png)

3. 作成した**Green** チームを選択し、**Create** をクリックします。
4. アプリ名に **Upcycle** と入力し、**Save** をクリックします。
5. このページから離れないでください。

#### タスク2：テーブルを作成する
このタスクでは、テーブルと列を作成します。

1. **With data** をクリックし、**+ Create new table** を選択します。

![A Screenshot with an arrow pointing to the with data option and a box around the create new table button from the select a data source prompt](03-1/media/ex2-t2-image2.png)

2. テーブル名に **Gadget** と入力し、**Create** をクリックします。
3. **+ Add column** をクリックします。
4. 名前に **Description** を入力し、タイプに **Text** を選択し、クリックして **Advanced options** セクションを展開します。

![A Screenshot with an arrow pointing to the advanced options button](03-1/media/ex2-t2-image3.png)

5. **Max ength** を**500** に変更し、**Create** をクリックします。
6. **+ Add column** をもう一度クリックします。
7. 名前に **Availability** と入力し、タイプに **Choice** を選択し、最初の選択肢に **Available** と入力して、**+ New choice** をクリックします。

![A Screenshot with an arrow pointing to the new choice button](03-1/media/ex2-t2-image4.png)

8.  2番目の選択肢に **Reserved** と入力し、**+ New choice** をクリックします。
9.  3番目の選択肢として **Picked up** と入力し、**Create** をクリックします。
10. これで、テーブル画面は次の画像のようになります。
     ![A Screenshot with an arrow pointing to the word saved in the right hand corner of the window](03-1/media/ex2-t2-image5.png)
11.  **Close** ボタンをクリックしてテーブルエディタを閉じます。
12.  このページから離れないでください。


#### タスク3：列を追加する
このタスクでは、テーブルに新しい列を追加します。

1. **Home** タブを選択し、**See more** をクリックします。

![A screenshot of a box around the home button and an arrow pointing to the see more button in the recent apps window of the home page of power apps](03-1/media/ex2-t3-image1.png)

2. クリックして **Gadget** テーブルを開きます。
3. **+ Add column** 列をクリックします。
4. 表示名に **Location** を入力し、データタイプに **Text** を選択し、列を **Required** にして、**Done** をクリックします。

![A screenshot of the add column window with the relevant text in each field](03-1/media/ex2-t3-image.png)

5. **+ Add column** をクリックします。
6. 表示名に **Photo** と入力し、データタイプに **Image** を選択し、**Primary image** チェックボックスをオンにして、**Done** をクリックします。

![A screenshot of the add column window with the relevant text in each field](03-1/media/ex2-t3-image3.png)

7.  **+ Add column** をクリックします。
8.  表示名に **Reserved by** と入力し、データ型に **Lookup** を選択し、関連テーブルに **User** を選択して、**Done** をクリックします。

![A screenshot of the add column window with the relevant text in each field](03-1/media/ex2-t3-image4.png)

9.  **Availability** 列を選択します。
10. デフォルト値として **Available** を選択し、**Done** をクリックします。

![A screenshot with a box around available selected as the default value option](03-1/media/ex2-t3-image5.png)

11. 画面の右下にある **Save table** ボタンをクリックします。
12. このページから離れないでください。


#### タスク4：アプリケーションを編集する
このタスクでは、使用可能なガジェットのフィルターによってアプリケーションを編集し、フォームを編集します。

1. **Home** タブを選択し、クリックして、作成した **Upcycle** アプリケーションを開きます。
2. **Screen1** を選択します。 画面にすでにフォームが含まれている場合は、次の手順に進みます。それ以外の場合は、**With data** をクリックして、**Current environment** の下の **Gadgets** テーブルを選択します。 これにより、フォームを含む画面要素が作成されます。
3. **RightContainer1** が展開されていることを確認し、ツリービューから **EditForm1** コントロールを選択します。

![A screenshot with a border around the edit form button under screen 1](03-1/media/ex2-t4-image1.png)

3. **Properties** ペインに移動し、**Edit fields** をクリックします。

![A Screenshot with an arrow pointing to the edit fields button](03-1/media/ex2-t4-image2.png)

4. **+ Add field** ボタンをクリックします。
5. 以下のリストから EditForm コントロールに存在しないフィールドを選択し、**Add** をクリックします。
   1. **Name**
   2. **Description**
   3. **Availability**
   4. **Location**
   5. **Reserved by**
   6. **Photo**

![A screenshot of the add field window](03-1/media/ex2-t4-image3.png)

6. 余分なフィールドをすべて削除し、**Fields** ペインを閉じます。 フォームには、**Name, Description, Availability, Location, Reserved By and Photo** の列のみを含める必要があります。
7. 列にスナップの **Columns** を **1** に変更します。

![A screenshot with a border around the columns field and the value of 1 in the field itself](03-1/media/ex2-t4-image4.png)

8. キャンバス内の **Photo** を選択し、**Width** を **400** に変更します。

![A screenshot of the photo selected inside the canvas and a border around the size field changed to 400 in the properties pane](03-1/media/ex2-t4-image5.png)

9.  フォームを展開し、**Reserved by** データカードを選択します。

![A screenshot of a border around reserved by data card selected under edit form 1](03-1/media/ex2-t4-image5_1.png)

10. **Properties** ペインに移動し、**Advanced** タブを選択して、**Unlock** をクリックします。

![A Screenshot with an arrow pointing to the lock icon under the advanced tab](03-1/media/ex2-t4-image5_2.png)

11.   displayを検索し、**DisplayMode** の値を **DisplayMode.View** に変更します。

![A screenshot with a border around the display mode field](03-1/media/ex2-t4-image5_3.png)

12.  **Browse gallery** を選択します。
13. 数式バーから **Items** を選択し、値を以下の数式に置き換えます。 この数式は、ガジェットをフィルタリングして、使用可能なガジェットのみを表示します。

    ```Filter(Gadgets, Availability <> 'Availability (Gadgets)'.'Picked up')```

![Filter data - screenshot](03-1/media/ex2-t4-image6.png)

14.  ギャラリー内の **Image** を選択します。

![A Screenshot with an arrow pointing to image 1 inside the gallery](03-1/media/ex2-t4-image7.png)

15.  数式バーに移動し、画像の値を次の数式に変更します。

```ThisItem.Photo```

![A screenshot of the relevant command put into the formula bar](03-1/media/ex2-t4-image8.png)

16.   **Data** タブを選択し、**Gadgets** テーブルの **...More actions** ボタンをクリックして、**Refresh** を選択します。

![A Screenshot with an arrow pointing to the ellipsis icon for more actions and a border around the refresh button](03-1/media/ex2-t4-image9.png)

17.  **Save** をクリックして、アプリが保存されるのを待ちます。
18.  **Preview** をクリックします。
19.  **+ New record** をクリックします。

![A screenshot of a border around the new record button](03-1/media/ex2-t4-image10.png)

20.  フォームに記入し、**Tap or click to add a picture** をクリックします。

![A Screenshot with an arrow pointing to the tap or click to add a picture button](03-1/media/ex2-t4-image11.png)

21.  自分の写真を提供するか、ラボのリソースフォルダーから写真を選択します。
22.  **Save** をクリックします。

![A Screenshot with an arrow pointing to the tick icon to save](03-1/media/ex2-t4-image12.png)

23.  さらにいくつかのアイテムを追加します。
24.  これで、アプリは次の画像のようになります。 プレビューを閉じます。

![A screenshot of the running app with an arrow pointing to the cross icon to close the preview](03-1/media/ex2-t4-image13.png)

25.  このページから離れないでください。


#### タスク5：Dataverse行を更新する
このタスクでは、ユーザーがアイテムを予約および/またはピックアップできるようにするボタンを追加します。また、Dataverseの行を予約済みまたはピックアップ済みとして更新します。

1. ツリービューから **App** を選択し、**OnStart** 値を次の式に設定します。 この式は、CurrentUser という名前の変数を作成し、その値を、ログインしたユーザーの電子メールに一致する最初のユーザーに設定します。

```Set(CurrentUser, First(Filter(Users, 'Primary Email' = User().Email)))```

![A screenshot with a border around app selected in the screens tab on the left and another border around the formula bar with the relevant command typed in](03-1/media/ex2-t5-image1.png)

2. アプリを選択し、**ellipsis** を選択して、**Run OnStart** を選択します。
3. **RightContainer** を選択します。

![A screenshot with a border around the RightContainer1 element selected](03-1/media/ex2-t5-image2.png)

3. **+** 挿入ボタンをクリックし、**Button** を選択します。

![A Screenshot with an arrow pointing to the plus icon to insert and a border around the button option](03-1/media/ex2-t5-image3.png)

4. **Tree view** を選択し、追加したボタンをダブルクリックして、名前を **Reserve Button** に変更します。

![A screenshot with the text "Reserve Button" highlighted as the new name for the button you added](03-1/media/ex2-t5-image4.png)

5. 予約ボタンの **Text** 値を **Reserve** に設定します。
6. 予約ボタンを移動して、画像の横に配置します。

![A screenshot of the Reserve button selected and moved next to the image on the right hand side](03-1/media/ex2-t5-image5.png)

7. 予約ボタンの **DisplayMode** 値を次の式に設定します。 この式は、選択したアイテムが利用できない場合にボタンを無効にします。

```If(BrowseGallery1.Selected.Availability = 'Availability (Gadgets)'.Available, DisplayMode.Edit, DisplayMode.Disabled)```

8. 予約ボタンの **OnSelect** 値を次の式に設定します。 この式は、予約済みの値を現在のユーザーに設定し、可用性の値を予約済みに設定することにより、選択したレコードを更新します。

```Patch(Gadgets, BrowseGallery1.Selected, {Availability: 'Availability (Gadgets)'.Reserved, 'Reserved by': CurrentUser})```

9. 予約ボタンの **Visible** 値を次の式に設定します。 この式は、ユーザーが新しいレコードを作成している場合にボタンを非表示にします。

```If(EditForm1.Mode = FormMode.View, true, false)```

10. **RightContainer** をもう一度選択します。
11. **+** 挿入ボタンをクリックして、**Button** をもう一度選択します。
12. **Tree view** を選択し、追加したボタンをダブルクリックして、名前を **Picked Up Button** に変更します。

![A screenshot with the text "Picked Up Button" highlighted as the name new for button you added](03-1/media/ex2-t5-image6.png)

12. 予約ボタンの **Text** 値を **Picked up** に設定します。
13. 幅を調整し、ピックアップボタンを移動して、予約ボタンの右側に配置します。

![A screenshot showing the Picked Up button selected and moved to the right of the Reserve button](03-1/media/ex2-t5-image7.png)

14. PickedUp ボタンの **DisplayMode** 値を次の式に設定します。 この式は、選択したアイテムが予約されていて、ユーザーによって予約されているのが現在のユーザーではない場合、ボタンを無効にします。

 ```If(BrowseGallery1.Selected.Availability = 'Availability (Gadgets)'.Reserved And BrowseGallery1.Selected.'Reserved by'.'Primary Email' <> CurrentUser.'Primary Email', DisplayMode.Disabled, DisplayMode.Edit)```

15. ピックアップ ボタンの **OnSelect** 値を次の式に設定します。 この式は、予約済みの値を現在のユーザーに設定し、可用性の値を取得するように設定することで、選択したレコードを更新します。 2番目の数式は、ギャラリーの最初のアイテムを選択します。

```Patch(Gadgets, BrowseGallery1.Selected, {Availability: 'Availability (Gadgets)'.'Picked up', 'Reserved by': CurrentUser});Select(BrowseGallery1,1)```

16. ピックアップ ボタンの **Visible** 値を次の式に設定します。 この式は、ユーザーが新しいレコードを作成している場合にボタンを非表示にします。

```If(EditForm1.Mode = FormMode.View, true, false)```

 17. **Save** をクリックして変更を保存します。
 18. このページから離れないでください。


#### タスク6：検索を追加する
このタスクでは、アプリケーションに検索機能を追加します。

1. **RightContainer** を選択します。
2. **+** 挿入メニューをクリックし、**+ Add icon** を選択します。
3. フォームの上にアイコンを配置します。

![A screenshot of the plus icon selected](03-1/media/ex2-t6-image1.png)

4. アイコンを選択し、**Properties** に移動して、アイコンの **Search** を選択します。

![A screenshot with a border around the Search option selected as the icon](03-1/media/ex2-t6-image2.png)

5. **+** 挿入メニューをクリックし、**Text box** を選択します。
6. **Tree view** を選択します。
7. 追加したテキストボックスを選択し、名前を **Search box** に変更します。

![A screenshot of the words "Search Box" highlighted as the new name for the text box you added](03-1/media/ex2-t6-image3.png)

8. アイコンの右側に検索ボックスを配置します。

![A screenshot of the Search Box placed to the right of the icon](03-1/media/ex2-t6-image4.png)

9.  **Search Box** を選択し、**OnChange** の値を次の式に設定します。 この数式はギャラリーをリセットします。

```Reset(BrowseGallery1)```

10. **BrowserGallery** を選択し、**Items** 式を以下の式に変更します。 数式は不完全です。次のステップで完成させます。

```Filter(Search(Gadgets, 'Search Box'.Value, ), Availability <> 'Availability (Gadgets)'.'Picked up')```

11. **'Search Box'.Value** の後にカーソルを置き、名前を入力します。 crxxx_nameの提案が表示されたら、提案された列を選択します。

![A screenshot with a border around the words "crefe4_name"](03-1/media/ex2-t6-image5.png)

12. 選択した名前の列の後にカンマを追加し、**description** と入力して、提案された列をもう一度選択します。

![A screenshot with a border around the worlds "crfe4_description"](03-1/media/ex2-t6-image6.png)

13. これで、数式は次の画像のようになります。 この数式は、ガジェットテーブルの名前と説明の列で、ユーザーがテキストボックスに入力した内容を検索し、選択したアイテムを除外します。

![Suggested description column - screenshot](03-1/media/ex2-t6-image7.png)

14.  **Search Box** を選択します。
15.  数式バーに移動し、**Value** のテキストを削除します。

![A screenshot with a border around the formula bar](03-1/media/ex2-t6-image8.png)

16.  **Save** をクリックして変更を保存します。

### 演習3：アプリケーションをテストして公開する
この演習では、アプリケーションをテスト、公開し、同僚に使用許可を与えます。

#### タスク1：アプリケーションをテストする
このタスクでは、アプリケーションをテストします。

1. **Preview** ボタンをクリックします。 

![A screenshot with an arrow pointing to the Preview button](03-1/media/ex3-t1-image1.png)

2. **Reserve** および **Picked up** ボタンが表示され、有効になっている必要があります。
3. ケーブルを検索します。 ギャラリーには、名前または説明の列に **cable** というテキストが含まれるアイテムが表示されます。

![A screenshot with the word cable in the search bar and a gallery showing items that have the text cable in their name or description column on the left side of the window](03-1/media/ex3-t1-image2.png)

4. 項目の1つを選択します。**Reserved by** 列の値は空である必要があります。
5. **Reserve** ボタンをクリックします。 

![A screenshot of a border around the Reserved by field and an arrow pointing to the Reserve button](03-1/media/ex3-t1-image3.png)

6. **Reserve** ボタンが無効になり、**reserved by** の値がユーザー名に設定されます。

![A screenshot with a border around the reserved by field with your username and another border around the now-disabled reserve button](03-1/media/ex3-t1-image4.png)

7. アイテムがギャラリーに表示されなくなり、ギャラリーの最初のアイテムが選択されます。
8. プレビューを閉じます。
9. このページから離れないでください。


#### タスク2：アプリケーションを公開する
このタスクでは、アプリケーションをTeamsに公開します。

1. **Publish to Teams** ボタンをクリックします。

![A Screenshot with an arrow pointing to the publish to teams button](03-1/media/ex3-t2-image1.png)

2. **Next** をクリックします。
3. **+** をクリックしてアプリをタブとして追加します。

![A Screenshot with an arrow pointing to the plus icon for add app as a tab in the general box](03-1/media/ex3-t2-image2.png)

4. **Save and close** をクリックします。
5. **Teams** を選択し、新しい **Upcycle** タブを選択します。

![A Screenshot with an arrow pointing to the upcycle button](03-1/media/ex3-t2-image3.png)

6. アプリが読み込まれるはずです。 アプリが読み込まれていない場合は、ページを更新してください。

![A screenshot of the loaded app](03-1/media/ex3-t2-image4.png)

7. Teamsでアプリケーションをテストし、期待どおりに動作することを確認します。


#### Task 3: Give permissions
このタスクでは、同僚に、新しいアイテムの作成、作成したアイテムの編集、作成したアイテムの削除、および他の人が作成したアイテムの読み取りを許可します。

1. **Power Apps** を選択し、**See more** リンクをクリックします。

![A screenshot with a border around the power apps button on the left side of the window and an arrow pointing to the see more link in the recent apps](03-1/media/ex3-t3-image1.png)

2. クリックして **Gadget** テーブルを開きます。
3. **Manage permissions** をクリックします。

![A Screenshot with an arrow pointing to the manage permissions button](03-1/media/ex3-t3-image2.png)

4. **Members** を選択し、**Collaborate** 権限を選択して、**Save** をクリックします。

![A screenshot of the collaborate permission selected](03-1/media/ex3-t3-image3.png)

5. 別のユーザーでアプリケーションをテストして、その動作を確認できます。

