# Validation

### ベターな実装方法

- default providerにlocalizedを設定

[Localized_github](https://github.com/cakephp/localized)
<br>
[coockBook](https://book.cakephp.org/3/ja/core-libraries/validation.html#adding-validation-providers)

- xxTable.php内の1箇所でしか使用しないバリデーションはクロージャーを定義

- xxTable.php内で複数回使用するバリデーションはコールバック関数を定義
