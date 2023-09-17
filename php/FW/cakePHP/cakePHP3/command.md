# Migration
### 既存DBからmigrationファイルを作成
```shell
./bin/cake bake migration_snapshot initial
```

### migrationファイルとDBの差分を抽出しmigrationファイルを作成
```shell
./bin/cake bake migration_diff add_追加したカラム名_column_for_カラムを追加したテーブル名
```

### migrationファイルの実行状況を確認
```shell
./bin/cake migrations status
```
※上記はphinxlogテーブルを見て判断した結果を返している。

### migrationの適用取り消し(1つ前)
```shell
./bin/cake migrations rollback
```

### migrationの適用取り消し(指定したマイグレーションIDの次まで)
```shell
./bin/cake migrations rollback -t マイグレーションID
```
