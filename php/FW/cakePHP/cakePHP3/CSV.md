# CSV

### download

[本ライブラリ](https://github.com/FriendsOfCake/cakephp-csvview)がおすすめ

実装のサンプルについては以下
```xxController.php
public function download()
    {
        // CSVデータの作成
        $_body = $this->LoginHistorys->find()->all();

        $_serialize = '_body';
        $_header = ['id', 'user_id', 'login_time', 'logout_time', 'created', 'modified', 'created_user', 'modified_user'];
        $_footer = ['これはフッターです'];
        $_csvEncoding = 'UTF-8';
        $_newline = PHP_EOL;
        $_eol = PHP_EOL;

        // ダウンロードするCSVファイルのファイル名及び形式を設定
        $this->response = $this->response
        ->withType('csv')
        ->withDownload('login_history.csv');

        // オプションをセットしてviewBuilderにCsvView.Csvを設定
        $this->viewBuilder()->setClassName('CsvView.Csv');
        $this->set(compact('_body', '_serialize', '_header', '_footer', '_csvEncoding', '_newline', '_eol'));
    }
```
