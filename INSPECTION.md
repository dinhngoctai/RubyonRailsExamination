# チャレンジ点検表

## 全チャレンジ共通項目

#### READMEの設定
- [ ] [Skeleton-challenge-cli](https://github.com/code-check/skeleton-challenge-cli/blob/master/README.md)もしくはクライアント指定のひな形に準じた形式になっている
- [ ] 課題となるプログラムの意図が明確である
- [ ] 遊び心のある表記になっている
- [ ] 行数が100行以内である。目標値は70行。
- [ ] 誤字脱字がない
- [ ] 文末、文体が統一されている
- [ ] サンプルが示されている
  - [ ] サンプルで十分に期待している動作を表現できていること
  - [ ] サンプルの表記に誤りがないこと
- [ ] 引数の不正に対する記述がある
- [ ] 言語に関する記載が無い（examの仕様上、記載されていないべき）

#### challenge.jsonの設定
- [ ] challenge.json が設置されている
- [ ] 言語設定が適切である
  - プリセットCLIは [環境ページ](https://app.code-check.io/guide/environments)の内容に準拠すること
  - クライアントチャレンジの場合、クライアント指定の言語になっていること
- [ ] editable の設定が適切である
  - [ ] 以下が`editable`として設定されている(テンプレートとして組み込まれているファイル)
    - .gitignore
    - package.json
    - codecheck.yml
    - answer.md
- [ ] excludes の設定が適切である
  - [ ] challenge.json がexcludeされている
  - [ ] 秘匿すべきテストがexcludeされている
- [ ] ignores の設定が適切である
  - [ ] サンプル解答コードが除外されている
  - [ ] サンプル解答コードが一般的に使われているディレクトリ(`/app`など)以外で作られている
    - 指定されたディレクトリ名でプログラムを実装した時の挙動が保証できないため
    - [ ] `INSPECTION.md`,`eslint`設定ファイル及び `.github/`が除外されている
- [ ] testの設定が適切である(普段は`mocha`)

#### codecheck.ymlの設定
- [ ] codecheck.yml が設置されている
  - ローカル受験では challenge.json の内容が見られないため、codecheck.yml ファイルが必要になる
- [ ] testの設定が適切である(普段は`mocha`)
- [ ] codecheck.yml と challenge.json の "test" セクションが一致している
- [ ] "env" セクションと、その中で "APP_COMMAND" のセクションに記載がある


#### answer.mdの設定
- [ ] answer.md が設置されている
- [ ] answer.md にチャレンジ特有の要求されている解答説明等に関する記述がある
- [ ] answer.md に不要な記述が含まれていない

#### package.jsonの設定
- [ ] package.json が設置されている
- [ ] package.json に不要なモジュールが含まれていない
- [ ] `"scripts": ( "test": "mocha" )`は不要。除外されているか？

#### テストケースの設定
- [ ] テストケースが実装されている
- [ ] 秘密のテストケースが実装されている
- [ ] 解答コード不在時に、全てのテストケースが`fail`する
- [ ] 解答コード不在時に、テストケースの母数が変化しない
- [ ] 解答コードで全てのテストケースが`pass`する
- [ ] `app.run`ではなく`app.codecheck`を利用している
- [ ] 「良い」テストスイートの定義(RISES)を満たしている
  - [ ] Readable (可読性は高い）
  - [ ] Independent 各テストは他テストや不要なモジュールに依存していない。他テストと重複していない。
  - [ ] Small 小さいか？各テストは検証できる最小単位の機能を検証している
  - [ ] Exhaustive テスト群は全機能を網羅している
  - [ ] Speedy 実行速度が早い。検証サイクルは小さい方が楽しい。

#### Githubの設定
- [ ] `master`をprotected branchとして設定できている

#### 機能点検
- [ ] code-develop でチャレンジとしてインポートできる
- [ ] editable であるべきファイルが編集できる
- [ ] excludes かignore と設定されるべきファイルが表示されていない
- [ ] 実装した場合、webeditorで全てのユニットテストがパスする
- [ ] 実装した場合、local受験で全てのユニットテストがパスする
- [ ] すべての言語で初期状態(ユーザーが１行もコードを書いていない状態)でテスト実行可能である

#### ユーザー受け入れ点検
- [ ] 第三者に作成した問題を解いてもらった
- [ ] 実装が容易なfirst step（はじめの一歩）が設けてある
- [ ] 回答時間が1-3時間だった