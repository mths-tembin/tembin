# Tembin Portfolio Website

ロゴデザイン、グラフィックデザイン、WEBデザインのポートフォリオサイトです。

## 特徴

- 🎨 モダンなデザインシステム
- 📱 レスポンシブデザイン
- ✨ パララックス効果とスクロールアニメーション
- 📧 メール送信機能付きお問い合わせフォーム
- 🚀 Vercelでの簡単デプロイ

## 技術スタック

- HTML5
- CSS3 (カスタムプロパティ、Grid、Flexbox)
- JavaScript (ES6+)
- EmailJS (メール送信)
- Vercel (ホスティング)

## セットアップ

### 1. リポジトリのクローン

```bash
git clone <repository-url>
cd tembin-portfolio
```

### 2. 依存関係のインストール

```bash
npm install
```

### 3. ローカル開発サーバーの起動

```bash
npm run dev
```

ブラウザで `http://localhost:3000` を開いてサイトを確認できます。

## メール送信機能の設定

### EmailJSの設定

1. [EmailJS](https://www.emailjs.com/) にアカウントを作成
2. メールサービスを設定（Gmail、Outlook等）
3. メールテンプレートを作成
4. 以下の情報を取得：
   - User ID
   - Service ID
   - Template ID

### 設定の更新

`contact/branding-contact.html` の以下の部分を更新：

```javascript
emailjs.init("YOUR_USER_ID"); // あなたのUser ID
```

```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', {
  // メールデータ
});
```

## デプロイ

### Vercelでのデプロイ

1. GitHubリポジトリをVercelに接続
2. 自動デプロイが有効になります
3. プッシュすると自動的にデプロイされます

### 手動デプロイ

```bash
npm run build
vercel --prod
```

## ファイル構造

```
tembin-portfolio/
├── index.html              # メインページ
├── contact/
│   └── branding-contact.html  # お問い合わせフォーム
├── assets/
│   ├── css/
│   │   └── style.css       # メインスタイル
│   ├── js/
│   │   └── main.js         # メインスクリプト
│   └── images/             # 画像ファイル
├── package.json
├── vercel.json
└── README.md
```

## カスタマイズ

### 色の変更

`assets/css/style.css` のCSS変数を編集：

```css
:root {
  --bg-dark: #08211c;
  --bg-main: #0e241e;
  --bg-panel: #274c42;
  --highlight: #c3d647;
  /* その他の色設定 */
}
```

### コンテンツの更新

- `index.html` - メインコンテンツ
- `contact/branding-contact.html` - フォーム内容
- `assets/images/` - 作品画像

## ライセンス

MIT License

## お問い合わせ

- Email: matsuhashi@tembin.jp
- Website: https://tembin.jp
