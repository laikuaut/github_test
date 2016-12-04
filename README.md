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
git remote -v
# origin  git@github.com:laikuaut/github_test.git (fetch)
# origin  git@github.com:laikuaut/github_test.git (push)
```

鍵作成

```Bash
mkdir .ssh
cd ~/.ssh/
ssh-keygen -t rsa
# id_rsa_git.pubの中身をgithubのSSH keysに登録
eval `ssh-agent`
ssh-add ~/.ssh/id_rsa_git
# 接続確認
ssh -T git@github.com
```

#### ユーザ名を設定

メールアドレスがgithubのと一致していないと、
Your Contributionsに反映されないっぽい

なので、ユーザ名(一応)とメールアドレスを登録しておく

```Bash
git config --global user.name 'laikuaut'
git config --global user.email 'メールアドレス'
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

### ブランチを使う

基本手順

```Bash
git branch -a
git checkout -b branch_name
# 作業・・・
git commit -m "fix #(issuesID)" #issueと関連したコメント(pull requestでmergeされた場合、クローズされる)
# 参考 : https://help.github.com/articles/closing-issues-via-commit-messages/
# ・・・・・
git push origin branch_name
git remote show origin
git fetch --prune
git checkout master
git pull origin master
git branch -d branch_name
```

#### ブランチ確認

全てのブランチを確認

```Bash
git branch -a
```

#### ブランチ作成とチェックアウト

ブランチを作成して、チェックアウトする

```Bash
git checkout -b branch_name
```

#### ブランチをプッシュ

ブランチをリモートへプッシュする

```Bash
git push origin branch_name
```

#### リモートブランチの状態確認

リモートブランチの状態を確認。
ブランチの更新や削除等が確認できる。

```Bash
git remote show origin
```

#### リモートで削除済みのブランチを反映

```Bash
git fetch --prune
```

#### ローカルブランチ削除

```Bash
git branch -d branch_name
```
