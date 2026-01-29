# 20250817
Markdown記法/書き方（見出し・表・リンク・画像・文字色など）
https://help.notepm.jp/hc/ja/articles/17267176922393-Markdown%E8%A8%98%E6%B3%95-%E6%9B%B8%E3%81%8D%E6%96%B9-%E8%A6%8B%E5%87%BA%E3%81%97-%E8%A1%A8-%E3%83%AA%E3%83%B3%E3%82%AF-%E7%94%BB%E5%83%8F-%E6%96%87%E5%AD%97%E8%89%B2%E3%81%AA%E3%81%A9
README書く際のプレビュー確認方法
https://zenn.dev/kenkenlysh/articles/2e5c881074a791

# 20250908
卒業制作提出までのながれ
1.与えられた課題を作る
2.git branch,git status,git add .,git commit -m '',git push origin データ名までmacのターミナルで終わらせる
3.git hub上でプルリクだす（rspecカリキュラム参考）
4.コメント書いとく。書かんと見る人がわからない。

# 20250909
解答例を確認してPullRequestのマージ
最後に解答例を確認して、修正等なければGitHub上からPullRequestをマージします。

PullRequestのマージ
最後にブランチをdevelopにマージして完了です。
下記を参考にGitHub上でマージしてください。
作成したPullRequestの画面の下部にMerge pull requestボタンをクリックします、これでマージ完了です。

課題完了！次のchapterへ
GitHubのdevelopブランチに実装した内容が反映されているかと思います。
自分のローカルにもdevelopのコードをgit pullコマンドで反映させておきます。
次のchapterからもこのような流れで進めていきますので、PullRequestの作成に困ったらこちらの流れを見返すようにしてください。

**ターミナルでの操作**
git chckout develop
git pull origin develop

# 20260110
googleログイン（Render本番）

google console  
承認済みの JavaScript 生成元  
https://〇〇.onrender.com  
承認済みのリダイレクト URI  
https://〇〇.onrender.com/users/auth/google_oauth2/callback  
Render  
EnvironmentsにGOOGLE_CLIENT_IDとGOOGLE_CLIENT_SECRETを登録する

# 20260114
今更ですが、こまめにデプロイした方がよい

ブランチ切って初めてのとき
・git add
・git commit -m ''
・git push -u origin ブランチ名
・初めての時はリポジトリにPRが自動で作られ（develop）それをPR,merge
・デプロイ確認できる

2回目以降
・まだ修正してデプロイ確認したいとき
・ブランチはdevelopにかえない
・git add
・git commit -m ''
・git push
・自分でプルリク作る（develop←ブランチ名）自動で作れない？
・それをPR,merge
・デプロイ確認できる

しばらく修正ないなーと思った時
・ローカルブランチをdevelopに移動 git checkout develop
・git pull origin develop

# 20260129
1. ngrok を Mac にインストール（Docker外）
brew install ngrok/ngrok/ngrok
ngrok version
2. ngrok アカウント作成（無料）
https://dashboard.ngrok.com/signup
3. authtoken 登録
ngrok config add-authtoken xxxxxxxxxxxxx
4. Railsが localhost で開けること確認
http://localhost:3000
5. ngrok 起動（Mac側）
ngrok http 3000
Forwarding https://xxxx.ngrok-free.dev -> http://localhost:3000
6. Rails HostAuthorization 対策
config/environments/development.rb に追加：
config.hosts.clear
