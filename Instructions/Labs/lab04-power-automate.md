---
lab:
    title: 'Lab 04: Power Automate'
    module: 'Module 04: Power Automate'
---

> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


# ラボ04： Power Automate

このラボでは、Power Automateクラウドフローを作成して、Company 311 ソリューションのさまざまな部分を自動化します。

プロジェクトを完了するために実装する必要のある要件として、以下が特定されています。 

  - 緊急のメンテナンス問題のエスカレーション、承認、および実行プロセス

  - 問題のステータスの変更についてレポートユーザーに通知する 

  - ビジネスルールを使用してロジックを実装する方法。

## あなたが学ぶこと

  - 自動化をサポートするために（データモデル内の）データ列を設計する方法

  - Microsoft Dataverse Connectorを使用してフローを構築する方法

  - 承認の使用方法

## 高レベルのラボ手順

  - エスカレーションをサポートする列を追加する 
  - エスカレーションを承認するためのフローを構築する
  - ステータスの変更をユーザーに通知するフローを作成する
  - Microsoft Teamsでアダプティブカードとして承認を作成する

## Prerequisites

* **ラボ02.1：データモデルとモデル駆動型アプリ** を完了している必要があります
* **ラボ02.2：ビジネスプロセスフローとビジネスルール** を完了している必要があります

## 始める前に考慮すべきこと

  - 緊急のメンテナンスの問題を特定し、それらをエスカレーションするための最も効率的な方法は何ですか

## 詳細な手順  

### 演習1：通知フローを作成する

この演習では、ステータスが変更されたときに問題を作成者に通知するフローを作成します。

#### タスク1：フローを作成する

このタスクでは、問題レポート行のステータスが変更されたときに通知を送信するフローを作成します。

1.  [Power Apps maker portal](https://make.powerapps.com/) に移動し、正しい環境にいることを確認します。 

2.  **Solutions** を選択し、クリックして **Company 311** ソリューションを開きます。

3.  **+ New** をクリックし、**Cloud Flow** を選択します。

![A screenshot with an arrow pointing to the + New button with a red border around the Cloud Flow link](04/media/image1.png)

4.  **Microsoft Dataverse** コネクタを選択します。 **Microsoft Dataverse** コネクタが表示されていない場合は、**コネクタ** タブを選択してから、**Microsoft Dataverse** を選択します。

5.  **When a row is added, modified or deleted** を選択します。

![A screenshot of a border around the when a row is added, modified, or deleted option](04/media/image2.png)

6.  **Change type** で **Modified** を選択し、**Table name** で **Problem Reports** を選択し、**Scope** で **Organization** を選択して、**Show advanced options** を表示します。

7.  トリガーステップの **Select columns** および **… Menu** ボタンに **statuscode** を入力します。

![A Screenshot with an arrow pointing to the ellipses icon for more options and a border around the select columns statuscode](04/media/image3.png)

8.  **Rename** を選択します。

9.  トリガーステップの名前を **When problem report status changes** に変更します。

10.  **+ New step** をクリックします。

![A Screenshot with an arrow pointing to the add new step button](04/media/image4.png)

11. **Connectors** タブを選択してから、**Microsoft Dataverse** を選択します。 **Get a Row by ID** を選択します。

12. **Table name** に **Users** を選択します。

13. **Row ID** フィールドをクリックし、動的ペインに移動して、**created** を検索し、**Created By (Value)** を1回クリックして追加します。

14. 新しいステップの **Show advanced options** をクリックします。

15. **Select columns** に **internalemailaddress** を入力します。

16. 新しいステップの **… Menu** ボタンをクリックし、**Rename** を選択します。

17. ステップの名前を **Get problem creator** に変更します。

18. **+ New step** をクリックします。

19. **send email** を検索し、**Send an email (V2)** を選択します。

20. **To** 列をクリックして選択し、**Switch to advanced mode** をクリックします。 このボタンをクリックすると、動的ペインの表示と非表示が切り替わります。

![A Screenshot with an arrow pointing to the switch to advanced mode icon](04/media/image5.png)

21. **Get problem creator** ステップから **Primary Email** 列を選択します。

22. **Subject** に **Problem report status change notification** を入力します。

23. **Body** 列をクリックして選択します。

24. **The status of the problem you reported has changed.** と入力し、**[ENTER]** キーを押します。

25. **Problem Title:** と入力し、[動的]ペインに移動して、**title** を検索し、**Title** を選択します。

26. **[ENTER]** キーを押します。

27. Type **Current Status:** go to the Dynamic pane, select the **Expression** tab, paste the expression below, and click **OK**. This expression will show the label of the choice instead of the value.

`triggerOutputs()?['body/_statuscode_label']`

![A Screenshot with an arrow pointing to the ok button under the expression tab with the relevant expression pasted into it](04/media/image6.png)

28. Click on the **… Menu** button of the new step and select **Rename**.

29. Rename the **Notify problem creator**.

30. The step should now look like the image below.

![A screenshot of the modify problem creator window being to primary email, the subject being problem report status change notification, and the body being "The status of the problem you reported has changed" with the problem title and current status as trigger outputs below that](04/media/image7.png)

31. Scroll up change the flow name from Untitled to **Notify Problem Creator.**

32. Click **Save** and wait for the flow to be saved.

![A screenshot of the current flow](04/media/image8.png)

33. **Close** the flow designer browser window or tab.

34. Click **Done** on the popup window.

#### Task 2: Test the flow

In this task, you will test the notify problem creator flow.

1.  Make sure you are still on the [Power Apps maker portal](https://make.powerapps.com/) site and you are in the correct environment.

2.  Select **Apps**, and then select the **Company 311 Admin** Model-driven application. Click **Play**.

3.  Click **+ New**.

4.  Enter **Flow test** for **Title**, select **London Paddington** for **building**, enter **This is a flow test** for **Details**, and click **Save**.

5.  Scroll down and change the **Status Reason** value to **In Progress** and save again.

6.  Close the application browser window or tab.

7.  You should now be back to the [Power Apps maker portal](https://make.powerapps.com/)

8.  Select **Solutions** and click to open the **Company 311** solution.

9.  Locate and click to open the **Notify Problem Creator** flow you created.

10. You should see a succeeded flow run in the **28-day run history section**. Click to open the run.

![A Screenshot with an arrow pointing to the start date of the 28-day run history section](04/media/image9.png)

11. All the flow steps should have a **green** check mark.

12. Click **App launcher** and select **Outlook**.

![A Screenshot with an arrow pointing to the app launcher and a border around outlook](04/media/image10.png)

13. You should get an email from the flow. Click to open the email.

14. The email should look like the image below.

![A screenshot of the email you should receive with the status of the problem, problem title, and its current status](04/media/image11.png)

### Exercise 2: Build escalation flow

In this exercise, you create add two new Columns to the problem report Table and create escalation flow.

#### Task 1: Add Columns

In this task, you add a new Columns to the problem report Table.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Locate and click to open the **Problem Report** Table.

4.  Make sure you have the **Columns** tab selected and click **+ Add Column**.

5.  Enter **Estimated Cost** for **Display name**, select **Currency** for **Data type** and click **Done**.

6.  Click the **Save Table** located on bottom right of the screen.

7.  Select the **Forms** tab.

8.  Click to open the **Information** form of type **Main**.

9.  Add **Estimated Cost** Column to the form and place it below the **Status Reason** Column.

10. Add the **Assign to** Column and place it below the **Estimated Cost** Column.

11. The **Resolution details** section of the form should now look like the image below. Click **Save**.

![A Screenshot with a border around estimated cost and assign to placed correctly and an arrow pointing to the save button](04/media/image12.png)

12. Click on the **Back** button located on the top left of the screen.

13. Select **Solution**, click **Publish all customizations**, and wait for the publishing to complete.

#### Task 2: Build escalation flow

In this task, you will create the escalation flow.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Click **+ New** and select **Cloud flow**.

4.  Search for **when a row is added** and select **When a row is added, modified, or deleted**  from **Microsoft Dataverse** connector.

5.  Select **Added or Modified** for **Change type**, select **Problem Reports** for **Table name**, select **Organization** for **Scope** and click **Show advanced options**.

6.  Enter **lh_estimatedcost,lh_assignto** for **Select columns** and click **Hide advanced options**.

7.  Click on the **… Menu** button of the trigger step and select **Rename**.

8.  Rename the trigger step **When a problem report is created or updated**.

9.  Click **+ New step**.

10. Search for **Condition** and Select **Condition** control.

11. Click to select the first **Choose a value** Column.

12. Go to the Dynamic content pane, search for **estimated** and select **Estimated Cost**.

![A screenshot of the dynamic content pane with the word estimated in the search bar](04/media/image13.png)

13. Select **is greater than** in the second field and enter **1000** in the third field.

14. Rename the condition step to **Check if cost is greater than 1000**.

15. Go to the **If yes** branch and click **Add an action**.

16. Search for **Get a row** and select **Get a row by ID** from **Microsoft Dataverse**.

17. Select **Users** for **Table name**.

18. Click to select the **Row ID** Column and select **Assign to (Value)** from the **Dynamic content** pane.

19. Click **Show advanced options**.

20. Enter **internalemailaddress** for **Select columns**.

21. Click **Hide advanced option**.

22. Rename the **Get a Row by ID** step **Get user**.

23. Click **Add and action**.

24. Search for **approval** and select **Start and wait for an approval**.

25. Select **Approve/Reject - Everyone must approve** for **Approval type**.

26. Enter **Cost approval required** for **Title**.

27. Click to select the **Assigned to** Column.

28. Go to the **Dynamic content** pane and select **Primary Email** from the **Get user** step.

29. Paste the markdown text below in the **Details** Column.

> \#\# URGENT Approval Required
>
> This is \*\*very\*\* expensive item with the estimated cost of

30. Place your cursor after cost of, go to the Dynamic content pave, select the Expression tab, paste the expression below, and click **OK**.

`formatNumber(triggerOutputs()?['body/lh_estimatedcost'], 'C2')`

![A Screenshot with an arrow pointing to the ok button in the expression tab under the pasted expression](04/media/image14.png)

31. Click **Add an action**.

32. Search for **condition** and select **Condition** control.

33. Click to select the first **Choose a value** Column.

34. Go to the **Dynamic content** pane, search for **Outcome** and select **Outcome**.

35. Select **equals to** in the second field and type **Reject** for value in the third field.

36. Go to the **If yes** branch and click **Add an action**.
37. Search for **update a Row** and select **Update a Row** from **Microsoft Dataverse**.

38. Select **Problem Reports** for **Table name**.

39. Click to select the **Row ID** Column.

40. Go to the **Dynamic content** pane, search for **problem report** and select **Problem Report**.

41. Click **Show advanced options**.

42. Click to select the **Resolution** Column, go to the **Dynamic content** pane and select **Response summary**.

43. Select **Won’t fix** for **Status Reason**.

44. Rename the step **Update problem report**.

45. Scroll up and rename the flow **Escalate Expense Approval**.

46. Click **Save**.

![A screenshot of the current flow](04/media/image15.png)

47. Close the flow designer browser window or tab.

48. Click **Done** on the popup.

#### Task 3: Test flow

In this task, you will test the escalation flow

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application.

3.  Click to open one of the **Problem Report** rows.

4.  Scroll down, enter **2500** for **Estimated Cost**, assign it to **yourself** (for test purposes) and click **Save**.

5.  Navigate to [Power Automate](https://us.flow.microsoft.com/en-us/)

6.  Expand **Action Items** and select **Approvals**.

7.  You should see at least one approval in the received tab. Click to open the approval. It can take around 10-15 minutes for approvals to show up here on the first run.

![A Screenshot with an arrow pointing to the cost approval required request](04/media/image16.png)

8.  Select **Reject**, enter **We don't have the funds for this item** for **comment**, and click **Confirm**.

![A screenshot of the details of the request with the relevant text in each field](04/media/image17.png)

9.  Go back to the **Company 311 Admin** application.

10. Change the view to **My Reports** and click to open the same row you change the estimated cost.

11. The **Status Reason** should be set to **Won’t fix** and the **Resolution** should contain the details of Approver, Response, Request Date and Response Date.

12. Click **Save**, if you have not done so previously.

![A screenshot of the status reason and resolution matching the values and text you put into the request](04/media/image18.png)

### Exercise 3: Send approval requests as adaptive card in Microsoft Teams

In this exercise, you will setup a team in Microsoft Teams dedicated to the Company 311 applications. You will modify the flow to send the approval request as an adaptive card in Teams chat instead of an approval message.

* Task 1: Setup Company 311 Team
* Task 2: Modify flow to send adaptive card in Teams chat
* Task 3: Test adaptive card

#### Task 1: Setup Company 311 Team

In this task you will setup a Microsoft Teams team for the Lamna Healthcare Company, if you have not done so in previous exercises.

1.  Navigate to [Microsoft Teams](https://teams.microsoft.com) and sign in with the same credentials you have been using previously.

2.  Select **Use the web app instead** on the welcome screen.

![A screenshot of the Microsoft Teams landing page with a border around the use the web app instead button](04/media/image-5-teams.png)

3.  When the Microsoft Teams window opens, dismiss the welcome messages.

4.  On the bottom left corner, choose **Join or create a team**.

5.  Select **Create a team**.

![A screenshot with a box around the join or create a team button at the bottom of the window and a border around the create a team button](04/media/image-5-createteam.png)

6.  Press **From scratch**.

7.  Select **Public**.

8.  For the Team name choose **Company 311** and select **Create**.

9.  Select **Skip** adding members to Company 311.


#### Task 2: Modify flow to send adaptive card in Teams chat

In this task you will replace the approval sent by email with the adaptive card.

1. Locate **Start and wait for an approval** step created earlier in **Exercise 2, Task 2**.
2. Select **...** then select **Delete**.
3. Click **+** between the steps to insert a new step then select **Add an action**.
4. Search for **approval** and select **Create an approval**.
5. Select **Approve/Reject - Everyone must approve** for **Approval type**.
6. Enter **Cost approval required** for **Title**.
7. Click to select the **Assigned to** Column.
8. Go to the **Dynamic content** pane and select **Primary Email** from the **Get user** step.
9. Paste the markdown text below in the **Details** Column.

> \*\*{title}\*\*
>
> 
>
> {details}
>
> 
>
> This is a \_very\_ expensive item with the estimated cost of

10. Select **{title}** placeholder, go to the **Dynamic content** pane, locate and select **Title** Column from **When a problem report is created or updated** step.

11. Select **{details}** placeholder, go to the **Dynamic content** pane, locate and select **Details** Column from **When a problem report is created or updated** step.

12. Place your cursor after **cost of** , go to the **Dynamic content** pane, select the **Expression** tab, paste the expression below, and click OK.

`formatNumber(triggerOutputs()?['body/lh_estimatedcost'], 'C2')`

13. Your step should look like the following:

![A screenshot of the create an approval window with the following. Approval type as approve/reject - everyone must approve, title as cost approval required, assigned to primary email, details as title, details, some text and format number, item link, and item link description](04/media/image-5-create-approval.png)

14. Click **+** then select **Add an action**.

15. Search for **teams** and select **Post adaptive card in a chat or channel** action.

16. Select **Flow bot** for Post as and select **Chat with Flow bot** for Post in.
17. Click to select the **Recipient** field.

18. Go to the **Dynamic content** pane and select **Primary Email** from the **Get user** step.

19. Click to select **Adaptive Card** field.

20. Go to the **Dynamic content** pane and select **Teams Adaptive Card** from the **Create an approval** step.
21. Post adaptive card in chat or channel should look like the image below.

![A screenshot of the post adaptive card in a chat or channel pane](04/media/image-5-post-adaptive-card.png)

22. Select **+** then select **Add an action**.

23. Search for **approval** and select **Wait for an approval** action.

24. Select **Approval ID** Column.

25. Go to the **Dynamic content** pane and select **Approval ID** from the **Create an approval** step.

    ![A screenshot of the wait for an approval panel with approval ID in the approval ID field](04/media/image-5-wait-for-approval.png)

26. You now have replaced **Start and wait for an approval** step with the following:

![A screenshot of the current flow with: create an approval, post adaptive card in a chat or channel, and wait for an approval](04/media/image-5-replaced-approval.png)

25. Expand **Condition 2** step. The left side of the condition should be empty because it was referring the step which is now removed. 
26. Go to the **Dynamic content** pane, search for **outcome,** and select **Outcome** from **Wait for an approval** step. 
27. Locate **Update problem report** step under **If yes** branch.
28. Click **Show advanced options**.
29. Click to select the **Resolution** Column, go to the **Dynamic content** pane, and select **Response summary** from **Wait for an approval** step.
30. Click **Save**.
31. Close the flow designer browser window or tab.
32. Click **Done** on the popup.

#### Task 3: Test flow

In this task, you will test the escalation flow with the Teams and adaptive cards.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) and make sure you are in the correct environment.

2.  Select **Apps** and click to open the **Company 311 Admin** application.

3.  Click to open one of the **Problem Report** Rows.

4.  Scroll down, enter any amount greater than **1000** for **Estimated Cost**, assign it to **yourself** (for test purposes) and click **Save**.

5.  Navigate to [Microsoft Teams](https://teams.microsoft.com)

6.  Select **Chat**.

7. You should see the Cost Approval Required Adaptive Card.

![A screen shot of the request for cost approval pane](04/media/image-5-sample-adaptive-card.png)  

8. Press **Reject** button and enter a comment of your choice in the Comments area, for example **The item is too expensive**.

9. Select **Submit**.  The card will become read-only.

![A screenshot of the request once you have rejected it](04/media/image-5-readonly-card.png)

10. Go back to the **Company 311 Admin** application.

11. Change the view to **My Reports** and click to open the same Row you change the estimated cost.

12. The **Status Reason** should be set to **Won’t fix** and the **Resolution** should contain the details of Approver, Response, Request Date and Response Date.

![A screenshot of the status reason and resolution matching the details of your response to the request](04/media/problemreportadaptivecard.png)

## **Discussion**

  - Would creating a bool Column for Approved/Rejected be better?
  - What are the pros and cons of using Microsoft Teams over regular email?

## **Bonus exercises**

  - Add ability for the users to subscribe to the reported problems and only notify if there is a subscription. 
  - Auto-subscribe creator of the problem report.
  - How to find out previous value of status reason?
  - Create your own adaptive card using [Adaptive Cards Designer](https://adaptivecards.io/designer/).
