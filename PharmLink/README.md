# **PharmLink: 在庫管理システム**

## **概要**
PharmLinkは、各店舗の在庫を共有し、在庫移動や残数の管理を行うためのシンプルな在庫管理システムです。
Googleスプレッドシートを使用し、各店舗の在庫を一元管理しながら、定期的な在庫移動や処理を行うために設計されています。
##　**特徴**
- **店舗ごとの在庫管理** :各店舗で在庫を独自に管理し、必要なデータが自動的に集約シートに反映されます。
- **簡単な操作** : Excel関数やGoogleスプレッドシートの基本機能を利用して、簡単に在庫管理が可能です。
- **在庫移動と残数管理** : 店舗間での在庫移動をシステム化し、残数管理を効率化します。

## **システム構成**

### **1. 共有シート　（PharmLink）**
- **A列: 薬品ID** - 各薬品に一意のIDが付与されます。
- **B列: 薬品名** - 薬品の名称（規格含む）。
- **C列: 期限** - 薬品の有効期限。
- **D列: ロット番号** - 薬品のロット番号。
- **E列: 不動在庫数** - 不動となっている在庫の数量。
- **F列: 備考** - 特記事項
- **G列: 店舗名** - 現在在庫がある店舗の名前
- **H列: 引き取り可能店舗** - 他店舗から引き取り可能な場合、各自で自分の店舗名を設定。
- **I列: 引き取り可能数量** - 他店舗から引き取れる数量を記載。
- **J列: 残数** - 引き取り可能数量を引いた残りの数量
- **K列: 発送状況** - 発送済みかどうかを手動で記入
- **L列: 受け取り状況** - 受け取り済みかどうかを手動で記入
- **M列: 処理済み** - 発送・受け取りが完了するとシート関数で”〇”を自動表示

### **2.各店舗シート**
- 各店舗ごとの在庫管理用シート。
- **A列: 薬品ID** - 各薬品のIDを保持
- **B列: 薬品名** - 各店舗ごとの在庫名を管理
- **C列: 期限** - 在庫の期限を管理。
- **D列: ロット番号** - ロット番号を記録。
- **E列: 不動在庫数** - 店舗ごとの不動在庫数
- **F列: 備考** - 備考欄。

### **3. 履歴シート**
- 共有シートや店舗シートから削除されたデータが履歴として記録されます。

## **使用方法**

### **1. 新不動在庫の登録**
- 各店舗シートに新しい在庫情報（薬品名、期限、ロット番号など）を入力します。IDは自働的に生成されます。

### **2. 在庫の同期**
- 店舗ごとの更新ボタンを押すと、各店舗の在庫が共有シートに自動転記され、在庫状況が最新の状態になります。

### **3. 在庫移動処理**
- 他店舗に在庫を移動させる場合は、共有シートのH列に引き取り店舗を指定し、I列に引き取り可能数を入力します。
残数は自動計算されます。

### **4. 発送受け取り処理**
- 発送や受け取りが終了したら、K列（発送状況）とL列（受け取り状況）に手動で入力し、処理が完了したものには
M列に〇が表示されます。

### **5. 定期的な在庫の整理**
- 処理済みで残数が0のアイテムは、定期的に共有シートおよび店舗シートから削除されます。削除されたアイテムは
履歴シートに転記されます。

## **管理機能**

### **1. ID生成**
- 各店舗のシートのK1セルに最終の薬品IDが記録されており、新規追加されたアイテムに対して次のIDを自動生成します。

### **2. 共有シートの更新**
- 各店舗シートでの在庫情報を共有シートに転記し、IDの一致する行を更新します。新しいアイテムは共有シートに追加されます。

### **3. 不動在庫の削除**
- 共有シート上で処理済み（M列に〇）で残数が０の場合、共有シート及び店舗シートから自動削除されます。

## **注意点**
- 各シートの権限を適切に設定し、データの保護を行うことで不正な変更を防止します。
- 処理済みのアイテムは履歴シートに自動転記され、削除されても後で参照できるようになっています。

## **連絡先**
システムに関する質問や問題が発生した場合は〇〇までご連絡ください。
e-mail XXXXX@XX.jp