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

* Must have completed **Lab 02.1: Data model and model-driven app**

## 詳細な手順

  ### 演習1：キャンバスアプリケーションを作成する

この演習では、共有コンポーネントを使用してソリューションをインポートし、問題レポートテーブルのビューを作成して、キャンバスアプリケーションを作成します。

#### タスク1：コンポーネントライブラリソリューションをインポートする

このタスクでは、共有コンポーネントソリューションを環境にインポートします。 この共有コンポーネントライブラリは、会社の別のチームによって作成されました。

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click **Import**.

![A Screenshot with an arrow pointing to the import button](03-2/media/image1.png)

3.  Click **Browse**.

4.  Go to the course resources folder, select the **Shared components** solution, and click **Open**.

5.  Click **Next**.

6.  Click **Import** and wait for the import to complete.

7.  Click **Publish All Customizations** and wait for the publishing to complete.

8.  You should now see the **Shared Components** solution you imported. Click to open the **Shared Components** solution.

9. The solution should have one item in it. (**Lamna Healthcare Shared Components**)

![A screenshot of the shared components window with the Lamna Healthcare shared components item](03-2/media/image2.png)

> [!IMPORTANT]
> ソリューションの一部としてアプリをインポートしても、コンポーネントライブラリにアプリが追加されない場合があるという問題があります。 次の手順は、問題を解決するために設計されています。

10. Navigate to **Apps**, Select the **Lamna Healthcare Shared Components App**.
11. Click the **Edit Icon** to edit the app.

![A Screenshot with an arrow pointing to the edit button](03-2/media/image2-1.png)

12. Select your **Region/Country** and click **Get started** if prompted.
    
    > [!Note]
    >
    > When the app is open in Edit mode, move on to next step, as the Preloader component shows a Loading icon but it is not actually waiting for something to load.
13. After the app opens, click **File** > **Save As**.
14. Save the app as **Lamna Healthcare Share Components A**.

![A screenshot with a border around the app name saved as Lamna Healthcare Shared Components A](03-2/media/image2-2.png)

14. Click **OK**.
15. Close the **Lamna Healthcare Shared Components** tab in your browser.

#### タスク2：ビューを作成する

このタスクでは、現在のユーザーの問題レポートを表示するビューを作成します。 後で、このビューをキャンバスアプリのフィルター機能で使用します。

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Locate and click to open the **Problem Reports** Table.

4.  Select the **Views** tab and click to open the **Active Problem Reports** view.

![A Screenshot with an arrow pointing to the active problem reports view button](03-2/media/image3.png)

5.  Click **Edit filters**.

![A Screenshot with an arrow pointing to the edit filters button](03-2/media/image4.png)

6.  Change the filter to **Created By Equals current user** and click **OK**.

![A screenshot of the edit filters window](03-2/media/image5.png)

7.  Click on the chevron button next to the Save button and select **Save As**.

![A Screenshot with an arrow pointing to the save as button](03-2/media/image6.png)

8.  Enter **My Reports** for **Name** and click **Save**.

9.  Click **Publish** and wait for the publishing to complete.

10. Click on the **Back** button in your browser tab to go back to the Problem Report table details.

#### タスク3：ユーザーアプリケーションを作成する

このタスクでは、電話のフォームファクターを使用してキャンバスアプリケーションを作成します。

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Click **+ New | App |Canvas app**.

![A Screenshot with an arrow pointing to the new button with the drop down menu under app upon and a border around the canvas app button](03-2/media/image7.png)

4.  Enter **Company 311 Phone App**, select **Phone** for format, and click **Create**.

5.  Select **Skip**.

6.  Go to the Tree view and double click **Screen1**.

![A Screenshot with an arrow pointing to the screen 1 button](03-2/media/image9.png)

10. Rename the screen **Main Screen**. It’s always a good idea to give your screens a meaningful name.

![A screenshot with the Screen 1 name highlighted and renamed Main Screen](03-2/media/image10.png)

11. Select the **Main Screen** and click **Insert**.

![A Screenshot with an arrow pointing to the plus icon for insert](03-2/media/image11.png)

12. Select **Get more Components**.

![A screenshot with a border around the get more components button](03-2/media/image12-1.png)

13.  Expand the **Lamna Healthcare Shared Components A** Library, select **Header** and **Tab Control**, and then click **Import**.

![A screenshot of the import components window with Ta control and header selected](03-2/media/image12-2.png)


14.  Expand **Library components**, select **Header Control** and **Tab Control**. These are both components from the library you imported earlier in the lab.

![A screenshot with a border around the library components Header and Tab control](03-2/media/image12-3.png)

15. Move the **Tab Control** to the bottom of the screen and the **Header Control** to the top of the screens.

16. Select the **Header Control** and change the **Text** value to **"Company 311".**

![A screenshot of a border around the expression tab with the text value set to company 311](03-2/media/image13.png)

17. Set the **Height** of the **Header Control** to **75**.

    ![Set Height - Header](03-2/media/image37.png)

18. Right click on the Main Screen and select **Duplicate screen**.

![A screenshot with a border around the duplicate screen button](03-2/media/image14.png)

18. Rename the new screen **New Reports Screen**.

19. Select the **Tree view**, select **App** and change the **OnStart** value to the formula below. This formula will create a new variable named My Tabs and set it to a table of tab items.

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

20. Select the **Tab Control** in the **Main Screen** and change the **Items** value to **‘My Tabs’**.

![A screenshot of the items value set to my tabs for Tab control](03-2/media/image16.png)

21. Change the **SelectedColor** value to **WhiteSmoke**.

22. Select the **Tab Control** inside the **New Report Screen** and set the Item value to **‘My Tabs’**.

23. Change the **SelectedColor** value to **WhiteSmoke**.

24. Click on the **…** button of the **App** and select **Run OnStart**.

![A screenshot of the run on start button coming from the ellipsis icon for see more under the app button](03-2/media/image17.png)

25. Your tabs should now show the two tabs you added.

![A screenshot of the two tabs you added](03-2/media/image18.png)

26. Click **File** and then click **Save**.
27. Click on the **<- back** button.

28. Do not navigate away from this page.

### 演習2：私のレポート

この演習では、現在ログインしているユーザーによって作成されたレポートを表示するギャラリーを追加します。

#### タスク1：ギャラリーを追加する

1.  Select the **Main Screen**, go to the **Insert** tab, click **Gallery**, and select **Vertical**.

![A Screenshot with an arrow pointing to the vertical gallery option](03-2/media/image19.png)

2.  Rename the new gallery **My Reports Gallery**.

3.  Resize and reposition **My Reports Gallery** and make sure the screen looks like the image below.

![A screenshot of the my reports gallery selected](03-2/media/image20.png)

4.  Select **My Reports Gallery**, go to the **Properties** pane, and select **Problem Reports** for **Data Source**. If you do not see Problem Reports, click **See all tables** or **Search** for the table.

![A screenshot of the my reports gallery window and the properties pane with problem reports selected for data source](03-2/media/image21.png)

5.  Select the **My Reports** view you created for **View**.

6.  Click **Edit fields**.

![A Screenshot with an arrow pointing to the edit button](03-2/media/image22.png)

7.  Change Subtitle1 to **statuscode**. This is the Status Reason Column.

![A screenshot of a border around subtitle 1 changed to the correct name](03-2/media/image23.png)

8.  Click **File** and then click **Save**.

9.  Click on the **<- Back** button.

10. Do not navigate away from this page.

### 演習3：レポートの削除を許可する

この演習では、割り当てられていないレポートを削除できるようにします。 これにより、ユーザーは誤って作成されたレポートを簡単に削除できます。

#### タスク1：削除を許可する

1.  Expand the **My Reports Gallery**.

2.  Select the **Icon** inside the **My Reports Gallery**.

![A screenshot of the arrow icon inside the my reports gallery](03-2/media/image24.png)

3.  Change the **Icon** value to **Icon.Trash**.

![A screenshot of icon.trash typed into the expression tab](03-2/media/image25.png)

4.  Change the **Visible** value to the formula below. This formula will hide the icon if the status reason is not New.

`If(Text(ThisItem.'Status Reason') = "New", true, false)`

![A screenshot of the expression tab with the relevant command pasted in](03-2/media/image26.png)

5.  Make sure you still have the icon selected. Change the **OnSelect** value to the formula below. This formula will remove item from the data source.

`Remove('Problem Reports', ThisItem)`

6.  Click **File** and then click **Save**.

7.  Click on the **<-** **Back** button.

8.  Do not navigate away from this page.

### 演習4：新しいレポートを追加する

この演習では、新しい問題レポートを送信するためのフォームを追加します。

#### タスク1：新しいレポートフォームを追加する

1.  Select the **New Report Screen**, go to the **Insert** tab, click **Form**, and select **Edit**.

![A screenshot of the inset tab and forms button selected](03-2/media/image27.png)

2.  Rename the form to **New Report Form**.

3.  Select **New Report Form**, go to the **Properties** pane, and select **Problem Report** for **Data source**.

4.  Click **Edit fields**.

![A Screenshot with an arrow pointing to the edit fields button](03-2/media/image28.png)

5.  Remove the **Status Reason** Column.

![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the remove button](03-2/media/image29.png)

6.  Remove the **Created On** Column.

7.  Remove the **Location** Column.

8.  Click **+ Add field**.

9.  Select **Details**, **Building**, **Department**, and **Photo**, and then click **Add**.

![A screenshot of photo, details, building, and location selected in the fields window](03-2/media/image30.png)

10. Resize and reposition the form so it takes most of the page and leave enough room for a button in the bottom.

![A screenshot of the form resized and reposition for room at the bottom for a button](03-2/media/image31.png)

11. Select the **New Report Screen**.

12. Go to the **Insert** tab and select **Button**.

13. Rename the button **Submit Report**.

14. Place the button below the form and make it stretch across the screen

15. Change the **Submit Report** button's **text** property to **Submit**.

16. Select the Submit Report button and change the **OnSelect** value to the formula below. This formula will create a new Row in the Problem Reports table.

`SubmitForm('New Report Form') `

17. Select the **New Report Form**.

18. Change the **OnSuccess** value to the formula below. This formula will show a notification after the new Row gets created and clear the form when the record creation is successful.

`Notify("Created new problem report row");NewForm('New Report Form')`

19. Select the **New Report Screen**.

20. Set the **OnVisible** value to the formula below. This formula will create a new form when the screen becomes visible.

`NewForm('New Report Form')`

21. Click **File** and then click **Save**.
22. Click **Publish**.
23. Click **Publish this version** and wait for the publishing to complete.
24. Click on the **<-** **Back** button.
25. Do not navigate away from this page.


### 演習5：アプリケーションをテストする

この演習では、問題レポートを送信して作成したキャンバスアプリケーションをテストします。

#### タスク1：アプリケーションをテストする

1.  Select the **Main Screen** and click **Preview the app**.

![A Screenshot with an arrow pointing to the play icon to preview the app](03-2/media/image32.png)

2.  The application should load, and the list should show all the reports you created.

![A screen of your loaded application](03-2/media/image33.png)

3.  Select the **New Report** tab.

4.  The **New Report Form** should load. Fill out the form and click on the **Photo** Column.

5.  Select an image.

6.  Click **Submit**

7.  The Row should get created successfully and you should see the success message.

![A screen of the success message reading "created new problem report record"](03-2/media/image38.png)

8.  Select the **My Reports** tab.

9.  You should see the new report you created. Click **Delete** to test the delete.

![A Screenshot with an arrow pointing to the trash can icon to delete](03-2/media/image35.png)

10. The Row should be deleted and removed from the list.

![A screenshot of the row deleted and removed from the list](03-2/media/image36.png)

11. **Close** the preview.
12. **Close** the app studio by closing the browser tab.

### 演習6：Microsoft Teamsにキャンバスアプリを埋め込む

この演習では、スタッフがチーム内で直接問題をログに記録できるようにする方法として、以前に作成したCompany 311 Phone アプリを Microsoft Teams に追加します。

#### タスク1：会社311チームをセットアップする

In this task, you will setup a **Microsoft Teams** team for the Lamna Healthcare Company, if you have not done so previously.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com) and sign in with the same credentials you have been using previously.

2.  Select **Use the web app instead** on the welcome screen.

![A screenshot of the Microsoft Teams web browser landing page with a border around the use the web app instead button](03-2/media/image-3-teams.png)

3.  When the Microsoft Teams window opens, dismiss the welcome messages.

4.  Select **Teams**.
5.  On the bottom left corner, choose **Join or create a team**.

6.  Select **Create a team**.

![A screenshot of a border around the join or create a team button and another border around the create a team button](03-2/media/image-3-createteam.png)

6.  Press **From scratch**.

7.  Select **Public**.

8.  For the Team name enter **Company 311** and select **Create**.

9.  Select **Skip** adding members to Company 311.
10. Do not navigate away from this page.


#### タスク2：チームにキャンバスアプリを追加する

1.  Select the **General** channel of the **Company 311** team.

2.  On the top of the page, press the **+** symbol to add a new tab.

![A screenshot of a border around the plus icon to add a new tab](03-2/media/image-3-addpowerbitab.png)

4.  Search for **power** and select **PowerApps** from the results.

5.  Select **Add** to add Power Apps to Teams

![A screenshot of the prompt to add Power Apps to Teams](03-2/media/image-3-powerappsteams.png)

6. Select the **Company 311 Phone App** that you created earlier in this lab. 

> [!IMPORTANT]
> アプリが表示されない場合は、アプリエディターに戻ってアプリを公開する必要があります

7. Select **Save**.

8. The **Company 311** app should now appear on a tab in Microsoft Teams.

![A screenshot of the company 311 app appearing on a tab in Microsoft Teams](03-2/media/image-3-powerappinteams.png)



### 演習7：モデル駆動型アプリにキャンバスを埋め込む

この演習では、キャンバスアプリケーションを作成し、それをモデル駆動型アプリケーションに追加します。

#### タスク1：フォームにキャンバスアプリを追加する

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in your practice environment.
2. Select **Solutions** and click to open the **Company 311** solutions.
3. Locate and click to open the **Building** table.
4. Select the **Forms** tab and click to open the **Information** form of type **Main**.

![A Screenshot with an arrow pointing to the word information with a border around the form type being main](03-2/media/opentableform.png)

5. Select the **form section**.
6. Go to the Properties pane and click to expand **Formatting**.
7. Change the **Columns** value to **2**.

![A screenshot with a border around the number of columns](03-2/media/formsectioncolumns.png)

8. Make sure you still have the section selected. Select the **Table columns** tab.
9. Uncheck the **Show only unused table columns** checkbox and click on the **Name** column.

![A Screenshot with an arrow pointing to the name button](03-2/media/addcolumntoform.png)

10. The column should now appear on right side column of the section. Select the **Name** column on the form.
11. Check the **Hide label** checkbox and click **Save**.

![A Screenshot with an arrow pointing to the save button](03-2/media/saveform.png)

12.  Click on the **Switch to classic** button. Select **Skip** if prompted.

![A Screenshot with an arrow pointing to the switch to class button](03-2/media/switchtoclassic.png)

13.   Double click on the **Name** column you added to the form.
14.   Select the **Controls** tab and click **Add control**.

![A Screenshot with an arrow pointing to the add control button](03-2/media/ex_7_addcontrol.png)

15.   Select **Canvas app** and click **Add**.
16.   Click **Customize**.

![A Screenshot with an arrow pointing to the customize button](03-2/media/ex_7_customizeapp.png)

17.   A new browser window or tab should open and load the app studio.
18.   Do not navigate away from this page.

#### タスク2：アプリをカスタマイズする

1.  Right click on **Form1** and select **Delete**.

![A screenshot with a border around the delete button](03-2/media/ex_7_deleteform.png)

2.  Click **File**.
4.  Select **The cloud**, enter **Model embed app** for name, and click **Save**.

![A screenshot of the Save As prompt](03-2/media/ex_7_saveapp.png)

5.  Select **Settings**.
6.  Select **Display**.
7.  Enter **400** for Width.

![A screenshot with a border around the width changed to 400](03-2/media/ex_7_displaywidth.png)

8.   Click **Apply** on the popup.
9.   Enter **500** for Width.
10.  Click **Apply** on the popup.
11.  Close the Settings popup window.
12.  Select the **App** object from the Tree view.
13.  Select the **OnStart** of the **App** object and set it to the formula below. This formula will create two variables one to keep track of the current index of the reports table and another to keep track of the current item row.

```Set(currentIndex,1);Set(CurrentItem, Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex)))```

![A screenshot with a border around the app object changed to onstart and set to the aforementioned formula. There is also another border around the app button selected](03-2/media/ex_7_apponstart.png)

14.  Select the **Insert** insert tab, click **Media**, and select **Image**.

![A screenshot of a border around the image button](03-2/media/ex_7_insertimage.png)

15.  Select the image you just added and set the **Image** value to the formula below.

```CurrentItem.Photo```

16.   Click on the **...** button of the **App** object and select **Run OnStart**.

![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the run on start button](03-2/media/ex_7_runonstart.png)

17.  You should see the photo. Select **Image control** from Tree View.

![A screenshot of an icon of a broken door](03-2/media/ex_7_imagephoto.png)

18. Set the **X** value of the image to **0**.
19. Set the **Y** value of the image to **0**.
20. Set the **Width** value of the image to the formula below.

```Parent.Width```

21. Set the **Height** value of the image to the formula below.

```Parent.Height```

22. Go to the **Properties** pane and select **Fill** for **Image position**.

![A Screenshot with an arrow pointing to the the file tab](03-2/media/ex_7_imageposition.png)

23. Click **File** and then click **Save** to save your progress.
24. Click on the **<-** **Back** button.
25. Do not navigate away from this page.


#### タスク3：コントロールを追加する

1.  Select the **Insert** tab and click **Label**.
2.  Select the label you just added and set the **Text** value to the formula below.

```CurrentItem.Title```

3.  Set the **Height** value of the label to **60**.
4.  Set the **X** value of the label to **0**.
5.  Set the **Y** value of the label to formula below.

```Parent.Height -Self.Height```

6.  Set the the **Width** value of the label to formula below.

```Parent.Width```

7.  Set the **Fill** value of the label to **RGBA(0, 108, 191, .5)**.
8.  Set the **Color** value of the label to **RGBA(255, 255, 255, 1)**.
9.  Set the **Align** value to the formula below.

```Align.Center```

10. The label should now look like the image below. If you don't see the title, click on the **...** button of the **App** object and **Run OnStart** again.

![A screenshot of the broken door icon now with a label](03-2/media/ex_7_resizedlabel.png)

11.  From the **Insert** tab, click **Icons** and select **Next**.
12.  Double click on the icon you just added and rename it **Next icon**.
13.  From the **Insert** tab, click **Icons** and select **Back**.
14.  Double click on the second icon you just added and rename it **Back icon**.
15.  Drag and place the the **Next icon** above the right side of the label.
16.  Drag and place the the **Back icon** above the left side of the label.
17.  The icons should now look like the image below.

![A screenshot of the broken door icon with the next and back icons](03-2/media/ex_7_iconlocation.png)

18.  Select the **Next icon** and set the **OnSelect** value to the formula below.

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex +1)```

19.  Set the **DisplayMode** value of the **Next icon** to the formula below.

```If(currentIndex = CountRows([@ModelDrivenFormIntegration].Item.'Problem Reports'), DisplayMode.Disabled, DisplayMode.Edit)```

20.  Select the **Back icon** and set the **OnSelect** value to the formula below.

```UpdateContext({CurrentItem: Last(FirstN([@ModelDrivenFormIntegration].Item.'Problem Reports',currentIndex))});Set(currentIndex, currentIndex -1);```

21.  Set the **DisplayMode** value of the **Back icon** to the formula below.

```If(currentIndex > 1, DisplayMode.Edit, DisplayMode.Disabled)```

22. Click **File** and then click **Save**.

23. Open a new browser tab and navigate to [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment

24. Select the **Apps** and click to launch the **Company 311 Admin** application.

25. Click **Change Area** and Select **Settings**.

![Change sitemap area - screenshot](03-2/media/image39.png)

26. Select **Buildings**. 

27. Sort the Buildings rows on **Created On** Column in **Oldest to Newest** order. Keep a note of the oldest record.

28. Click **Change Area** and Select **Manage Problems**.

29. Select **Problem Reports**.

30. Click **+New**. 

31. Enter **Broken Tap** for Name, select the oldest building in the **Building** column and enter **The Tap is broken and the water is continuously flowing.** in the Details column. Add any image of your choice in the **Photo** column.

32. Click **Save**.

33. Click **+New**.

34. Enter **Roof Leaks** for Name, select the oldest building in the **Building** column and enter **Water is seeping through the ceiling.** in the Details column. Add any image of your choice in the **Photo** column.

35. Click **Save** and close the browser tab of the Model Driven App.

36. Open the Canvas App Editor for the **Model embed app** application. Select **Data** icon on the left menu.

    ![Select Data - screenshot](03-2/media/image40.png)

37. Locate **Problem Reports** and click on the **ellipsis** and then click on **Refresh**.

38. Click on the **...** button of the **App** object and select **Run OnStart**.

39. Select **Tree View** from the left menu and select **FormScreen** screen.

40. Click **Play**.

41. Click on the next and back icons and make sure the image changes.

42. Close the preview.

43. Click **File**.

44. Click **Save**.

45. Click **Publish**.

46. Click **Publish this version** and wait for the publishing to complete.

47. Close the app studio browser window or tab.

48. You should now be back on the **Field Properties**. Select **Web, Phone, Tablet** and click **OK**.

![A screenshot with a border around the canvas app item under control with web, phone, and tablet selected. There is also an arrow pointing to the ok button at the bottom of the window](03-2/media/ex_7_fieldproperties.png)

49. Click **Save** on the classic form editor.
50. Close the classic form editor browser window or tab.
51. You should now be back on the modern form editor. Click on **<-** **Back** button.

![A Screenshot with an arrow pointing to the back button](03-2/media/ex_7_backtomaker.png)

52. Select **Solutions**.
53. Click **Publish all customizations** and wait for the publishing to complete.


#### タスク4：アプリをテストする

1. Select the **Apps** and click to launch the **Company 311 Admin** application.

   ![A Screenshot with an arrow pointing to the company 311 admin application](03-2/media/ex_7_launchmodelapp.png)

2. Select **Problem reports** and click to open one of the problem report rows.
3. Make sure the problem has a photo and click on the **Building** lookup.

   ![A Screenshot with an arrow pointing to the building lookup](03-2/media/ex_7_lookup.png)

4. Canvasアプリは、モデル駆動型アプリケーション内に読み込まれる必要があります。 [次へ] / [戻る]アイコンをクリックして、アプリケーションが期待どおりに動作することを確認します。

   ![A screenshot of the broken door icon in the context of the canvas app inside the Model-Driven Application](03-2/media/ex_7_canvasinmodel.png)

