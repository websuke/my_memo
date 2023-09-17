# mysql dumpコマンド
```shell
sudo mysqldump -u root -p -B 対象のDB名 > 出力先のパス
```
【注意事項】
- 端末にてmysqlログイン前の状態で実行すること。
- 認証方式が「auth_socket」になっていると、mysql -u 実行時に指定されているユーザ名が、Ubuntuにログイン中のユーザ名と同じでなければいけないためsudoで実行すること。
