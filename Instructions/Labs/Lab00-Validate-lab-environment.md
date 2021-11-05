---
lab:
    title: 'Lab 00: Validate lab environment'
    module: 'Module 01: Course introduction'
---


> [!NOTE]
> Effective November 2020:
> - Common Data Service has been renamed to Microsoft Dataverse. [Learn more](https://aka.ms/PAuAppBlog)
> - Some terminology in Microsoft Dataverse has been updated. For example, *entity* is now *table* and *field* is now *column*. [Learn more](https://go.microsoft.com/fwlink/?linkid=2147247)
>


モジュール0：コース紹介
=================================

## 実験室 - ラボ環境を検証します

シナリオ
--------

このモジュール0ラボでは、Power Platform の試用テナントを取得し、Power Platform管理センターにアクセスします。 管理センターでは、コース中に設定のための個々の環境を作成します。

練習1  - あなたの Power Platform の試用テナントを取得します 
------------------------------------------

1. 許可された Lab Hoster から、あなたの **Microsoft 365 credentials** をコピーします。
2. [Power Apps](https://.<powerapps.microsoft.com) に移動し、**Start free** をクリックします。
3. **Work email** の下で、Microsoft 365 Credentials から Eメールアドレスを入力し、 **Next** をクリックします。
4. Microsoftの既存のアカウントを持っていることを示すプロンプトが表示されます。 **Sign in**を選択します。
5. 認定ラボ ホスティング業者から提供されたパスワードを入力します。
6. サインイン を継続するには、**Yes** を選択します。
7. 国または地域と電話番号を入力してください。 **Get Started** を選択します。
8. 再度、**Get Started** を選択します。

> [!NOTE]
> 
> 「申し訳ありませんが、接続が切断されました」というエラーが発生した場合は、以下の手順を実行できます。 そうでない場合は、**演習2** に進むことができます。
>
> 1. [Power Apps Maker Portal](https://make.powerapps.com) に移動します。 
> 2. ページのヘッダーの右上隅から **歯車アイコン**（設定）を選択します。
> 3. **Plan(s)** を選択し、**Power Apps Per User Plan Trial** があるかどうかを確認します。 
> 4. 上記のライセンスをお持ちの場合は、**演習2** に進んでください。それ以外の場合は、**演習1** を繰り返してください。

演習2 - 環境を作成する
------------------------------------------

この演習では、このトレーニングのラボ作業の大部分を実行するために使用する　**Practice** 環境を作成します。

### タスク1 - 環境を作成する

1.  [Power Platform 管理センター]<https://admin.Powerplatform.microsoft.com）に移動し、再度プロンプトが表示されたら、Microsoft365の資格情報を使用してログインします。

2. **Environment** を選択し、**+ 新規** を選択します。

    - **Name** から **[my initials] Practice**　を入力します。(例: AJ Practice.)
    
    - **Type** から **Trial** を選択します。
    
    - **Create a database for this environment?** を **Yes** に変更します。
    
    - 他の項目すべてをデフォルトのままにして **Next** を選択します。

    - 次のタブで、すべての項目をデフォルトのままにして、 **Save** を選択します。

3. **Practice** 環境が、環境リストに表示されます。 

4. ご利用の環境では、プロビジョニングに数分かかる場合があります。必要に応じてページを更新します。環境の準備ができたら、名前の横にある楕円をクリックしてドロップダウンメニューを展開し、**Setting** を選択し、 **Practice** を選択します。

5.  関心ある内容を変更を加えないで、 **Settings** を確認します。
