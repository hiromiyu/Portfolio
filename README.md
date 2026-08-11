# Hiro Portfolio Website

Web・iOSアプリ開発を行っている Hiro のポートフォリオサイトです。

制作したWebアプリケーションや使用技術、開発で取り組んでいることを紹介しています。

## 🌐 About

このサイトでは、以下の内容を紹介しています。

- Webアプリケーションの制作実績
- iOSアプリケーションの制作実績
- 使用している技術
- 個人開発で取り組んでいること
- お問い合わせフォーム

## ✨ Portfolio

### SNS Application

XのようなSNSアプリを個人開発しています。

ユーザー認証から投稿、画像投稿、いいね、コメント、返信、フォローなど、SNSの基本的な機能を実装しています。

#### 主な機能

- ユーザー登録・ログイン
- 投稿
- 画像投稿
- いいね
- コメント
- コメントへの返信
- フォロー・フォロワー
- プロフィール
- 投稿削除
- 無限スクロール
- 仮想スクロール

#### パフォーマンスへの取り組み

投稿一覧を表示する際、投稿ごとにいいね情報を取得するとAPIリクエスト数が増加するため、投稿一覧APIで `like_count` と `is_liked` をまとめて取得する設計にしています。

これにより、

```text
改善前

GET /api/posts
GET /api/likes/1
GET /api/likes/2
GET /api/likes/3
...
```

のようなN+1問題を、

```text
改善後

GET /api/posts
```

の1回のAPIリクエストで必要な情報を取得できるように改善しました。

また、`react-virtuoso` を利用して仮想スクロールを実装し、大量の投稿を効率的に表示できるようにしています。

## 🛠 Technology

### Frontend

- React
- TypeScript
- Vite
- React Router
- Tailwind CSS
- react-virtuoso

### Backend

- Hono
- TypeScript
- Cloudflare Workers

### Database

- Cloudflare D1
- SQLite

### Authentication / Storage

- Supabase Auth
- Supabase Storage

### Hosting / Infrastructure

- Cloudflare

## 📁 Project Structure

```text
.
├── index.html
├── style.css
├── favicon.ico
├── manifest.json
└── images/
    └── sns-app.png
```

## 📱 Responsive Design

PC・タブレット・スマートフォンから閲覧できるよう、レスポンシブデザインに対応しています。

## 📩 Contact

サイト内のお問い合わせフォームから連絡できます。

お問い合わせフォームでは、Cloudflare Turnstileを利用してBot対策を行っています。

## 🚀 Getting Started

### Clone

```bash
git clone https://github.com/hiromiyu/Portfolio.git
cd Portfolio
```

### Run locally

静的HTML/CSSサイトなので、ブラウザで `index.html` を開くことで確認できます。

ローカルサーバーを利用する場合は、例えば以下のように起動できます。

```bash
python3 -m http.server 8000
```

その後、ブラウザから以下にアクセスします。

```text
http://localhost:8000
```

## 📌 Future Improvements

今後、以下のような改善を予定しています。

- 制作実績の追加
- SNSアプリの詳細ページ追加
- iOSアプリの制作実績追加
- アニメーションの追加
- 英語・日本語の多言語対応
- デザインのさらなる改善

## 👤 Author

Hiro

Web・iOSアプリケーションの個人開発を行っています。

---

© 2026 Hiro

```

```
