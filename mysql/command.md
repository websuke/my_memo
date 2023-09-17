# mysql dumpコマンド
### 基本形
```shell
sudo mysqldump -u ユーザー名 -p -h ホスト名 --port ポート番号 -B 対象のDB名 > カレントから見た出力先のパス
```
### 最低限の基本形
```shell
sudo mysqldump -u ユーザー名 -p -B 対象のDB名 > カレントから見た出力先のパス
```

<br>

---

<br>

### rootユーザーでsampleDBからdump.sqlファイルをカレントに作成する場合
```shell
sudo mysqldump -u root -p -B sample > dump.sql
```
【注意事項】
- 端末にてmysqlログイン前の状態で実行すること。
- 認証方式が「auth_socket」になっていると、mysql -u 実行時に指定されているユーザ名が、Ubuntuにログイン中のユーザ名と同じでなければいけないためsudoで実行すること。

<br>

### 上記をroot以外のユーザーで実施し「〜〜tablespaces」のエラーが発生する場合
```shell
sudo mysqldump --no-tablespaces -u root以外のユーザー名 -p -B sample > dump.sql
```
【対応策については以下2つのどちらか】
- 上記のように「--no-tablespaces」をつける。
- もしくはユーザーにPROCESS権限を与える。

<br>

---

<br>

# dumpファイル　インポートコマンド
### 基本形
```shell
sudo mysql -u ユーザー名 -p -h ホスト名 --port ポート番号 DB名 < インポートするファイルのパス
```

### rootユーザーでlocalのポート番号3306のsampleDBにdump.sqlをインポートする場合
```shell
sudo mysql -u root -p -h localhost --port 3306 sample < dump.sql
```
