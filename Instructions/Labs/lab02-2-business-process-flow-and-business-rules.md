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

12. 新しいデータステップを選択し、**Properties** ペインに移動し、**Data Field** で **Department** を選択して、**Apply** をクリックします。

13. **Route** ステージは次の画像のようになります。

![A screenshot of the completed route stage with three data steps: building, location, and department](02-2/media/image8.png)

14. **+ Add** をクリックし、**Add Stage** を選択します。

15. **Route** ステージの後に新しいステージを追加します。

16. ステージを選択し、**Properties** ペインに移動し、**Display Name** に **Fix** と入力して、**Apply** をクリックします。

17. **Fix** ステージの **Details** を展開します。

18. **Fix** ステージの **Data Step \#1** を選択します。

19. **Properties** ペインに移動し、**Data Field** で **Assign to** を選択して、**Apply** をクリックします。

20. **+ Add** をクリックし、**Add Stage** を選択します。

21. **Fix** ステージの後に新しいステージを追加します。

22. 新しいステージを選択し、**Properties** ペインに移動し、**Display Name** に **Resolve** と入力して、**Apply** をクリックします。

23. **Resolve** ステージの **Details** を展開します。

24. **Resolve** ステージの **Data Step \#1** を選択します。

25. **Properties** ペインに移動し、**Data Field** で **Resolution** を選択して、**Apply** をクリックします。

26. **+ Add** をクリックし、**Add Data Step** を選択します。

27. **Resolution** データステップの下に新しいデータステップを追加します。

28. 新しいデータステップを選択し、**Properties** ペインに移動し、**Date Field** で **Resolved on** を選択して、**Apply** をクリックします。

29. これで、ビジネスプロセスフローは次の画像のようになります。 **Save** をクリックします。

![A Screenshot of a Business Process Designer with an arrow pointing to the save button](02-2/media/image9.png)

30. **Activate** をクリックします。

31. ポップアップでもう一度 **Activate** をクリックします。

32. 画面の左下にある **Status: Active** を確認します。

    ![A screeshot of a high-level overview of a business process with the words "Status: Active" highlighted in the left bottom corner](02-2/media/image28.png)

33. プロセスエディタのブラウザウィンドウまたはタブを閉じます。

#### タスク3：ビジネスプロセスフローをソリューションに追加する

このタスクでは、作成したビジネスプロセスフローをCompany311ソリューションに追加します。

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **+ Add existing** を追加をクリックし、**Process** を選択します。

![A Screenshot with an arrow pointing to the drop down icon next to the add existing button and a border around the process button](02-2/media/image10.png)

4.  問題を検索し、**Problem resolution process** を選択して、**Add** をクリックします。

![A screenshot of the add existing processes window with problem resolution process selected](02-2/media/image11.png)

5.  **Publish all customizations** をクリックして、公開が完了するのを待ちます。

### 演習2：ビジネスルールを作成する

この演習では、問題の完了を解決せずにブロックするビジネスルールを作成します。

#### タスク1：ビジネスルールを作成する

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **Problem Report** テーブルを探し、開きます。

4.  **Business rules**　タブを選択し、**Add Business rule** をクリックします。

![A screenshot of the business rules tab](02-2/media/image12.png)

5.  **Scpe** が **Entity** に設定されていることを確認し、**Show details** シェブロンをクリックします。

![A Screenshot with an arrow pointing to the drop down icon next to the text problem report: new business rule and a border around the scope set to entity on the right hand side of the page](02-2/media/image13.png)

6. **Business rule name** を **Completion rule** に変更し、**Hide details** をクリックします。

![A screenshot of a business rules property pane with an arrow pointing to the shevron that collapses the entire property pane](02-2/media/image29.png)

7. **Condition** を選択します。

8. **Properties** ペインに移動し、**Display name** を **Resolution required** に変更します。

9. **Rule 1** まで下にスクロールし、**Field** に **Status Reason** を選択し、**Operator** に **Equals** を選択し、**Type** に**Value** を選択します。 **Value** で **Completed** を選択し、**Apply** をクリックします。

![A screenshot of the rules panel](02-2/media/image14.png)

10. **+ New** をクリックします。

![A Screenshot with an arrow pointing to the new button](02-2/media/image15.png)

11. **Rule 2** まで下にスクロールし、**Field** に **Resolution** を選択し、**Operator** に **Does not contain data** を選択し、**And** が選択されていることを確認します

![A screenshot of the rules panel if you scroll further down with the relevant text in each field](02-2/media/image16.png)

12. **+ Add** をクリックします。

![A Screenshot with an arrow pointing to the add button](02-2/media/image17.png)

13. **Add show error message** を選択します。

14. 条件の　**true** パスにアクションを追加します。

![A Screenshot with an arrow pointing to the add button on the true path of the condition](02-2/media/image18.png)

15. 新しいアクションを選択し、**Properties** ペインに移動し、**Display Name** に **Show message** と入力し、**Field** に **Status Reason** を選択して、**Message**  に **The Problem must have a resolution before it can be closed** を入力し、**適用** をクリックします。

![A screenshot of the properties panel with the relevant text in the fields](02-2/media/image19.png)

16. ビジネスルールは次の画像のようになります。 **Save** をクリックします。

![A Screenshot with an arrow pointing to the save button](02-2/media/image20.png)

17. **Activate** をクリックします。
18. ポップアップで再度 **Activate** をクリックします。
19. アクティベーションを確認します。
20. プロセスエディタのブラウザウィンドウまたはタブを閉じます。
21. **Done** をクリックします。

### 演習3：テストプロセス

この演習では、作成したビジネスプロセスフローとビジネスルールをテストします。

#### タスク1：プロセスをテストする

1.  [Power Apps maker portal](https://make.powerapps.com/) ページに移動し、正しい環境にいることを確認します。 

2.  **Apps** を選択し、クリックして**Company 311 Admin** アプリケーションを開きます。

![A Screenshot with an arrow pointing to the company 311 admin option in apps](02-2/media/image21.png)

3.  **Problem Reports** を選択し、**+ New** をクリックします。

4.  ビジネスプロセスフローのステージが表示されます。 **Title** に **Dark parking lot** を入力し、**Building** に **London Paddington** を選択し、**Details** に **There are no lights at the north end of the parking lot** と入力します。 **Save** をクリックします。

![A screenshot of the new problem report](02-2/media/image22.png)

5.  **Route** ステージをクリックします。

![A Screenshot with an arrow pointing to the route stage at the top of the page](02-2/media/image23.png)

6. **Location** に **North-end** と入力し、**Department** に **Facility Maintenance** を選択して、**Next stage** のステージを選択します。

   > [!NOTE]
   >
   > 次のステージ オプションが表示されていない場合は、ページを更新してください。
  
   ![A screenshot of the drop down from the route stage with the relevant options selected and typed in](02-2/media/image24.png)

7. **Assign to** のユーザーを選択し、**Next stage** をクリックします。

8. **Resolved on** の日付と時刻を選択し、**Resolution** 値を空のままにします。

9. Resolution details セクションまで下にスクロールし、**Status Reason** で **Completed** を選択します。 ビジネスルールのエラーメッセージが表示されます。

![A screenshot of the error message under status reason](02-2/media/image25.png)

10. **Resolution** を入力します。エラーメッセージは消えるはずです。

![A screenshot of the form without the error message after resolution](02-2/media/image26.png)

11. 行を **Save** します。

**Next** をクリックして、次のラボに進みます。

