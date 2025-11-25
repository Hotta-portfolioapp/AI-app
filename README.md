# 概要

AIの生成ノウハウを売買して共有できるアプリ

---

# アプリ URL / GitHub リポジトリ

- アプリURL: [https://ai-app-5rve.onrender.com](https://ai-app-5rve.onrender.com)  
- GitHubリポジトリ: [https://github.com/Hotta-portfolioapp/AI-app.git](https://github.com/Hotta-portfolioapp/AI-app.git)

---

## 作成目的

- StripeやActioncableといった商用に関連性の高いRailsの機能を用いて、開発を学習するため
- API通信やデータベース設計の理解を深めるため
- rspecのテスト構造の理解を深めるため
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

- Rails 8 アプリ
  - フロントエンド: JavaScript / Bootstrap / Turbo
  - 認証: Devise
- データベース: PostgreSQL
- 開発環境: Docker Compose
- デプロイ: Render
- CI/CD: GitHub Actions
  - rubocop と rspec が pass したら自動で Render にデプロイ
- 画像・動画管理: Cloudinary（本番環境のみ）

---

## データ構造・ER図

アプリのデータベース構造を示します。

![ER図](./screenshots/er_diagram.png)

### 補足
- `users` テーブル: アプリ利用者情報
- `tasks` テーブル: ユーザーのタスク情報（user_id が外部キー）
- `categories` テーブル: タスクのカテゴリ
- 1人のユーザーは複数のタスクを持つ (1:N)
- タスクは 1 つのカテゴリに所属 (N:1)

---

## 学んだこと・今後の改善

- フルスタック開発（フロント・バックエンド）の理解を深めた
- 認証・CRUD操作・API連携の基礎を経験
- 今後の改善点：
  - テストコードの追加（RSpec / Jest）
  - UI/UX改善（ドラッグ＆ドロップでタスク順番変更など）
  - CI/CD の導入
