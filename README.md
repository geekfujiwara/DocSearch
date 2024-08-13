# 社内ドキュメント検索アプリ
社内SharePoint & OneDrive をユーザー権限で検索できるPower Apps です。また、SharePoint ドキュメントライブラリから取得したファイルを要約する機能、フリーに質問する機能も備わっています。

> [!Note]
> 事前にSharePoint ドキュメントライブラリにファイルを保存しておいてください。

## 前提条件

- **ライセンス**
  - Power Apps Premium ライセンス 
  - AI Builder アドインライセンス (クレジットを基本ライセンスに付与されている分を超過して必要な場合)

## 制限事項

- AI Builder のAIプロンプトで利用しているモデルはGPT-4oです。そのため128,000トークンが上限です。
- 要約するドキュメントはPDF、または画像フォーマットである必要があります。
- 対応しているファイル形式は以下のとおりです。`doc、docx、epub、eml、htm、html、md、msg、odp、ods、odt、pdf、pps、ppsx、ppt、pptx、rtf、tif、tiff、xls、xlsm、xlsx`

## ソリューションのインストール方法

1. **Power Apps ポータルにアクセス**
   - [Microsoft Power Apps 作成者ポータル](https://make.powerapps.com/)にログインします。

2. **ソリューションのインポート**
   - [本ソリューションのリリース](https://github.com/geekfujiwara/DocSearch/releases/tag/DocSearch)からソリューションファイルを取得します。

   - Power Apps ポータルで「ソリューション」セクションに移動し、「インポート」ボタンをクリックして、ダウンロードしたソリューションファイルをアップロードします。
![image](https://github.com/user-attachments/assets/e3e3824c-6913-472e-98fe-91c5fbac9b96)

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

以上
