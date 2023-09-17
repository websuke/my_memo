# mysql dumpコマンド
```shell
sudo mysqldump -u root -p -B 対象のDB名 > 出力先のパス
```
【注意事項】
- 端末にてmysqlログイン前の状態で実行すること。
- 認証方式が「auth_socket」になっていると、mysql -u 実行時に指定されているユーザ名が、Ubuntuにログイン中のユーザ名と同じでなければいけないためsudoで実行すること。

### root以外のユーザーで「〜〜tablespaces」のエラーが発生する場合
```shell
sudo mysqldump --no-tablespaces -u ユーザー名 -p -B 対象のDB名 > 出力先のパス
```
【対応策については以下2つのどちらか】
- 上記のように「--no-tablespaces」をつける。
- もしくはユーザーにPROCESS権限を与える。


