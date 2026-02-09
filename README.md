# Instagram投稿文ジェネレーター

商品URLを入力すると、クライアントごとのトンマナに合わせたInstagram投稿文を生成し、xlsxでダウンロードできるWebアプリです。

## セットアップ

### 1. 依存パッケージのインストール
```bash
pip install -r requirements.txt
```

### 2. Gemini APIキーの設定
`.streamlit/secrets.toml` を編集し、Google Gemini APIキーを設定してください：
```toml
GEMINI_API_KEY = "あなたのGemini APIキー"
```

APIキーは https://aistudio.google.com/apikey から無料で取得できます。

### 3. アプリの起動
```bash
streamlit run app.py
```

ブラウザで `http://localhost:8501` が自動で開きます。

## 使い方

### 初回：クライアントプロフィールの作成
1. サイドバーで「（新規作成）」を選択
2. クライアントIDを入力（例: `toutvert`）
3. ブランド名、トンマナ指示、サンプル投稿文、テンプレート等を入力
4. 「💾 保存」をクリック

### 投稿文の生成
1. サイドバーでクライアントを選択
2. メインエリアに商品URLを1行1つずつ入力
3. 「✨ 投稿文を生成」をクリック
4. 生成されたキャプションを確認・編集
5. 「📥 xlsxをダウンロード」でファイル取得

### xlsxの活用
ダウンロードしたxlsxファイルは、Googleスプレッドシートに新規タブとしてインポートできます：
- Googleスプレッドシートを開く → ファイル → インポート → アップロード → 「新しいシートに挿入する」

## デプロイ（Streamlit Community Cloud）
1. このフォルダをGitHubリポジトリにプッシュ
2. https://share.streamlit.io/ でリポジトリを連携
3. Secrets設定で `GEMINI_API_KEY` を登録
4. デプロイ完了
