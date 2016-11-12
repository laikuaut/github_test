# github_test

githubになれるためのリポジトリ

## gitの基本コマンドメモ

gitコマンドの基本メモ

### githubで作成したリポジトリの取得

githubで作成したリポジトリをローカルで扱うためのメモ

#### ローカルリポジトリ作成(初期化)

ローカルのgitリポジトリを作成します。

```Bash
mkdir github_test
cd github_test
git init
```

#### リモートリポジトリの情報追加

ローカルリポジトリにリモートリポジトリの情報を追加する。

```Bash
git remote add origin https://github.com/laikuaut/github_test.git
```

#### sshプロトコルに変更

```Bash
git remote set-url origin git@github.com:laikuaut/github_test.git
```

#### リモートブランチの変更を取得

リモートリポジトリからブランチの変更を反映する。

```Bash
git pull origin master
```

#### 追加されているか確認

リポジトリの状態を取得

```Bash
git status
```

#### gitのインデックスを追加

ローカルリポジトリをインデックスへ追加

```Bash
git add README.md
```

#### コミット

ローカルリポジトリをコミットする。

```Bash
git commit -m "コメント"
```

#### ローカルリポジトリをリモートリポジトリへプッシュする

リモートリポジトリへpushする。

```Bash
git push origin master
```



