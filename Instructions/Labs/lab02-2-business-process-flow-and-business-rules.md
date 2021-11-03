---
lab:
    title: 'Lab 02.2: Business Process Flows and Business Rules'
    module: 'Module 02: Building model-driven apps'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# ラボ02.2：ビジネスプロセスフローとビジネスルール

このラボでは、ビジネスプロセスフローとビジネスルールを追加することで、データモデルを強化し、アプリの動作を改善します。

## あなたが学ぶこと

  - ビジネスプロセスフロー（BPF）の段階を特定する方法

  - BPFを作成して使用する方法

  - ビジネスルールを使用してロジックを実装する方法

## 高レベルのラボ手順

  - 演習1 - 問題レポートのBPFライフサイクルを作成する
    
      - Route 
      
      - Fix 
      
      - Resolved 

  - 演習2 – 解決せずにクローズを許可しないビジネスルール

## 前提条件

* **ラボ02.1：データモデルとモデル駆動型アプリ** を完了している必要があります

## 詳細な手順

### 演習1：ビジネスプロセスフローを作成する

この演習では、問題レポートテーブルのビジネスプロセスフローを作成します。

#### タスク1：テーブルをカスタマイズする

このタスクでは、ルックアップ列を問題レポートテーブルに追加します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **Problem Report** テーブルを探し、開きます。

4.  **Columns** タブがあることを確認し、**+ Add Column** をクリックします。

5.  **Display name** に **Assign to** を入力し、**Data type** に **Lookup** を選択し、**Related table** に**User** を選択して、**Done** をクリックします。

![A screenshot of the assign to panel with all relevant values in each field](02-2/media/image1.png)

6.  **Save Table** をクリックします。

7.  ソリューション名をクリックして、ソリューションに戻ります。

![A Screenshot with an arrow pointing to the solution name](02-2/media/image2.png)

8.  **Publish all customizations** をクリックして、公開が完了するのを待ちます。

#### タスク2：ビジネスプロセスフローを作成する

このタスクでは、問題レポートテーブルのビジネスプロセスフローを作成します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Flows** を選択します。

3.  **Business process flows** タブを選択し、**+ New** をクリックします。

![A Screenshot with an arrow pointing to the new button](02-2/media/image3.png)

4.  **Flow Name** に**Problem resolution process** を入力し、**Table** に **Problem Report** を選択して、**Create** をクリックします。

5.  **New stage** を選択し、**Properties** ペインに移動し、**Display Name** を **Route** に変更して、**Apply** をクリックします。

![A screenshot of the new stage and properties pane](02-2/media/image4.png)

6.  **Route** ステージの **Details** を展開します。

![A Screenshot with an arrow pointing to the details button](02-2/media/image5.png)

7.  **Data Step \#1** を選択し、**Properties** ペインに移動し、**Data Field** の **Building** を選択して、**Apply** をクリックします。

![A screenshot of the new stage with data step one selected and the properties pane open](02-2/media/image6.png)

8.  **+ Add** をクリックし、**Add Data Step** を選択します。

![A Screenshot with an arrow pointing to the add button and a border around add data step button](02-2/media/image7.png)

9. **+** オプションを選択して、**Building** データステップの下にデータステップを追加します。

   ![A screenshot of a data step being about to be added to the process stage](02-2/media/image27.png)

10. 新しいデータステップを選択し、**Properties** ペインに移動し、**Data Field** で **Location** を選択して、**Apply** をクリックします。

11. **+ Add** をもう一度クリックし、**Add Data Step** を選択します。

12. Select the new data step, go to the **Properties** pane, select **Department** for **Data Field**, and click **Apply**.

13. The **Route** stage should now look like the image below.

![A screenshot of the completed route stage with three data steps: building, location, and department](02-2/media/image8.png)

14. Click **+ Add** and select **Add Stage**.

15. Add the new stage after the **Route** stage.

16. Select the stage, go to the **Properties** pane, enter **Fix** for **Display Name**, and click **Apply**.

17. Expand **Details** of the **Fix** stage.

18. Select **Data Step \#1** of the **Fix** stage.

19. Go to the **Properties** pane, select **Assign to** for **Data Field** and click **Apply**.

20. Click **+ Add** and select **Add Stage**.

21. Add the new stage after the **Fix** stage.

22. Select the new stage, go to the **Properties** pane, enter **Resolve** for **Display Name** and click **Apply**.

23. Expand **Details** of the **Resolve** stage.

24. Select **Data Step \#1** of the **Resolve** stage.

25. Go to the **Properties** pane, select **Resolution** for **Data Field** and click **Apply**.

26. Click **+ Add** and select **Add Data Step**.

27. Add the new data step below the **Resolution** data step.

28. Select the new data step, go to the **Properties** pane, select **Resolved on** for **Date Field** and click **Apply**.

29. The Business process flow should now look like the image below. Click **Save**.

![A Screenshot of a Business Process Designer with an arrow pointing to the save button](02-2/media/image9.png)

30. Click **Activate**.

31. Click **Activate** again on the pop-up.

32. Confirm that **Status: Active** on the bottom-left side of the screen.

    ![A screeshot of a high-level overview of a business process with the words "Status: Active" highlighted in the left bottom corner](02-2/media/image28.png)

33. Close the process editor browser window or tab.

#### Task 3: Add business process flow to solution

In this task, you will add the business process flow you created to the Company 311 solution.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Click **+ Add existing** and select **Process**.

![A Screenshot with an arrow pointing to the drop down icon next to the add existing button and a border around the process button](02-2/media/image10.png)

4.  Search for problem, select **Problem resolution process**, and click **Add**.

![A screenshot of the add existing processes window with problem resolution process selected](02-2/media/image11.png)

5.  Click **Publish all customizations** and wait for the publishing to complete.

### Exercise 2: Create business rule

In this exercise, you will create a business rule that will block completion of problems without resolution.

#### Task 1: Create business rule

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Locate and click to open the **Problem Report** Table.

4.  Select the **Business rules** tab and click **Add business rule**.

![A screenshot of the business rules tab](02-2/media/image12.png)

5.  Make sure the **Scope** is set to **Entity** and click **Show details** chevron.

![A Screenshot with an arrow pointing to the drop down icon next to the text problem report: new business rule and a border around the scope set to entity on the right hand side of the page](02-2/media/image13.png)

6. Change **Business rule name** to **Completion rule** and click **Hide details** chev

![A screenshot of a business rules property pane with an arrow pointing to the shevron that collapses the entire property pane](02-2/media/image29.png)

7. Select the **Condition**.

8. Go to the **Properties** pane and change the **Display name** to **Resolution required**.

9. Scroll down to **Rule 1**, select **Status Reason** for **Field**, select **Equals** for **Operator**, select **Value** for **Type**, select **Completed** for **Value**, and click **Apply**.

![A screenshot of the rules panel](02-2/media/image14.png)

10. Click **+ New**.

![A Screenshot with an arrow pointing to the new button](02-2/media/image15.png)

11. Scroll down to **Rule 2**, select **Resolution** for **Field**, select **Does not contain data** for **Operator**, make sure **And** is selected for **Rule Logic**, and click **Apply**.

![A screenshot of the rules panel if you scroll further down with the relevant text in each field](02-2/media/image16.png)

12. Click **+ Add**.

![A Screenshot with an arrow pointing to the add button](02-2/media/image17.png)

13. Select **Add show error message**.

14. Add the action on the **true** path of the condition.

![A Screenshot with an arrow pointing to the add button on the true path of the condition](02-2/media/image18.png)

15. Select the new action, go to the **Properties** pane, enter **Show message** for **Display Name**, select **Status Reason** for **Field**, enter **The Problem must have a resolution before it can be closed** for **Message**, and click **Apply**.

![A screenshot of the properties panel with the relevant text in the fields](02-2/media/image19.png)

16. The business rule should now look like the image below. Click **Save**.

![A Screenshot with an arrow pointing to the save button](02-2/media/image20.png)

17. Click **Activate**.
18. Click **Activate** again on the pop-up.
19. Confirm activation.
20. Close the process editor browser window or tab.
21. Click **Done**.

### Exercise 3: Test processes

In this exercise, you will test the business process flow and the business rule you created.

#### Task 1: Test processes

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application.

![A Screenshot with an arrow pointing to the company 311 admin option in apps](02-2/media/image21.png)

3.  Select **Problem Reports** and click **+ New**.

4.  You should see the business process flow stages. Enter **Dark parking lot** for **Title**, select **London Paddington** for **Building**, enter **There are no lights at the north end of the parking lot** for **Details**, and click **Save**.

![A screenshot of the new problem report](02-2/media/image22.png)

5.  Click on the **Route** stage.

![A Screenshot with an arrow pointing to the route stage at the top of the page](02-2/media/image23.png)

6. Enter **North-end** for **Location**, select **Facility Maintenance** for **Department** and select the **Next stage** stage.

   > [!NOTE]
   >
   > If the Next Stage option is not visible, then refresh the page.
  
   ![A screenshot of the drop down from the route stage with the relevant options selected and typed in](02-2/media/image24.png)

7. Select a user for **Assign to** and click **Next stage**.

8. Select date and time for the **Resolved on** and leave the **Resolution** value empty.

9. Scroll down to the resolution details section and select **Completed** for **Status Reason**. You should see the business rule error message.

![A screenshot of the error message under status reason](02-2/media/image25.png)

10. Provide **Resolution**. The error message should go away.

![A screenshot of the form without the error message after resolution](02-2/media/image26.png)

11. **Save** the Row.

Click **Next** to advance to the next lab.

