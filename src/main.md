<!-- $theme: gaia -->
<!-- custom style start -->
<style type="text/css">
  .right { float: right; }
  .cert-logo { width: 17%; height: 17%; }
  .img-practice { width: 80%; height: 80%; margin-left: auto; margin-right: auto; display: block; }
  .img-practice-small { width: 60%; height: 60%; margin-left: auto; margin-right: auto; display: block; }
  .img-practice-40 { width: 40%; height: 40%; margin-left: auto; margin-right: auto; display: block; }
  .img-practice-30 { width: 30%; height: 30%; margin-left: auto; margin-right: auto; display: block; }
  .img-jaws-logo { width: 15%; height: 15%; margin-left: auto; margin-right: auto; display: block; }
  .img-mfa { width: 20%; height: 20%; vertical-align: top; }
  .text-standard { font-size: 24px; }
  .top { vertical-align: top; display: inline-block; }
  .margin-top { margin-top: 60px; }
  .title-highlight { text-decoration: underline; color: orange; }
  ul { font-size: 24px; }
  p { font-size: 24px; }
  a { font-size: 16px; }
  tr { font-size: 20px; }
  td { font-size: 20px; }
</style>
<!-- custom style end -->

<!-- *template: gaia -->

不安で夜眠れない
AWSアカウント管理者に送る
処方箋という名のハンズオン
===

---

<!-- page_number: true -->

# Profile

<div class="right">
  <img src="./images/00_profile_02.png" width="80%" height="80%" class="right" />
</div>

#### 角山 恵介 (Keisuke Kadoyama)

* SI歴 10年
  * エンタープライズ 4年
  * WEB 6年
  * 今年からまたエンタープライズへ
* AWS歴 6年
  * ソリューションアーキテクト
  * Cloud Migration / DevOps / Trouble Shooting

<div align="center" class="margin-top">
  <img src="./images/aws_sa_a.png" class="cert-logo">
  <img src="./images/aws_dev.png" class="cert-logo">
  <img src="./images/aws_sysop.png" class="cert-logo">
  <img src="./images/aws_sa_p.png" class="cert-logo">
  <img src="./images/aws_devops.png" class="cert-logo">
</div>

---

## Questions ?

* とりあえずAWSアカウントを取得したが、そのまま使いはじめて
  大丈夫なの？
* 最初のシステムが本番稼働しはじめたけど、このまま次々システムを
  動かして問題はないの？
* なしくずし的にAWSアカウントが増えていってるがこのままで大丈夫？
* AWSアカウントの管理をしているけど不安で夜も眠れないんだけど？

<!-- note
* ログインさえしてしまえば何でもできてしまう、、、まずいと思うけどどうすればいいのかわからない
* 管理コンソールや適切に管理されてないAPIキーが漏洩するとなんでも出来てしまう。
* AWSに限った話ではないので、他のサービスでも同じようなことをどうやって担保しているのかハンズオンを通して学んでもらう。
-->

---

## Overview

* AWSアカウントを取得して、==最初にやっておくべき初期設定==を
  ハンズオン形式で学んでもらう :hammer:
* 設定しない場合のリスクを理解してもらう
* セキュリティだけではなく設定しておくと便利なTipsも
* :warning: 今日のハンズオンは==1コイン程度の料金==が発生します :warning:

## Infomation

* 会場のWiFi :zap:

SSID|GOTANDA-MESSE
:--|:--
Password|1234123412341

* 本資料のURL <a href="http://bit.ly/jaws2017h1" class="text-standard">http://bit.ly/jaws2017h1</a>
* JAWS DAYS全体のハッシュタグ ==#jawsdays #jawsug==
* ワークショップトラックのハッシュタグ ==#jd2017_workshop==

<!-- note
このセッションではこちらに上げたような事柄をハンズオンを通して学んで頂きます。
またこちらの会場のwifiはスライドに記載しておりますSSIDとパスワードで接続できます。
本セッションのスライドもこちらのURLからダウンロードできます。
-->

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

<!-- note
本セッションの具体的な章立てはこのようになっています
多分AWSをそこそこお使いの方であれば、おなじみの内容もあるかなと思います
-->

---

## AWSアカウント取得 :beginner:

アカウント周りのハンズオンなので、
すでに本番システムを動作させているAWSアカウントや、
管理者権限を持っていない場合は、新規AWSアカウント取得を推奨

#### 必要なもの

* アカウント作成用のメールアドレスとパスワード
* 認証用のPINコードを受け取るための電話番号
* クレジットカード

#### 手順はこちらを参照

<a href="https://aws.amazon.com/jp/register-flow/" class="text-standard">https://aws.amazon.com/jp/register-flow/</a>

<!-- page_number: true -->

<!-- note
それではまず最初のハンズオンに移って行きたいと思いますが、
その前にAWSアカウントを持っていないという方、どれくらいいらっしゃるでしょうか。
AWSアカウントは同じシステムでも本番／ステージングなど環境毎にアカウントを分けることを推奨。
-->

---

<!-- *template: invert -->

<div align="left">

#### <span class="title-highlight">1. ルートアカウントの保護</span>

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

---

## 1. ルートアカウントの保護

#### Why / Risk

* AWSのすべての操作が可能な==管理者権限==を持つアカウントのため、
権限の制限ができない
* ルートアカウントの情報が漏洩して乗っ取られると何でもされてしまう
意図しない課金、既存システムの削除、システムが持つデータや情報の漏洩 :scream:

#### Answer

* パスワードを複雑にする
* MFA (他要素認証) の有効化
* APIキーの削除
  * 不要なAPIキーを悪用されると、ログインしなくてもAWSを
    ==管理者権限==で操作できてしまう
* 普段の操作にはルートアカウントを==使用しない==

<!-- note
Admin権限＝Root権限
一部のサポートへの申請にはAWSアカウントが必要なケースがあるので情報はなくさないように。
ペネトレーションテストやE-mail制限緩和の申請など。
-->

<!-- page_number: true -->

---

## 1. ルートアカウントの保護

以下のURLアクセスして右上の [サインアップ] をクリック
https://aws.amazon.com/jp/

<img src="./images/01_aws_account_01.png" class="img-practice">

---

## 1. ルートアカウントの保護

①メールアドレス
②パスワードを入力して
③[Sign in using our secure server] をクリック

<img src="./images/01_aws_account_02.png" class="img-practice">

---

## 1. ルートアカウントの保護

AWSサービスの下に表示されているテキストボックスに [IAM] と入力し、表示されたIAMサービスをクリック

<img src="./images/01_aws_account_03.png" class="img-practice">

---

## 1. ルートアカウントの保護

IAM = Identity and Access Management (無料)
「どのユーザがどのAWSリソースへアクセスできるか」を制御する仕組み
AWSのセキュリティの要

<img src="./images/01_aws_account_04.png" class="img-practice">

---

## 1. ルートアカウントの保護

一番上の [ルートアクセスキーの削除] でルートアカウントのAPIキーを削除

<img src="./images/01_aws_account_04b.png" class="img-practice-small">

削除する場合は事前にシステム等で利用していないかよく確認

<img src="./images/01_aws_account_04c.png" class="img-practice-small">

<!-- note
今日アカウントを取得された方は緑になっていると思いますが、
一番上のルートアクセスキーの削除というのがルートアカウントのAPIキーの削除になります
先程申し上げたとおりAdmin権限を持っているルートアカウントのAPIキーを利用するのは
セキュリティの観点から非常に危険なので、もしここが警告マークになっている方は削除をおすすめします
ただ、すでに運用中のAWSアカウントだと何かシステムで利用している可能性もあるので、使用していないかよく確認して削除してください
-->

---

## 1. ルートアカウントの保護

[ルートアカウントのMFAを有効化] をクリックし、
[MFAの管理] をクリック

<img src="./images/01_aws_account_05.png" class="img-practice">

<!-- note
今日アカウントを取得された方は緑になっていると思いますが、
一番上のルートアクセスキーの削除というのがルートアカウントのAPIキーの削除になります。
先程申し上げたとおりAdmin権限を持っているルートアカウントのAPIキーを利用するのは
セキュリティの観点から非常に危険なので、もしここが警告マークになっている方は削除をおすすめします。
-->

---

## 1. ルートアカウントの保護

#### MFAとは？

MFA = Multi Factor Authentication
要はパスワード＋αによる2段階認証 (6桁の認証コード)

##### 仮想MFAデバイス

* Android / iOSアプリ: Authenticator / Authy
* Chrome Extension: <a href="https://chrome.google.com/webstore/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai" class="text-standard">Authenticator</a>
* Firefox Extension: <a href="https://addons.mozilla.org/ja/firefox/addon/open-two-factor-authenticator/" class="text-standard">Open Two-Factor Authenticator</a>

##### ハードウェアMFAデバイス

<img src="./images/01_aws_account_06a.png" class="top">
<img src="./images/01_aws_account_06b.png" class="top">
<img src="./images/01_aws_account_06c.png" class="top">

---

## 1. ルートアカウントの保護

#### 仮想MFAデバイスをお持ちでない方

Android / iOSスマートフォンをお持ちの方はアプリのストアより「Authy」と検索してアプリをダウンロード
起動してSMSで電話番号の認証をすませる

<div align="center">
<img src="./images/01_aws_account_15a.png" class="img-mfa">
<img src="./images/01_aws_account_15b.png" class="img-mfa">
<img src="./images/01_aws_account_15c.png" class="img-mfa">
<img src="./images/01_aws_account_15d.png" class="img-mfa">
</div>

---

## 1. ルートアカウントの保護

[仮想MFAデバイス] を選択する

<img src="./images/01_aws_account_07.png" class="img-practice">

---

## 1. ルートアカウントの保護

QRコードが表示されるので、仮想MFAデバイスのアプリからスキャンする

<img src="./images/01_aws_account_08.png" class="img-practice-30">

Authyをお使いの方は [+] ボタンから [Scan QR Code] をタップして
表示されているQRコードをスキャン

<div align="center">
<img src="./images/01_aws_account_15e.png" class="img-mfa">
<img src="./images/01_aws_account_15f.png" class="img-mfa">
<img src="./images/01_aws_account_15g.png" class="img-mfa">
</div>

---

## 1. ルートアカウントの保護

仮想MFAデバイスに表示される認証コードを2つ入力して有効化
※2つの認証コードは異なるコードであること

<img src="./images/01_aws_account_09.png" class="img-practice-30">

Authyをお使いの方は以下の画面に表示される6桁の認証コードを入力

<div align="center">
<img src="./images/01_aws_account_15h.png" class="img-mfa">
</div>

---

## 1. ルートアカウントの保護

無事ルートアカウントのMFAが有効になりました

<img src="./images/01_aws_account_11.png" class="img-practice">

---

## 1. ルートアカウントの保護

確認のため一度サインアウトし、

<img src="./images/01_aws_account_12.png" class="img-practice">

もう一度サインイン

<img src="./images/01_aws_account_13.png" class="img-practice">

---

## 1. ルートアカウントの保護

メールアドレス、パスワードを入力後、登録した仮想MFAデバイスの認証コードが求められる

<img src="./images/01_aws_account_14.png" class="img-practice-small">

Authyをお使いの方は以下の画面に表示される6桁の認証コードを入力

<div align="center">
<img src="./images/01_aws_account_15h.png" class="img-mfa">
</div>

---

## 1. ルートアカウントの保護

#### Why / Risk

* AWSのすべての操作が可能な==管理者権限==を持つアカウントのため、
権限の制限ができない
* ルートアカウントの情報が漏洩して乗っ取られると何でもされてしまう
意図しない課金、既存システムの削除、システムが持つデータや情報の漏洩 :scream:

#### Answer

* パスワードを複雑にする
* MFA (他要素認証) の有効化
* APIキーの削除
  * 不要なAPIキーを悪用されると、ログインしなくてもAWSを
    ==管理者権限==で操作できてしまう
* 普段の操作にはルートアカウントを==使用しない==

<!-- note
Admin権限＝Root権限
一部のサポートへの申請にはAWSアカウントが必要なケースがあるので情報はなくさないように。
ペネトレーションテストやE-mail制限緩和の申請など。
-->

<!-- page_number: true -->

---

## Break

* 不要なAPIキーの作成や、不適切な権限が付与されているかだけでなく、誤って==APIキーがグローバルに公開されていないか==チェック
  * Amazonが公開しているgit-secretsというツールで、プログラムの
    gitリポジトリにAPIキーをcommitしていないかチェック
<a href="https://github.com/awslabs/git-secrets" class="text-standard">https://github.com/awslabs/git-secrets</a>
  * もしグローバル公開したり漏洩の危険性がある場合、Amazonから
    警告メールが来ることも
    ※AWSアカウントへのアクセスが強制停止されることもあります

<img src="./images/01_aws_account_16.png" class="img-practice-40">

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### <span class="title-highlight">2. IAMユーザーとパスワードポリシー</span>

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

---

## 2. IAMユーザとパスワードポリシー

#### Why / Risk

* 管理者権限を持ったルートアカウントの代わりに他のアカウントが必要
* 漏洩時や操作ミスを考慮してアカウントには適切な権限管理を行いたい
* ==アカウントを共有==していると誰が何をしたかの証跡が追いづらい

#### Answer

* IAMユーザーと、権限を定義したIAMポリシーを作成
  * IAMユーザーは==共有せず==に利用者単位で作成
  * 権限はIAMユーザーではなくIAMグループに設定して
    IAMユーザーの権限管理を楽にする
* IAMユーザーでもMFAを有効化
* パスワードポリシーを設定して簡単なパスワードを設定できないように

<!-- page_number: true -->

---

## 2. IAMユーザとパスワードポリシー


IAMの画面を表示し、末尾の [IAMパスワードポリシーの適用] から [パスワードポリシーの管理] をクリック

<img src="./images/02_iam_password_01.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

パスワードポリシーを設定して [パスワードポリシーの適用] をクリック

<img src="./images/02_iam_password_02.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

左メニューから [ユーザー] をクリック

<img src="./images/02_iam_password_03.png" class="img-practice">

[ユーザーを追加] をクリック

<img src="./images/02_iam_password_04.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

<img src="./images/02_iam_password_05.png" class="img-practice">

<!-- note
AWSアクセスの種類で、「プログラムによるアクセス」と「AWSマネジメントコンソールへのアクセス」の2種類があると思いますが、
前者はAPIでのアクセス、後者は今やっているブラウザでのAWSマネジメントコンソールへのログインが可能な権限になります。
両方つけることも可能ですが、今回はログインだけ出来ればいいので「AWSマネジメントコンソールへのアクセス」にチェックを入れて下さい。
-->

---

## 2. IAMユーザとパスワードポリシー

IAMグループを使って権限制御を行うため [グループの作成] をクリック

<img src="./images/02_iam_password_06.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

グループ名を入力し、 [AdministratorAccess] ポリシーを選択して作成する

<img src="./images/02_iam_password_07.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

作成したIAMグループにチェックが入っていることを確認し、次へ

<img src="./images/02_iam_password_08.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

内容を確認し、 [ユーザーの作成] をクリック

<img src="./images/02_iam_password_09.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

①サインイン用のURL、②パスワードをメモするか、
③Eメールでログイン情報を送信する

<img src="./images/02_iam_password_10.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

#### IAMユーザーもMFAを有効にする

左メニューの [ユーザー] から作成したIAMユーザーの名前をクリック

<img src="./images/02_iam_password_13.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

① [認証情報] タブを選択し、
② [MFAデバイスの割り当て] をクリック

<img src="./images/02_iam_password_14.png" class="img-practice">

先ほどのルートアカウントの手順と同様の手順で、
仮想MFAデバイスを有効にする

<!-- note
※IAMユーザー本人にMFAを設定してもらう場合はこちらの記事を参考に
![IAMユーザ本人にMFAを管理してもらうためのIAMポリシー](http://dev.classmethod.jp/cloud/aws/iam-mfa-policy/)
-->

---

## 2. IAMユーザとパスワードポリシー

ここまでできたらルートアカウントの使用をやめるためサインアウトし、

<img src="./images/01_aws_account_12.png" class="img-practice-small">

IAMユーザーのサインイン用URLにアクセスする
https://xxxxxxxxxxxx.signin.aws.amazon.com

<img src="./images/02_iam_password_11.png" class="img-practice-40">

---

## 2. IAMユーザとパスワードポリシー

パスワードを入力するとMFAコードを求められ、

<img src="./images/02_iam_password_15.png" class="img-practice-30">

サインインに成功すると強制的に新しいパスワードの設定を求められる

<img src="./images/02_iam_password_12.png" class="img-practice-30">

---

## 2. IAMユーザとパスワードポリシー

ここまで出来たらセキュリティステータスを確認
https://console.aws.amazon.com/iam/home

<img src="./images/02_iam_password_16.png" class="img-practice">

---

## 2. IAMユーザとパスワードポリシー

#### Why / Risk

* 管理者権限を持ったルートアカウントの代わりに他のアカウントが必要
* 漏洩時や操作ミスを考慮してアカウントには適切な権限管理を行いたい
* ==アカウントを共有==していると誰が何をしたかの証跡が追いづらい

#### Answer

* IAMユーザーと、権限を定義したIAMポリシーを作成
  * IAMユーザーは==共有せず==に利用者単位で作成
  * 権限はIAMユーザーではなくIAMグループに設定して
    IAMユーザーの権限管理を楽にする
* IAMユーザーでもMFAを有効化
* パスワードポリシーを設定して簡単なパスワードを設定できないように

<!-- page_number: true -->

---

## Break

* IAMユーザーのサインイン用URL (アカウント番号) は任意の文字列に変更することが可能
  https://xxxxxxxxxxxx.signin.aws.amazon.com :arrow_right: https://jawsdays.signin.aws.amazon.com
  
<img src="./images/02_iam_password_17.png" class="img-practice-small">

* IAMユーザーの利用者本人にMFAを設定してもらうには、こちらの公式
  チュートリアルを参考にIAMポリシーを設定する
  http://docs.aws.amazon.com/ja_jp/IAM/latest/UserGuide/tutorial_users-self-manage-mfa-and-creds.html

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### <span class="title-highlight">3. 証跡ログの設定</span>

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

---

## 3. 証跡ログの設定

#### Why / Risk

* ==どの操作==を==誰が==行ったのかわからない
* 悪意のある内部犯行があった場合に犯人がわからない :smiling_imp:
* 高額なリソースをこっそり使われても==誰が==利用したのかわからない :money_with_wings:

#### Answer

* ==CloudTrail==の有効化
  * 管理コンソールやAPIによる操作を証跡ログとして記録する
  * CloudTrailは最初の1つだけなら無料
    * ログを保存するS3のストレージ料金が別途発生
* 利用していないリージョンでも不正利用を記録できるように有効に
* 制限ではなく、あくまで==抑止力== :warning:

<!-- page_number: true -->

<!-- note
* 未対応のサービスがある
* ログ自体を改竄されると意味がないので注意
-->

---

## 3. 証跡ログの設定

左上の [サービス] から [CloudTrail] をクリック

<img src="./images/03_cloudtrail_01.png" class="img-practice">

---

## 3. 証跡ログの設定

右上のリージョン選択で [東京] リージョンを選択
[今すぐ始める] をクリック

<img src="./images/03_cloudtrail_02.png" class="img-practice">

---

## 3. 証跡ログの設定

①証跡名は好きな名前を、
②認証情報は全てのリージョンに適用する、
③④証跡ログを保存するS3バケットは新規で作成

<img src="./images/03_cloudtrail_03.png" class="img-practice-small">

---

## 3. 証跡ログの設定

設定完了

<img src="./images/03_cloudtrail_04.png" class="img-practice-small">

S3に出力されたログ

<img src="./images/03_cloudtrail_05.png" class="img-practice-small">

---

## 3. 証跡ログの設定

CloudTrailの証跡ログが出力されているS3バケット

<img src="./images/03_cloudtrail_06.png" class="img-practice-small">

JSON形式で圧縮して保存されている

<img src="./images/03_cloudtrail_07.png" class="img-practice-small">

---

## 3. 証跡ログの設定

#### Why / Risk

* ==どの操作==を==誰が==行ったのかわからない
* 悪意のある内部犯行があった場合に犯人がわからない :smiling_imp:
* 高額なリソースをこっそり使われても==誰が==利用したのかわからない :money_with_wings:

#### Answer

* ==CloudTrail==の有効化
  * 管理コンソールやAPIによる操作を証跡ログとして記録する
  * CloudTrailは最初の1つだけなら無料
    * ログを保存するS3のストレージ料金が別途発生
* 利用していないリージョンでも不正利用を記録できるように有効に
* 制限ではなく、あくまで==抑止力== :warning:

<!-- page_number: true -->

<!-- note
* 未対応のサービスがある
* ログ自体を改竄されると意味がないので注意
-->

---

## Break

* ==CloudWatch Logs==や==SNS==などAWSの他サービスと連携させることで、
  ただログを記録するだけでなく、「特定のリソースが削除された」、「ルートアカウントでログインが発生した」など==特定のイベントを元にメール通知==などが可能
* 証跡ログはJSON形式で保存され、他のログ可視化サービスと連携することでもっと見やすく管理することが可能
  * Splunk
  * Graylog
  * CloudCheckr
  * DataDog
  * etc...
    https://aws.amazon.com/jp/cloudtrail/partners/

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### <span class="title-highlight">4. 構成管理の設定</span>

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

---

## 4. 構成管理の設定

#### Why / Risk

* いつ誰が何をしたか、はCloudTrailの証跡ログから追えるが、
  そのときAWSのリソースが==どういう状態==だったかわからない
  * 一応証跡ログを順番に追っていけば再現できなくはない…:innocent:
* 昨年の年末セール対応ってサーバ何台用意してましたっけ？
  * ドキュメントには20台ってあるけど、当日増やした気が…

#### Answer

* ==AWS Config==の有効化
  * AWSリソースの状態や、各リソースのRelationship (関係) を記録
  * イベントの前後でAWSのリソースが==どう変化したか==記録
  * ルールを定義してルールに沿った設定がされているか自動チェック
  * すべてのAWSサービスの状態を記録してくれるわけではない :warning:

<!-- page_number: true -->

---

## 4. 構成管理の設定

左上の [サービス] から [Config] をクリック

<img src="./images/04_config_01.png" class="img-practice-small">

[Get started] をクリック

<img src="./images/04_config_02.png" class="img-practice-40">

---

## 4. 構成管理の設定

①[Include global resource] にチェック
②構成管理ログを保存するS3バケットは新規で作成

<img src="./images/04_config_03.png" class="img-practice">

<!-- note
まず一番上、どのリソースを記録するかですが、
ここではIAMなどリージョンに属さない、グローバルなAWSリソースもすべて記録対象にします
AWS Config有効にするのであればIAMの変更記録はすなわちアカウントの変更記録なので取っておいたほうがよいですよ
-->

---

## 4. 構成管理の設定

③SNS Topicを設定することで構成に変化があった際に通知できる
④Config roleはAWS Configが利用するIAMロール (権限) の設定
いずれもデフォルト値のまま [Next]

<img src="./images/04_config_04.png" class="img-practice">

---

## 4. 構成管理の設定

AWS Configは構成管理の記録だけでなく、特定のルールに沿った設定が
行われているかチェックが可能
今回はとくにチェックを入れず [Next]

<img src="./images/04_config_05a.png" class="img-practice-40">

自分たちの運用ルールに沿ったルールを設定 (カスタムルールの作成も可能)
* EBSは必ず暗号化する
* S3は必ずバージョニングを有効にする
* ルートアカウントは必ずMFAを有効にする
* RDSのバックアップを有効にする

---

## 4. 構成管理の設定

内容を確認して [Confirm]

<img src="./images/04_config_06.png" class="img-practice">

---

## 4. 構成管理の設定

左メニューの [Resources] をクリックして [Status] をクリック

<img src="./images/04_config_09.png" class="img-practice-small">

[Configuration Stream] がSuccessfullyになっていればOK
あとは勝手にリソース情報を収集して記録していく

<img src="./images/04_config_10.png" class="img-practice-small">

<!-- note
上半分にはAWS Configが構成情報を記録した時間が入っています
今設定したので多分みなさんはNot availableになってると思いますが、
このあと勝手に記録されていきます
Configuration SnapshotはConfiguration Itemの集合体で定期的もしくはリソースの変更をトリガーに記録されてS3に保存される
Configuration Historyは6時間おきにS3に配置されるConfiguration Itemをまとめた設定履歴
あとは定期的な取得とは別に、リソースの作成／削除といったイベントが発生しても記録されます
-->

---

## 4. 構成管理の設定

[Resources] で表示したいAWSリソースを選択して [Look up]

<img src="./images/04_config_11.png" class="img-practice-small">

該当するAWSリソースが一覧に表示される

<img src="./images/04_config_11a.png" class="img-practice-small">

---

## 4. 構成管理の設定

イベント発生時刻や内容、前後でリソースの状態がどうなったかが記録

* EC2の作成イベント

<img src="./images/04_config_12a.png" class="img-practice-40">
<img src="./images/04_config_12b.png" class="img-practice-40">

* SecurityGroupの変更

<img src="./images/04_config_13a.png" class="img-practice-40">
<img src="./images/04_config_13b.png" class="img-practice-40">

<!-- note
参考までにどんな感じで表示されるかというと、こんな感じです
画面はEC2インスタンスの作成イベントですが、削除なども同じように表示されます
-->

---

## 4. 構成管理の設定

#### Why / Risk

* いつ誰が何をしたか、はCloudTrailの証跡ログから追えるが、
  そのときAWSのリソースが==どういう状態==だったかわからない
  * 一応証跡ログを順番に追っていけば再現できなくはない…:innocent:
* 昨年の年末セール対応ってサーバ何台用意してましたっけ？
  * ドキュメントには20台ってあるけど、当日増やした気が…

#### Answer

* ==AWS Config==の有効化
  * AWSリソースの状態や、各リソースのRelationship (関係) を記録
  * イベントの前後でAWSのリソースが==どう変化したか==記録
  * ルールを定義してルールに沿った設定がされているか自動チェック
  * すべてのAWSサービスの状態を記録してくれるわけではない :warning:

<!-- page_number: true -->

---

## Break

* CloudTrailやAWS Configのログは延々と溜まり続ける
  * S3バケットのログは==Lifecycle機能==で一定期間過ぎたら自動削除
  * CloudWatch Logsのログは==保持期間の設定==で自動削除
* AWS ConfigもCloudTrailと同じく外部サービスと連携して可視化
  * Splunk
  * Logstorage
  * CloudCheckr
  * 2ndWatch
  * etc...
    https://aws.amazon.com/jp/config/partners/

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### <span class="title-highlight">5. Trusted Advisor</span>

#### 6. 請求周りの設定

<br />

#### Appendix. 複数のAWSアカウント運用Tips

</div>

<!-- page_number: false -->

---

## 5. Trusted Advisor

#### Why / Risk

* 現状のAWS設定に危険な設定がないか不安 :fearful:
* 人手では==チェックしきれない==、適切なチェックができない

#### Answer

* Trusted Advisorで以下の4項目を自動でチェックしてレコメンド
  * ==コスト最適化== (不要なリソースの発見など)
  * ==パフォーマンス== (スペック不足やAWSの制限に達していないかなど)
  * ==セキュリティ== (AWSサービスの権限設定や危険なポート許可など)
  * ==フォールトトレランス== (冗長化やバックアップの設定など)
* Trusted Advisorは無料、サポートレベルによりチェック項目が増加

<!-- page_number: true -->

---

## 5. Trusted Advisor

左上の [サービス] から [Trusted Advisor] をクリック

<img src="./images/05_trustedadvisor_01.png" class="img-practice">

---

## 5. Trusted Advisor

4項目がすべてグリーンになっているかチェック

<img src="./images/05_trustedadvisor_02.png" class="img-practice">

---

## 5. Trusted Advisor

先ほど作業したルートアカウントのMFAが有効でなかったり、EC2に対して不要だと思われるポートが許可されていると以下のように警告が表示される

<img src="./images/05_trustedadvisor_03.png" class="img-practice">

---

## 5. Trusted Advisor

[通知設定] から変化があった場合にメールでの通知を行うことができる

<img src="./images/05_trustedadvisor_05a.png" class="img-practice">

受信するメールアドレスを設定

<img src="./images/05_trustedadvisor_06.png" class="img-practice-small">

1週間ごとにサマリのレポートメールが届く

<!-- note
メールアドレスを設定してくださいから、AWSアカウントとは異なる別のメールアドレスを設定可能です。
必要に応じて言語を日本語に設定。
-->

---

## 5. Trusted Advisor

#### Why / Risk

* 現状のAWS設定に危険な設定がないか不安 :fearful:
* 人手では==チェックしきれない==、適切なチェックができない

#### Answer

* Trusted Advisorで以下の4項目を自動でチェックしてレコメンド
  * ==コスト最適化== (不要なリソースの発見など)
  * ==パフォーマンス== (スペック不足やAWSの制限に達していないかなど)
  * ==セキュリティ== (AWSサービスの権限設定や危険なポート許可など)
  * ==フォールトトレランス== (冗長化やバックアップの設定など)
* Trusted Advisorは無料、サポートレベルによりチェック項目が増加

<!-- page_number: true -->

---

## Break

#### サポートレベルによりチェック項目が増加

* Basicプラン (Free)
チェック項目数==4個== (コスト最適化とフォールトトレランスはなし)

<img src="./images/05_trustedadvisor_04a.png" class="img-practice-small">

* Businessサポートの場合 (月額料金1割増し or $100)
チェック項目数==55個==
https://aws.amazon.com/jp/premiumsupport/trustedadvisor/best-practices/

<img src="./images/05_trustedadvisor_04b.png" class="img-practice-small">

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### <span class="title-highlight">6. 請求周りの設定</span>

<br />

#### Appendix. 複数のAWSアカウント運用Tips
</div>

<!-- page_number: false -->

---

## 6. 請求周りの設定

#### Why / Risk

* デフォルトでは料金を見るのにルートアカウントが必要になる :thinking:
* 気づかないうちにAWSの料金が==予算をオーバー==していた :tired_face: :moneybag:
* 意図していない支払いが発生していた :money_with_wings: :money_with_wings: :money_with_wings:

#### Answer

* IAMユーザーでも見れるようにする
  * 経理の方など請求周りの権限のみを持ったIAMユーザーの作成
* コストエクスプローラーにより料金の詳細な分析
* 毎月の実績や予測の予算を設定して、==超過しそうなら通知== :blush:
* 毎月の料金をメールで受信する

<!-- page_number: true -->

---

## 6. 請求周りの設定 (IAM User)

メニューから [請求ダッシュボード] をクリック

<img src="./images/06_billing_01.png" class="img-practice">

アクセス権限がないため拒否される

<img src="./images/06_billing_02.png" class="img-practice">

---

## 6. 請求周りの設定 (IAM User)

一度サインアウトし、ルートアカウントでサインインし直す

<img src="./images/06_billing_03.png" class="img-practice-small">

メニューから [アカウント] をクリック

<img src="./images/06_billing_04.png" class="img-practice">

---

## 6. 請求周りの設定 (IAM User)

[IAMユーザー/ロールによる請求情報へのアクセス] の編集をクリックし、

<img src="./images/06_billing_05a.png" class="img-practice">

[IAMアクセスのアクティブ化] を設定

<img src="./images/06_billing_05b.png" class="img-practice">

---

## 6. 請求周りの設定 (IAM User)

再度サインアウトしてIAMユーザーでサインインし直し、
メニューから [請求ダッシュボード] へアクセス

<img src="./images/06_billing_06.png" class="img-practice">

月のAWSサービス別の料金が表示される

<!-- note
今使用しているIAMユーザーはAdmin権限を持っているので料金を見れるが、
権限の設定により料金を見れないようにしたり、経理向けに料金だけ見れるIAMユーザーを作ることも可能。
-->

---

## 6. 請求周りの設定 (CostExplorer)

#### コストエクスプローラー

コストエクスプローラーを使用すれば自由な分析が可能 (利用は無料)

* 日別／月別／年別の料金や推移
* 任意のタグでグルーピングした料金
* Consolidated Billingでまとめた各AWSアカウントの料金など

<img src="./images/06_billing_08.png" class="img-practice">

<!-- note
通常のダッシュボードでどのAWSリソースでどのくらい費用が発生しているかわかるが、
コストエクスプローラを使えばビューという形で好きな
-->

---

## 6. 請求周りの設定 (CostExplorer)

コストエクスプローラーの有効化

<img src="./images/06_billing_07.png" class="img-practice">

<!-- note
これだけです。
今日AWSアカウントを作った方はほとんど料金が発生していないのでリロードすれば使えると思いますが、何も表示されないかもしれません。
反対に結構AWS使ってるよという方は、表示が有効になるまで少し時間がかかるかもしれません。
-->

---

## 6. 請求周りの設定 (Budgets)

#### 予算

設定することで、料金が超過する／超過することが予想される場合などに
アラートを送信することができる

<img src="./images/06_billing_09.png" class="img-practice">

<!-- note
試しに作ってみましょう。
-->

---

## 6. 請求周りの設定 (Budgets)

月別の予測コストが、指定した予算 ($100) の80%を超過した場合に
メールで通知

<img src="./images/06_billing_10c.png" class="img-practice-40">
<img src="./images/06_billing_10b.png" class="img-practice-40">

<!-- note
関連コストは何もチェックを入れなければすべて対象。
-->

---

## 6. 請求周りの設定 (Budgets)

実際にAWSから送られてくるメール

<img src="./images/06_billing_11.png" class="img-practice-small">

---

## 6. 請求周りの設定 (Mail)

毎月の請求書 (PDF) をメールで受信する

<img src="./images/06_billing_12.png" class="img-practice">

<!-- note
経理の方向け。
-->

---

## 6. 請求周りの設定

#### Why / Risk

* デフォルトでは料金を見るのにルートアカウントが必要になる :thinking:
* 気づかないうちにAWSの料金が==予算をオーバー==していた :tired_face: :moneybag:
* 意図していない支払いが発生していた :money_with_wings: :money_with_wings: :money_with_wings:

#### Answer

* IAMユーザーでも見れるようにする
  * 経理の方など請求周りの権限のみを持ったIAMユーザーの作成
* コストエクスプローラーにより料金の詳細な分析
* 毎月の実績や予測の予算を設定して、==超過しそうなら通知== :blush:
* 毎月の料金をメールで受信する

<!-- page_number: true -->

---

## Break

#### アカウントや請求周りは他にもこんな設定が

* 支払い通貨の変更 ($ → ¥)
  * ==クレカの手数料込みのレート== or ==AWSのレート==
* 秘密の質問の設定による本人確認の強化
* AWSからのマーケティングメールの受信設定
* 時間別の詳細料金レポートをS3にcsv出力

<img src="./images/06_billing_13.png" class="img-practice">

自分の組織／環境にあわせて==適切な設定==を

<!-- note
通貨の設定は普通クレジットカード払いだと思いますが、クレジットカードの
秘密の質問の設定は必須ではなくて、特にこれを設定していて役に立ったことはないので、個人的には設定してません。
自分ひとりで使うなら設定しても良いと思いますが、会社のアカウントなんかだと質問を共有し忘れるとトラブルの元になったりすると思うので、
AWSからのマーケティングメールの受信はアカウント数が増えてくるとAWSからのメールの量も馬鹿にならないので必要に応じて設定。
最後の詳細レポートはプログラムでデータを扱う場合などに。
詳細料金のレポート以外は、表示されている [アカウント] の設定画面から設定できます。
自分の環境にあわせて適切な設定をしてください。
-->

---

# まとめ

* AWSアカウントを取得したら、==MFA==の設定や==IAMユーザー==の利用、
==証跡ログ==の記録など要件にあわせて初期設定をしておきましょう
※本番環境はとくに注意
* 設定しない場合でも、どういうリスクがあるかは把握しておきましょう
* AWSアカウントやコストの管理は==自己責任== (ユーザー責任) です :thinking:
* 予算超過のアラートやコストエクスプローラー、Trusted Advisorなど無料で利用できる==便利なサービス==が揃っています
* 夜も眠れない場合はAWSサポートやSAの方に相談を :innocent:

---

# Wrap up

#### 使用したリソースの削除

* 作成したCloudTrail、AWS Configの削除
* S3バケット、SNSのトピックの削除
* 作成したIAMユーザー、IAMグループの削除

#### Thanks!! & Questions?

本セッションの内容は以上です
お疲れ様でした
このあとも==JAWS DAYS 2017==をお楽しみください

<img src="./images/00_jaws.png" class="img-jaws-logo">

---

<!-- *template: invert -->

<div align="left">

#### 1. ルートアカウントの保護

#### 2. IAMユーザーとパスワードポリシー

#### 3. 証跡ログの設定

#### 4. 構成管理の設定

#### 5. Trusted Advisor

#### 6. 請求周りの設定

<br />

#### <span class="title-highlight">Appendix. 複数のAWSアカウント運用Tips</span>

</div>

<!-- page_number: false -->

---

## Apx. 複数のAWSアカウント運用

#### Why / Risk

* システム／環境が増えればAWSアカウントも増える
  * AWSのサービス制限の中にはアカウント単位のものもある
* ログイン用のIAMユーザー :arrow_up::arrow_up:
  * システム数 x 環境数 x 担当者数 = :scream:
* アカウントごとに請求されることで請求処理の手間 :moneybag:

#### Answer

* 担当者につきIAMユーザーは1つで複数のAWSアカウントにログイン
  * Switch RoleによるAWSアカウント切り替え :yum:
* 複数AWSアカウントの請求を1つにまとめる
  * Consolidated Billing (一括請求)

<!-- page_number: true -->

<!-- note
アカウント分割についての考え方
http://dev.classmethod.jp/cloud/aws/account-and-vpc-dividing-pattern/
例えば
Lambdaの同時実行数100
DynamoDBにはアカウントあたりの最大キャパシティーユニットがある
CodeDeployの同時デプロイ数が1アカウント10
SESのメール送受信レートが共有化されたり（STGでバウンスを大量に出してしまって、本番のメールも制限されそうになる、とか）
-->

---

## Apx. 複数のAWSアカウント運用

#### Switch Role

IAMユーザー = ログインやAPIでのアクセスに使用
IAMロール = IAMポリシー(権限)が付与された役割

<img src="./images/09_organazations_98.png" class="img-practice-small">

* AWSアカウントが4つある場合、そのまま利用すると利用者1人につき
ログイン用のIAMユーザーが4つ必要になる
* Switch Roleを使用すると、3つのAWSアカウントに切り替え用のIAMロールを作成し、利用者1人につきログイン用のIAMユーザーは1つですむ

---

## Apx. 複数のAWSアカウント運用

#### Consolidated Billing

実際に請求がくる親アカウント1つと、
支払いをしてもらう子アカウント複数を、
Consolidated Billingアカウントファミリーとして紐付ける
支払いは親アカウントからまとめておこなわれる
https://docs.aws.amazon.com/ja_jp/awsaccountbilling/latest/aboutv2/consolidated-billing.html
<img src="./images/09_organazations_97.png" class="img-practice-small">

ボリューム割引やファミリー間のReserved Instances共有などのメリットも

<!--
注意点として、有料サポートは各アカウント個別で入る必要があります
-->

---

## Apx. 複数のAWSアカウント運用

#### AWS Organazations

[https://aws.amazon.com/jp/about-aws/whats-new/2017/02/aws-organizations-now-generally-available/](https://aws.amazon.com/jp/about-aws/whats-new/2017/02/aws-organizations-now-generally-available/)

<img src="./images/09_organazations_00.png">

---

## Apx. 複数のAWSアカウント運用

* Consolidated Billing + 複数AWSアカウントを管理
* ポリシーを適用することで利用できるAWSリソースを機能を制限

<img src="./images/09_organazations_96.png" class="img-practice">

---

## Apx. 複数のAWSアカウント運用

以下のURLにアクセスし、 [使用を開始する]
[https://aws.amazon.com/jp/organizations/](https://aws.amazon.com/jp/organizations/)

<img src="./images/09_organazations_01.png" class="img-practice-small">

[Create Organazatioin] をクリック

<img src="./images/09_organazations_02a.png" class="img-practice-small">

<!--
またAWSコンソールに戻ってくるので、
ブラウザで新しいタブを開いて、OrganazationsのURLにアクセスしてください
-->

---

## Apx. 複数のAWSアカウント運用

[ENABLE ALL FEATURES] をクリック

<img src="./images/09_organazations_03.png" class="img-practice-40">

* ENABLE ONLY CONSOLIDATED BILLING
  * これまでのConsolidated Billingのみの機能、請求をまとめるだけ
* ENABLE ALL FEATURES
  * 上記に加え、ポリシーによる権限管理や今後実装されるであろう
    機能が利用可能

<!-- note
すでにConsolidated Billingを利用されていた方は、
いつの間にかこのENABLE ONLY CONSOLIDATED BILLINGに移行されています
その場合、ENABLE ALL FEATURESに切り替えることも可能です
-->

---

## Apx. 複数のAWSアカウント運用

:star: マスターアカウントになる
※Consolidated Billingでいう親アカウント (実際に請求がくる)

<img src="./images/09_organazations_04b.png" class="img-practice">

左上の [Add account] からAWSアカウントを追加

<img src="./images/09_organazations_04c.png" class="img-practice">

<!-- note
これがAWS Organazations、この組織のマスターアカウントになります
Consolidated Billingでいう親アカウント、請求処理を行うのアカウント
-->

---

## Apx. 複数のAWSアカウント運用

[Create account] からAWSアカウントを新規作成

<img src="./images/09_organazations_05a.png" class="img-practice-small">

[Create account] で新規作成したAWSアカウントは現状削除できない
ただし解約はできる、、、AWS Organazations上から消せないだけ :thinking:

<img src="./images/09_organazations_10.png" class="img-practice-small">

[Remove account] しようとしても。。 :rage:

<img src="./images/09_organazations_09e.png" class="img-practice-40">

<!-- note
次に追加のAWSアカウントを作っていきましょう
注意点として、Organazationsでは新規アカウントを作成するか、既存アカウントをInviteで追加するかの2つのパターンがありますが、
作成したアカウントは削除できないようです
ただ、AWSアカウント自体の解約はできるので、アカウントが削除できないというよりはOrganazationsの管理上から削除できない、という話のようです
なので、もし既存アカウントでハンズオンされている方でよくわからないから嫌だと言う方は、
スライドを見ていただくか、別アカウントをInviteもできるのでそちらでハンズオンをすすめてください
-->

---

## Apx. 複数のAWSアカウント運用

①[Full name] はAWSアカウント名
②[Email] はAWSアカウントを作成する際に入力するメールアドレスで一意
　※ハンズオンの最初で作成したメールアドレスとは異なるものを設定
③[IAM role name] は作成するAWSアカウントに用意されるIAMロール名
　※未指定だと [OrganizationAccountAccessRole] になる

<img src="./images/09_organazations_06c.png" class="img-practice">

<!-- note
EmailはAWSアカウント作るときに最初に入力するメールアドレスと同等です
一意である必要があるので、ハンズオンの最初で作ったAWSアカウントのメールアドレスとは異なるものを設定して下さい
IAM role nameは入れなくてもいいですが、入れておいたほうがわかりやすいです
-->

---

## Apx. 複数のAWSアカウント運用

AWSアカウントの追加が完了
※追加されたAWSアカウントの [Account ID] をメモ

<img src="./images/09_organazations_07a.png" class="img-practice">

右上のIAMユーザー名をクリックし [ロールの切り替え]

<img src="./images/09_organazations_11.png" class="img-practice">

<!-- note
無事AWSアカウントが作成されました
ここから作成されたAWSアカウントに切り替えていきます
-->

---

## Apx. 複数のAWSアカウント運用

①[アカウント] には先ほどメモした作成したAWSアカウントの
　[Account ID (12桁数字)] を入力
②[ロール] には作成したAWSアカウントのIAMロール名を入力
　※作成時に未指定の場合は [OrganizationAccountAccessRole]
③[表示名] はエイリアスなのでお好みで

<img src="./images/09_organazations_12.png" class="img-practice">

<!-- note
最後の色は複数切り替えるとどれがどのアカウントかパット見わかりにくくなるので、
例えば本番環境は赤色でテスト環境は青色とか、
そういう管理目的で設定する内容になりますのでお好みで
-->

---

## Apx. 複数のAWSアカウント運用

AWSアカウントが切り替わる
右上のアカウント名が [IAMロール名]@[Account ID] になる
※ロールの切り替えで [表示名] を設定した場合は [表示名] が表示

左上の [サービス] から [IAM] をクリック

<img src="./images/09_organazations_13.png" class="img-practice">

初期状態のIAMの画面が表示

<img src="./images/09_organazations_14.png" class="img-practice-40">

---

## Apx. 複数のAWSアカウント運用

左メニューから [ロール] をクリック
AWS OrganazationsからAWSアカウント作成の際に指定したIAMロールが表示されるので、ロール名をクリック

<img src="./images/09_organazations_15.png" class="img-practice-small">

[AdministratorAccess] ポリシーが設定されている
今後はこのIAMロールを起点に、必要な役割分のIAMロールを作成してマスターアカウントに作成したIAMユーザーから切り替えて利用

<img src="./images/09_organazations_16.png" class="img-practice-40">

---

## Apx. 複数のAWSアカウント運用

右上のアカウント名をクリック
①がAWSコンソールにログインしたIAMユーザーとAWSアカウントの情報
②が現在操作中の切り替えた先のIAMロールとAWSアカウントの情報

[請求ダッシュボード] をクリック

<img src="./images/09_organazations_18c.png" class="img-practice-small">

最初から料金が見える状態になっている (P76の設定不要)

<img src="./images/09_organazations_19.png" class="img-practice-small">

---

## Apx. 複数のAWSアカウント運用

左メニューから [一括請求] をクリック
AWS Organationsのメンバーで、料金請求はマスターアカウントにまとめられている

<img src="./images/09_organazations_20.png" class="img-practice-small">

右上のアカウント名クリックから [アカウント] へ

<img src="./images/09_organazations_21.png" class="img-practice-small">

---

## Apx. 複数のAWSアカウント運用

AWSアカウントの住所など連絡先はマスターアカウントと同じものが設定されている

<img src="./images/09_organazations_22.png" class="img-practice-small">

右上のアカウント名クリックから [xxx (IAMユーザー名) に戻る] で切り替え元のAWSアカウントに戻る
※ハンズオンでは最初にIAMユーザーを作成したAWSアカウントに戻る

<img src="./images/09_organazations_23.png" class="img-practice-small">

---

## Apx. 複数のAWSアカウント運用

#### Why / Risk

* システム／環境が増えればAWSアカウントも増える
  * AWSのサービス制限の中にはアカウント単位のものもある
* ログイン用のIAMユーザー :arrow_up::arrow_up:
  * システム数 x 環境数 x 担当者数 = :scream:
* アカウントごとに請求されることで請求処理の手間

#### Answer

* AWS Organazationsを利用してAWSアカウントを一元管理
  * 担当者につきIAMユーザーは1つで複数のAWSアカウントにログイン
    * Switch RoleによるAWSアカウント切り替え :yum:
  * 複数AWSアカウントの請求を1つにまとめる

---

## Break

#### AWS Organazations Tips (1/2)

* ポリシー (Service Control Policies: SCPs) により、各AWSアカウントで利用できるAWSサービスとオペレーションを制限できる
  * 例えばEC2とS3のみ利用可能だがEC2のTerminateは禁止、など
  * システムに必要なAWSサービスのみ制限したり、本番環境で不要なAWSサービス作成を制限したり
  * AWS OrganazationsのポリシーとIAMポリシーによる両方の制限
<img src="./images/09_organazations_99.png" class="img-practice-small">

* OUという組織単位でAWSアカウントをグルーピング＆階層構造で管理
  * ポリシーをOUに設定して配下のOU／AWSアカウントすべてに適用


<!-- note
AWS Organazationsはもう一つメイン機能としてService Control Policy、通称SCPというポリシーを利用して、
AWSアカウントで何のサービス、何のオペレーションが出来るのか許可／拒否など制限を行うことができます
なのでこのシステム用に作成したAWSアカウントではシステムに利用しないサービスを制限したり、
本番アカウントでは
-->

---

## Break

#### AWS Organazations Tips (2/2)

* AWS OrganazationsからAWSアカウントを作成した場合のルートアカウントは？
  * 存在するがパスワード未設定の状態になっている
  * サインイン時の [Forgot your password?] からパスワードを設定すれば使えるようになる

<img src="./images/09_organazations_17.png" class="img-practice-30">

EC2-Mail送信制限緩和や侵入テスト申請など、
どうしてもルートアカウントが必要な場面で

<!-- note
ルートアカウントは必要がなければ使わないのがベスト
-->

---

# EOF

<!-- page_number: false -->
