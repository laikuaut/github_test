# github_test
githubになれるためのリポジトリ

## gitの基本コマンドメモ

### ローカルリポジトリ作成(初期化)

ローカルのgitリポジトリを作成します。

```Bash
mkdir github_test
cd github_test
git init
```

### リモートリポジトリの情報追加

ローカルリポジトリにリモートリポジトリの情報を追加する。

```Bash
git remote add origin https://github.com/laikuaut/github_test.git
```

### リモートブランチの変更を取得

リモートリポジトリからブランチの変更を反映する。

```Bash
git pull origin master
```

### ローカル作業

#### gitのインデックスを追加

```Bash
git add README.md
```
