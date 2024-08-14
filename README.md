# 社内ドキュメント検索アプリ
社内SharePoint & OneDrive をユーザー権限で検索できるPower Apps です。また、SharePoint ドキュメントライブラリから取得したファイルを要約する機能、フリーに質問する機能も備わっています。


https://github.com/user-attachments/assets/eecaa929-3b13-4481-9473-0d67b5298d68

> [!note]
> ギークの[Xのポスト](https://x.com/geekfujiwara/status/1823299511055511731)まで是非ご感想を！



## 前提条件

- **ライセンス**
  - Power Apps Premium ライセンス 
  - AI Builder アドインライセンス (クレジットを基本ライセンスに付与されている分を超過して必要な場合)

> [!Note]
> 事前にSharePoint ドキュメントライブラリにファイルを保存しておいてください。


## 制限事項

- AI Builder のAIプロンプトで利用しているモデルはGPT-4oです。そのため128,000トークンが上限です。
- 要約に対応しているファイル形式は以下のとおりです。`doc、docx、epub、eml、htm、html、md、msg、odp、ods、odt、pdf、pps、ppsx、ppt、pptx、rtf、tif、tiff、xls、xlsm、xlsx`
- 検索は、SharePoint 検索できるファイル形式全般に対応しています。


## こだわりポイント

### 1. 様々なファイル形式に対応

PowerPoint ファイルであっても、一度PDFに変換してOCRを行い、AIプロンプトで処理できるようにしています。

こちらはPowerPoint ファイルを入力した結果です。
![image](https://github.com/user-attachments/assets/e750c10d-be7e-495e-a975-d5be05eaccc0)

こちらはExcel ファイルを入力した結果です。
![image](https://github.com/user-attachments/assets/9d3566dd-47b4-4ff3-b6c6-1bb9453f1247)

### 2. 出力結果の保存
出力結果を保存して、後に見直すことができるようにしています。

![image](https://github.com/user-attachments/assets/d0c7e8e2-09fd-48f8-8717-f019451e760f)


### 3. ファイル内容について追加で質問できる

ファイル内容について追加で質問することができ、深堀りすることができます。
![image](https://github.com/user-attachments/assets/b6e3eaa5-5669-4936-a2a8-639a82c772cf)



## ソリューションのインストール方法

1. **Power Apps ポータルにアクセス**
   - [Microsoft Power Apps 作成者ポータル](https://make.powerapps.com/)にログインします。

2. **ソリューションのインポート**
   - [本ソリューションのリリース](https://github.com/geekfujiwara/DocSearch/releases/tag/DocSearch)からソリューションファイルを取得します。

   - Power Apps ポータルで「ソリューション」セクションに移動し、「インポート」ボタンをクリックして、ダウンロードしたソリューションファイルをアップロードします。
![image](https://github.com/user-attachments/assets/e3e3824c-6913-472e-98fe-91c5fbac9b96)

   - 接続 を設定する場面では、すべての接続を更新するようにしてください。
   ![image](https://github.com/user-attachments/assets/58f7fdfb-025d-4b67-943c-c1fbeecdceed)

   - ラベルがないなどの警告が表示されたとしても問題ありません。
![image](https://github.com/user-attachments/assets/34b90db8-365f-48ce-ada9-1a31f31e7d13)


3. **すべてのカスタマイズの公開**
   - インポートしたソリューション内に入ります。**マネージド**のタブにソリューションは入っています。
   - そのまま、すべてのカスタマイズの公開を行います。
  ![image](https://github.com/user-attachments/assets/f5b55468-db6c-4983-8fe0-91a11b748768)

   - インポート後にPower Automate のフローが**オフ**になっている場合は有効化してください。
![image](https://github.com/user-attachments/assets/7316878c-1d62-4dfd-bdb9-69bae5e6ca29)

   - 有効化はこのように行います。
![image](https://github.com/user-attachments/assets/9542e0e3-d00f-41bd-88b7-c000ea394d50)


## アプリの実行

アプリはこちらから起動できます。

![image](https://github.com/user-attachments/assets/bc3d78e0-96e9-4f77-b1da-c1ef93437847)

起動時にはサインインが求められます。これにより、ユーザーの権限でファイル検索が行えるようになっています。

![image](https://github.com/user-attachments/assets/149e26d2-e3e3-4636-be4a-05ca43d03add)

SharePoint に対して検索を行います。

> [!Note]
> 自然言語またはキーワードを入力することができます。

要約が可能なファイル形式の場合は要約ボタンが活性化していますが、要約に対応していないファイル形式については非活性化しています。

![image](https://github.com/user-attachments/assets/b6952a6b-31c9-461f-8799-e6c1762dd071)


## トラブルシューティング
このようなエラーメッセージが表示されましたら、接続情報を更新する必要があります。

![image](https://github.com/user-attachments/assets/e79f72ea-7373-430d-9d77-0b4b46249a00)


ソリューションから要約のフローを選択して確認します。

![image](https://github.com/user-attachments/assets/411f191e-71cd-4cb9-a2ba-3af632eb2e9f)

このようにSharePoint のアクセス許可がエラーになっていることがわかります。

![image](https://github.com/user-attachments/assets/211247c5-5bba-4417-b6f1-0847a573f6ce)

 Power Automate を開き、接続を更新します。

 ![image](https://github.com/user-attachments/assets/ccfdc04f-c533-44e4-9ff7-ae4253b24acd)

接続を更新されるように促されます。

![image](https://github.com/user-attachments/assets/eb21c5fc-6217-416f-8ee3-1b57afd57aa7)

> [!Note]
> もし促されなかった場合、こちらから接続を選択できます。
> ![image](https://github.com/user-attachments/assets/2f945571-00c1-4c7e-8ff3-c134f2951676)

再接続を行います。

![image](https://github.com/user-attachments/assets/ad393eb9-8790-4b4a-a767-7a14c0d43e55)


問題が解消しましたら、アプリに戻ります。

![image](https://github.com/user-attachments/assets/9f8aa94c-4818-42c2-8e20-81471698355d)

要約を実行できるようになりました。

![image](https://github.com/user-attachments/assets/64de52b7-a4f2-4ad3-b302-bcb3fb7ca8bf)

出力結果がこのように表示されました。

![image](https://github.com/user-attachments/assets/41dc6844-e2cc-41d9-ae5b-6ccd3c5f7276)


以上
