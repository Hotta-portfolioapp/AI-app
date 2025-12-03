## 概要

あらゆるAI生成ノウハウを、投稿者に直接質問しながら入手できるプラットフォームです。  

**ターゲット**  
- AIの具体的な活用法を学びたいビジネスパーソン  
- AIを活用して制作や業務を効率化したいクリエイター  

**できること**  
- 投稿者が作った最新の生成ノウハウのパッケージで購入できる  
- 投稿者に直接質問して疑問を解消できる  

**購入者メリット**  
- 機械やソフトの操作が苦手な方や忙しい方でも手軽、且つ効率的に学習可能  
- チャットで質問・相談できるため、実務や制作で活用できる、より具体的手法を落とし込める

---

##  アプリ URL / GitHub リポジトリURL

- アプリURL: [https://ai-app-5rve.onrender.com](https://ai-app-5rve.onrender.com)  
- GitHubリポジトリ: [https://github.com/Hotta-portfolioapp/AI-app.git](https://github.com/Hotta-portfolioapp/AI-app.git)


  - デモアカウント　※アプリ動作確認時にご利用ください。
    - 投稿者用アカウント（Seller）
      - メールアドレス：seller@gmail.com
      - パスワード：000000

    - 購入者用アカウント（Buyer）
      - メールアドレス：buyer@gmail.com
      - パスワード：000000
---

## 主な機能

- ユーザー登録・ログイン・ログアウト（Devise 使用）
- コンテンツの新規投稿機能 (Javascriptを使用　STEP1とSTEP2でページ区分やファイルアップロード時のプレビュー表示など)
- コンテンツのカテゴリ・タグ・価格帯別検索機能 (Ransack 使用)
- コンテンツのカード擬似決済機能 (Stripe 使用)
- チャット機能 (ActionCable使用)

![機能説明](./app/assets/images/Feature%20Description/Feature%20Description.png)

---

## 技術スタック

- バックエンド：Ruby 3.3.3(Rails 8.0)
- フロントエンド: JavaScript / Bootstrap / Turbo
- データベース: PostgreSQL 15
- 開発環境: Docker
- 認証: Devise
- デプロイ: Render
- CI/CD: Circl CI / GitHub Actions(Dependabot用)
→ rubocop と rspec が pass したら自動で Render にデプロイ
- 画像・動画管理: Cloudinary（本番環境のみ）

---

## データ構造・ER図

アプリのデータベース構造を示します。

![ER図](./app/assets/images/README_image/Entity%20Relationship%20Diagram.png)

### 補足
- users テーブル: アプリ利用者情報
- knowhows テーブル: 投稿されたコンテンツ情報
- instructions テーブル: コンテンツ(生成ノウハウ)の生成手順情報
- payments テーブル:　決済用カード情報


---

## 学んだこと・今後の改善
- StripeやActioncableといった商用に関連性の高いRailsの機能を学習できた
- API通信やデータベース設計の理解を深めることができた
- rspecのテスト構造の理解を深めることができた

- 今後の改善点
  - DRYを意識したコード設計(現状が冗長的で生産的でない)
  - 本番環境のみ(Render)、チャット送信直後に、チャット一覧にメッセージが表示されずリロードしないと反映されないためため、改善を図る
  - チャットにおける通知機能の追加
  - SP版の実装
