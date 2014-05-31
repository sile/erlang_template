erlang_template
===============

Erlangで[rebar](https://github.com/basho/rebar)を使ったアプリケーションを作成する際のテンプレート。

アプリケーション作成手順
------------------------

以下のシェルを実行する:

```bash
git clone git@github.com:sile/erlang_template.git {アプリケーション名}

# 一行目の'APP=hoge'を適切なアプリケーション名に置き換える
vim Makefile

# 依存ライブラリ等があるなら追記する
vim rebar.config

# gitのremoteを適切なものに更新する
rm -rf .git
git init
git remote add ...
git add .
git commit -m'first commit'
git push origin master

# 開発サイクルを回す
make init               # 依存ライブラリの取得コンパイル
vim src/...             # ソース修正
make compile            # コンパイル
make xref eunit dialyze # ユニットテスト等

make start              # Erlangシェル起動
```
