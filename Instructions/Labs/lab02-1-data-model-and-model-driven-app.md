---
lab:
    title: 'Lab 02.1: Data model and model-driven app'
    module: 'Module 02: Create a model-driven app'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# ラボ02.1：データモデルとモデル駆動型アプリ

このラボでは、ソリューションのデータモデルを実装し、問題の修正や全体的な取り組みの管理に使用されるモデル駆動型アプリを構築します。

## あなたが学ぶこと

  - テーブル、列、リレーションシップを作成する

  - モデル駆動型アプリを作成する

  - サイトマップを作成する

  - テーブルフォームを作成して構成する

  - テーブルビューを作成および構成する

## 高レベルのラボ手順

  - 演習1 - 公開元とソリューションを作成する

  - 演習2 – データモデルを実装する
    
      - データモデル
        
          - Building 
          
          - Department 
          
          - Problem Report 

  - 演習3 – フォームとビューを構成する 

  - 演習4 – 基本的なモデル駆動型アプリを作成する 

  - 演習5 – データを入力していくつかのビューを調整し、いくつかの問題レポートをインポートします

## 詳細な手順

### 演習1：公開元とソリューションを作成する

この演習では、カスタムソリューションパブリッシャーとソリューションを作成します。 このソリューションは、このコースのすべてのラボで使用され、すべてのコンポーネントをまとめます。

#### タスク1：公開元とソリューションを作成する

1.  [Power Apps maker portal](https://make.powerapps.com/) に移動し、作成した Practice 環境にいることを確認します。

2.  **Solutions** を選択し、**+ New solution** をクリックします。

3.  **Display name** に **Company 311** を入力しし、クリックします。

4.  **Publisher** ドロップダウンをクリックし、 **+ Publisher** を選択します。

![A Screenshot with an arrow pointing to the new publisher button](02-1/media/image1.png)

5.  **Display name** に **Lamna Healthcare** を入力し、**Name** に **lamnahealthcare** 、**Prefix** に **lh** 、選択値に **88186** を入力し、 **Save** をクリックします。

![A screenshot of the new publisher properties pane](02-1/media/image105.png)

6.  **Publisher** ドロップダウンを再度クリックし、作成した **Lamna Healthcare** を選択します。

8.  **Create** をクリックします。

![A screenshot of the new solution pane](02-1/media/image3.png)

9.  これで、作成したソリューションがソリューションリストに表示されます。

![A screenshot with a border around your solution](02-1/media/image4.png)

### 演習2：データモデルを実装する

この演習では、Company 311アプリのデータモデルを設計したときに特定したテーブル、列、および関係を作成します。

#### タスク1：テーブルを作成する

1.  [Power Apps maker portal](https://make.powerapps.com/) で、 **Solutions** を選択し、演習1 で作成した **Company 311** ソリューションを開きます。

2.  **+ New** をクリックし、 **Table** を選択します。

3.  **Display name** に **Building** を入力し、 **Create** をクリックします。

![A screenshot of the new table window with the relevant value in each field](02-1/media/image5.png)

4.  ソリューション名をクリックして、ソリューションに戻ります。

5.  **+ New** をクリックし、 **Table** を再度選択します。

6.  **Display name** に **Department** を入力し、 **Create** をクリックします。

![A screenshot of the new table window with the relevant value in each field](02-1/media/image7.png)

7.  ソリューション名をクリックして、ソリューションに戻ります。

![Building Table properties - screenshot](02-1/media/image99.png)

8.  **+ New** をクリックし、再度、 **Table** を選択します。

9.  **Display name** に **Problem Report** を入力し、**Primary Column** の **Display name** を **Title** に変更し、 **More settings** をクリックします。

![A screenshot with a border around the primary name column settings: display name and name. There is also an arrow pointing to the more settings button below](02-1/media/image8.png)

10. **Collaboration** をクリックし、セクションを展開します。

![A Screenshot with an arrow pointing to the collaboration button](02-1/media/image9.png)

11. **Enable queues** チェックボックスをオンにして、 **Create** をクリックします。キューを有効にすると、問題レポート行を１つ以上のキューに関連付けて、様々な部門へのルーティングを容易にすることができます。

![A screenshot of the enable queues checkbox highlighted](02-1/media/image10.png)

12. **Confirm changes** ポップアップで、 **Okay** をクリックします。

![A screenshot of the confirm changes popup](02-1/media/image11.png)

#### タスク2：列を追加する

このタスクでは、Problem Report テーブルに列を追加します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。

2.  **Solutions** を選択し、演習1で作成した **Company 311** ソリューションを開きます。

3.  **Problem Report** テーブルを探して、開きます。

![A screenshot of a border around the problem report button](02-1/media/image12.png)

4.  **Columns** タブを選択し、 **+ Add Column** をクリックします。

![A Screenshot with an arrow pointing to the add column button](02-1/media/image13.png)

5.  **Display name** に **Location** を入力し、**Data type** から **Text** を選択し、 **Advanced options** をクリックします。

![A Screenshot with an arrow pointing to the advanced options at the bottom of the location window](02-1/media/image14.png)

6.  **Max length** に **150** を入力し、 **Done** をクリックします。

![A screenshot showing the max length at a value of 150](02-1/media/image15.png)

7.  再度 **+ Add Column** をクリックします。

8.  **Display name** に **Details** を入力し、**Data type** で **Multiline text** を選択し、 **Required** を選択し、 **Done** をクリックします。

![A screenshot of the details window with the relevant values in each field](02-1/media/image16.png)

9.  再度 **+ Add Column** をクリックします。

10. **Display name** に **Photo** を入力し、**Data type** をから **Image** を選択し、 **Done** をクリックします。

11. **+ Add Column** をクリックします。

12. **Display name** に **Resolution** を入力し、 **Data type** で **Multiline text** を選択し、 **Done** をクリックします。

13. **+ Add Column** をクリックします。

14. **Display name** に **Resolved On** を入力し、 **Data type** で **Date and time** を選択し、 **Done** をクリックします。

15. **Default** フィルターを選択し、**Custom** クリックをします。(小画面デバイスの場合、デフォルトのドロップダウンは**ellipsis**になります).
![A Screenshot with an arrow pointing to the default dropdown menu and a border around the custom button](02-1/media/image17.png)

16. これで、作成した5つの新しい列が表示されます。 **Save Table** をクリックします。

![A screenshot showing the 5 new columns you have created: details, location, photo, resolution, and resolved on](02-1/media/image18.png)

17. ソリューション名をクリックして、ソリューションに戻ります。

18. [**Publish all customizations**]をクリックして、公開が完了するのを待ちます。

19. すべてのカスタマイズが正常に公開されるまで、このページから移動しないでください。

#### タスク3：ステータス理由の編集選択

このタスクでは、問題レポートテーブルのステータス理由列を編集します。

1.  **Company 311** ソリューションを使用していることを確認してください。

2.  クリックして **Problem Report** テーブルを開きます。

3.  **… More commands** ボタンをクリックし、**Switch to classic** を選択します。

> [!NOTE]  
> 最新のソリューションエクスプローラーはステータス理由の編集をまだサポートしていませんが、将来的にサポートするため、クラシックに切り替えています。

![A Screenshot with an arrow pointing to the ellipses icon for more options next to AI builder and a border around the switch to classic button](02-1/media/image19.png)

4.  **Fields** を選択し、表示名列で **Status Reason** を探し、ダブルクリックして **Status Reason** 列を開きます。

> [!NOTE]  
> ブラウザでポップアップが有効になっていない場合、列を更新するためのポップアップウィンドウは開きません。 ブラウザタブで開いているポップアップとリダイレクトが有効になっていることを確認してください。 

![A screenshot with a border around the fields button and an arrow pointing to the display name of status code](02-1/media/image20.png)

5.  **Status** で **Active** が選択されていることを確認し、ダブルクリックして**Active** オプションを開きます。

![A Screenshot with an arrow pointing to the status with a border emphasizing it is active](02-1/media/image21.png)

6.  **Label** の値を **New** に変更し、**OK** をクリックします。

![A screenshot of the modify list value window](02-1/media/image22.png)

7.  **Add** をクリックします。

![A screenshot of the type window and a border around the add button](02-1/media/image23.png)

8.  **Label** に **Assigned** と入力し、**OK** をクリックします。

![A screenshot of the add list value window](02-1/media/image24.png)

9.  再度 **Add** をクリックします。

10. **Label** に **In Progress** と入力し、**OK** をクリックします。

11. 再度 **Add** をクリックします。

12. **Label** に **Completed** と入力し、**OK** をクリックします。

13. 再度 **Add** をクリックします。

14. **Label** に **Won't Fix** と入力し、**OK* をクリックします。

15. これで、5つのオプションがあります。 **Default** で **New** を選択し、**Save and Close** をクリックします。

![A Screenshot with an arrow pointing to the save and close button](02-1/media/image25.png)

16. **Publish** をクリックして、公開が完了するのを待ちます。

17. **Save and Close** をクリックして、クラシックエディタを閉じます。

18. これで、**Power Apps Maker** ポータルに戻るはずです。

![A screenshot of the Power Apps Maker portal](02-1/media/image26.png)

#### タスク4：リレーションシップ

このタスクでは、問題レポートテーブルと建物および部門のテーブルの間に多対1の関係を作成します。

1.  **Problem Report** のテーブルにいることを確認してください。

2.  **Relationships** タブを選択し、**+ Add relationship** をクリックします。

![A Screenshot with an arrow pointing to the add relationship button](02-1/media/image27.png)

3.  **Many-to-one** を選択します。

![A screenshot of a border around the many to one button](02-1/media/image28.png)

4.  **Related (One) Table**　の　**Building** を選択し、**Done** をクリックします。

![A screenshot of the many-to-one relationship settings](02-1/media/image29.png)

5.  **+ Add relationship** を再度クリックします。

6.  **Many-to-one** を選択します。

7.  **Related (One) Table**　の　**Department** を選択し、**Done** をクリックします。

8.  **Save Table** をクリックします。

9.  ソリューション名をクリックして、ソリューションに戻ります。

10. **Publish all customizations** をクリックして、公開が完了するのを待ちます。

### 演習3：フォームとビューを構成する

この演習では、Problem Report Table のフォームとビューを構成します。

#### タスク1：フォームを構成する

1.  [Power Apps maker portal](https://make.powerapps.com/) に移動し、正しい環境にいることを確認します。

2.  [ソリューション]を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **Problem Report** テーブルを探し、開きます。

4.  **フォーム** タブを選択し、**Main** タイプの **Information** フォームを開きます。

![A screen shot of a border around the main form under the forms tab](02-1/media/image30.png)

5.  フォームの下部にあるズームコントロールを使用して、簡単に作業できるようにフォームを十分に大きくします。 **form section** を選択します。

![A Screenshot with an arrow pointing to the selection of the form section](02-1/media/image31.png)

6.  **Properties** ペインに移動し、**Label** を **Problem details** に変更し、**Name** に**section\_problem\_report** と入力します。

![A screenshot of the properties pain with the relevant text in each field](02-1/media/image32.png)

7.  セクションを選択したまま、**Table Columns** ペインに移動し、**Building** 列をクリックします。 Building 列がフォームに追加されます。

![A screenshot with a border around the table columns icon and an arrow pointing to the building column](02-1/media/image33.png)

8.  **Details** 列と **Photo** 列をフォームに追加します。

9.  これで、フォームは次の画像のようになります。 **Detail** 列を選択します。

![A screenshot with the details column selected](02-1/media/image34.png)

10. **Properties** ペインに移動し、クリックして **Formatting** セクションを展開します。

![A Screenshot with an arrow pointing to the formatting button](02-1/media/image35.png)

11. **form field height** を **4** に変更します。

![A screenshot of the form field height set to 4](02-1/media/image36.png)

12. ツールバーから **Components** を選択します。

![A Screenshot with an arrow pointing to the components icon](02-1/media/image37.png)

13. **1-Column section** を選択します。

![A Screenshot with an arrow pointing to the 1-column section button](02-1/media/image38.png)

14. 新しいセクションをフォームに追加する必要があります。 **new section** を選択します。

![A Screenshot with an arrow pointing to the new section selected](02-1/media/image39.png)

15. **Properties** ペインに移動し、**Section Label** を **Resolution details** に変更し、**Name** に **section\_resolution\_details** と入力します。

![A screenshot of the properties pane with the relevant text in each field](02-1/media/image40.png)

16. ツールバーから **Table columns** を選択します。

17. **Department**、**Status Reason**、**Resolved on**、および **Resolution** 列を **Resolution details** セクションに追加します。

![A screenshot of the Resolution details section with the Resolution column highlighted](02-1/media/image100.png)

18. **Resolution** 列を選択します。

19. **Properties** ペインに移動し、クリックして **Formatting** セクションを展開します。

20. **Form field height** を **4** に変更します。

21. フォームは下の画像のようになります。 **Save** をクリックします。

![A Screenshot of the Problem Report form with an arrow pointing to the Save button](02-1/media/image101.png)

22. **Publish** をクリックして、公開が完了するのを待ちます。

23. **Back** ボタンをクリックします。

![A Screenshot with an arrow pointing to the back button arrow icon](02-1/media/image43.png)

24. これで、テーブルに戻るはずです。

#### Task 2: Edit view

1.  Select the **Views** tab and click to open the **Active Problem Reports** view.

![A Screenshot with an arrow pointing to the active problem reports button](02-1/media/image44.png)

2.  Click **+ View column** and select **Building** to add the **Building** column to the view.

![A Screenshot with an arrow pointing to the view column button and a border around the building button](02-1/media/image45.png)

3.  Add **Location**, **Status Reason**, and **Owner** columns to the view.
    You will have to change the column filter to **All** when adding status reason and owner columns.

![A screenshot of a border around the column filter set to all](02-1/media/image46.png)

4.  Go to the view properties pane and click **Edit filters**.

![A Screenshot with an arrow pointing to the edit filters button](02-1/media/image47.png)

5.  Update the existing filter and set it to **Status Reason Equals New**.

6.  Click on the Column where **New** is selected.

![A Screenshot with an arrow pointing to a column with new written in it](02-1/media/image48.png)

7.  Select **Assigned**.

![A Screenshot with an arrow pointing to the assigned option in the column where new is written](02-1/media/image49.png)

8.  Click on the column again and select **In progress**.

9.  The filter should now look like the image below. Click **OK**.

![A screenshot of the edit filters window with status reason equals, new, assigned, and in progress](02-1/media/image50.png)

10. Click **Save**.

#### Task 3: Create view from existing

In this task, you will create a new view from the Active Problem Reports view.

1.  Click **Edit filters**.

![A Screenshot with an arrow pointing to the edit filters buttton](02-1/media/image51.png)

2.  Remove **In Progress** from the filter.

![A Screenshot with an arrow pointing to the in progress box in the 3rd column in the edit filters window](02-1/media/image52.png)

3.  Remove **Assigned** and **New** values form the filter.

4.  Select **Completed**.

![A Screenshot with an arrow pointing to the completed button from the drop down in the 3rd column](02-1/media/image53.png)

5.  Add **Won’t Fix** and **Inactive** values to filter.

6.  The filter should now look like the image below. Click **OK**.

![A screenshot of the edit filters window with the following; status reason equals, completed, won't fix, inactive](02-1/media/image54.png)

7.  Click on the chevron button next to the save button and select **Save As**.

![A Screenshot with an arrow pointing to the save drop down chevron icon and a border around the save as button](02-1/media/image55.png)

8.  Enter **Resolved Problems** for **Name** and click **Save**.

![A screenshot of the save as window](02-1/media/image56.png)

9.  Click on the **Back Button** of your browser to go back to the solution.

![A Screenshot with an arrow pointing to the back button](02-1/media/image57.png)

10. Go to the solution by clicking on the solution name.

![A Screenshot with an arrow pointing to the solution name company 311](02-1/media/image58.png)

11. Click **Publish all customizations** and wait for the publishing to complete.

![A screenshot of a border around the publish all customizations button](02-1/media/image59.png)

### Exercise 4: Compose model-driven application

In this exercise, you will create model-driven application.

#### Task 1: Create new model-driven application

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select Solutions and click to open the **Company 311** solution.

3.  Click **+ New | App | Model-driven app**.

![A screenshot of a border around the Model-driven app button](02-1/media/image60.png)

4.  Select **Modern app designer** and click **Create**.

5.  Enter **Company 311 Admin** for name and click **Create**.

![A screenshot of the New model-driven app window](02-1/media/image61.png)

6. Select **Navigation** from left menu.

   ![A screenshot of the Pages selection pane with a red arrow pointing to the tree icon in the navigation pane](02-1/media/image102.png)

7. Select the **Area1**.

![A Screenshot with an arrow pointing to area 1 selected](02-1/media/image63.png)

8. Go to the **Properties** pane, enter **Manage Problems** for **Title**, and enter **area\_manage\_problems** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image64.png)

9. Select the **Group1**.

![A screenshot of group 1 selected](02-1/media/image65.png)

10. Go to the **Properties**, enter **Problems** for **Title**, and enter **group\_problems** for **ID**.
11. Select the **Subarea1**.
12. Go to the **Properties** pane, select **Table** for **Content Type**, and select **Problem Report** for **Table**, and enter **Problem reports** for **Title**.

![A screenshot of the properties pane and the content type, table, and title changed](02-1/media/image68.png)

> [!NOTE]
> The new app designer doesn't provide a way to add new sitemap area yet.

13. Click **Save**.
14. Click **Switch to classic**

![A Screenshot with an arrow pointing to the Switch to classic link](02-1/media/image69.png)

15. Select **Save and Continue**.

> [!NOTE] 
> If the pop-ups are not enabled on the browser, the classic view will not open. Make sure that you have enabled open popups and redirects on the browser tab. 

![Select Save and continue - screenshot](02-1/media/image103.png)

16. Click **Edit** on the Site Map.

![A Screenshot with an arrow pointing to the pencil icon to edit the site map](02-1/media/image70.png)

17.   Click **+ Add** and select **Area**.

![A Screenshot with an arrow pointing to the add button and a border around the area button](02-1/media/image96.png)

18.   Select the **New Area** you just added.

19. Go to the **Properties** pane, enter **Settings** for **Title**, and enter **area\_settings** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image97.png)

20.  Click **Save and close** to close the sitemap editor.

21.  Click **Save and close** again to close the classic app designer.

22. You should now be back to the new app designer. **Refresh** the browser. Switch to **Navigation** menu.

23.  The new **Settings** area should now be visible in the new app designer. Select the **Setting** area.

24. Click **+ Add** and select **Group**.

![A Screenshot with an arrow pointing to the add drop down menu and a border around the group button](02-1/media/image98.png)

25.  Select the **New Group** you just added.

26.  Go to the **Properties** pane, enter **Taxonomy** for **Title**, and enter **group\_taxonomy** for **ID**.

![A screenshot of the properties pane with the title and ID changed](02-1/media/image72.png)

27.  Select the **Taxonomy** group you just added, click **+ Add** and select **Subarea**

![A Screenshot with an arrow pointing to the subarea button](02-1/media/image73.png)

28.   Select **Table** for **Content type**, **Building** for **Table** and click **Add**.

![A screenshot of the New Subarea window and the content type changed](02-1/media/image74.png)

29.  Select the **Taxonomy** group, click **+ Add** and select **Subarea** again.

30.  Select **Table** for **Content type**, select **Department** for **Table**, and click **Add**.

31. The sitemap should now look like the image below. Click **Save** to save the sitemap.

![A Screenshot with an arrow pointing to the save button on your site map which should have active departments with a name column below](02-1/media/image76.png)

32. Click **Publish** to publish the sitemap and wait for the publishing to complete.
33. **Close** the browser tab. 
34. Open a new tab and navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
35. Select Solutions and click to open the **Company 311** solution.
36. Click **Publish all customizations** and wait for the publishing to complete.

![A Screenshot with an arrow pointing to the publish all customizations button](02-1/media/image77.png)

### Exercise 5: Input data

In this exercise, you will input data to the Dataverse tables.

#### Task 1: Input data

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application you created.

![A Screenshot with an arrow pointing to the company 311 admin app](02-1/media/image80.png)

3.  Click **Change area**.

![A Screenshot with an arrow pointing to chevron icon next to manage problems](02-1/media/image81.png)

4.  Select **Settings** area.

5.  Select **Departments** and click **+ New**.

![A Screenshot with an arrow pointing to the new button at the top of the window](02-1/media/image82.png)

6.  Enter **Facility Maintenance** for **Name** and click **Save**.

![A screenshot showing the change in name to facility maintenance](02-1/media/image83.png)

7.  Click **+ New** again.

8.  Enter **Human Resources** for **Name** and click **Save**.

9.  Click **+ New** one more time.

10. Enter **Marketing** for **Name** and click **Save**.

11. Select **Departments**.

12. You should now have three department Rows. Select **Buildings**.

![A Screenshot with an arrow pointing to the buildings button under taxonomy](02-1/media/image84.png)

13. Click **+ New**.

14. Enter **San Francisco Main Campus** for **Name** and click **Save & Close**.

15. Click **+ New** again.

16. Enter **London Paddington** for **Name** and click **Save & Close**.

17. You should now have two building Rows. Click **Change area**.

![A Screenshot with an arrow pointing to the chevron icon next to settings in the bottom left corner of the window](02-1/media/image85.png)

18. Select **Manage Problems**.

19. Click **+ New**.

![A screenshot of the active problem reports page](02-1/media/image86.png)

20. Enter **Broken door** for **Title**, select **San Francisco Main Campus** for **Building**, enter **The main entrance door will not open all the way** for **Details**, and click **Save**

![A screenshot of the new problem report window with all relevant text in each field](02-1/media/image87.png)

21. Click on the **Photo** Column.

![A Screenshot with an arrow pointing to the upload an image button](02-1/media/image88.png)

22. Select an image from your device. The sample image displayed below can be found [here](02-1/media/image89.png).

23. The image should now show on the form.

![A screenshot of a vector image of a door which should appear](02-1/media/image89.png)

24. Click **Save & Close**.

25. Close the browser tab.

### Exercise 6: Import data

In this exercise, you will import sample data into the environment. Rows are imported by a Power Automate cloud flow that you will first import using a solution.

#### Task 1: Import solution

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.
2.  Select **Solutions** and click **Import**.
3.  Click **Browse**.
4.  Select the **DataImport.zip** solution file located in the lab resources folder and click **Open**.
5.  Click **Next**.
6.  Click **Next** again.
7.  Expand **Select a connection** dropdown and click **+ New connection**.
8.  New tab will open with a prompt to create **Microsoft Dataverse** connection. 
9.  Click **Create**, authenticate if required, wait until new connection is created. Close the browser tab.
10.  Click **Refresh**. Make sure new connection is selected in the dropdown. 
11.  Click **Import** and wait for the message **Solution "Data Import" imported successfully** to appear.
12.  Click **Publish all customizations** and wait for the publishing to complete. 

#### Task 2: Review and run flow

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2. Select **Solutions** and click to open the **Data Import** solution you imported.

3.  Click to open the **Import Data** flow. Click the **Get Started** button on the **Welcome to Power Automate** window.

> [!NOTE]
> If the flow is not opened after clicking on Get Started, then close the current tab, go back to your previous window, click Done and reopen the flow.

![A Screenshot with an arrow pointing to the import data button](02-1/media/image90.png)

4.  Click **Edit**.

5.  Click **Continue**.

6.  Click to expand the **Input** **Data** step.

7.  Review the JSON text in the value Column. This is the data that will be imported into your environment. Note the image data encoded as a text.

8.  Expand the **Each Department** for each control

9.  Expand and review the **Upsert Department** step.

10. Expand and review the rest of the steps.

11. Click **Save** to save the flow.

12. Click on the button and go back to the flow details page.

![A Screenshot with an arrow pointing to the arrow icon to go back](02-1/media/image92.png)

13. Click **Run**.

14. Click **Run flow**.

15. Click **Done**.

16. Wait for the flow run to complete. Click on the **Refresh** button to check if the flow run completed successfully.

![A Screenshot with an arrow pointing to the refresh button in the top right corner and a border around the status showing it has succeeded](02-1/media/image93.png)

17. Close the flow editor browser window or tab.

18. Click **Done** on the popup

#### Task 3: Review imported data

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application.

3.  Select Problem Reports. You should see at least three new Rows.

![A screenshot with a border around your reports, there are three new rows at the bottom](02-1/media/image104.png)

4.  Click to open one of the **Problem Report** Rows.

5.  Click on the **Search** icon of the **Building** lookup and make sure building Rows were imported.

![A screenshot of a border around the building lookup with the building rows imported](02-1/media/image95.png)

6.  Scroll down and click on the **Department** lookup.

7.  Make sure the department Rows got imported.

### **Bonus exercise**

  - Deal with problem report assignment within a department.
