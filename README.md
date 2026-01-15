# OpenCode Web on GitHub Codespaces

iPhoneなどのモバイルデバイスからブラウザ経由でOpenCode Webにアクセスするための環境です。

## セットアップ手順

### 1. リポジトリの準備

このリポジトリをGitHubにプッシュするか、フォークしてください。

### 2. Codespacesの起動

1. GitHubリポジトリページを開く
2. 緑色の「Code」ボタンをクリック
3. 「Codespaces」タブを選択
4. 「Create codespace on main」をクリック

初回起動時は環境構築に数分かかります。

### 3. OpenCode Webへのアクセス

Codespacesが起動すると、ターミナルに以下のようなURLが表示されます：

```
============================================
🚀 OpenCode Web is starting...

📱 Access URL (copy this for iPhone):

https://xxx-3000.app.github.dev

============================================
```

このURLをコピーしてブラウザで開いてください。

## iPhoneからのアクセス方法

1. Codespacesを起動
2. ターミナルに表示されるURLを長押ししてコピー
3. Safariで開く
4. GitHubアカウントでログイン（初回のみ）

## 初回起動時のプロバイダー設定

OpenCode Webを初めて使う場合、LLMプロバイダーの設定が必要です。

### z.ai を使用する場合

z.aiは月額$3でClaude APIを利用できるサービスです。

1. **z.aiでサブスクリプション登録**
   - https://z.ai/subscribe にアクセス
   - サブスクリプションに登録
   - APIキーを取得

2. **OpenCode Webでプロバイダー設定**
   - OpenCode Webの画面で `/connect` と入力
   - 「Others」を選択
   - Base URL: `https://api.z.ai/api/anthropic`
   - APIキーを入力

### 他のプロバイダーを使用する場合

`/connect` コマンドから各プロバイダーを選択し、必要な情報を入力してください。

## ディレクトリ構成

```
opencode-workspace/
├── .devcontainer/
│   └── devcontainer.json  # Codespaces設定
├── scripts/
│   └── start.sh           # 起動スクリプト
├── workspace/             # 作業用ディレクトリ
│   └── .gitkeep
├── .gitignore
└── README.md
```

## トラブルシューティング

### URLが表示されない

ターミナルで手動で起動スクリプトを実行してください：

```bash
bash /workspaces/opencode-workspace/scripts/start.sh
```

### ポートが公開されていない

1. VS Codeの「PORTS」タブを開く
2. ポート3000の行を右クリック
3. 「Port Visibility」→「Public」を選択

### 接続できない

- Codespacesが実行中であることを確認
- URLが正しいことを確認（`-3000`が含まれている）
- GitHubにログインしているか確認

## 参考リンク

- [OpenCode公式ドキュメント](https://opencode.ai/docs/web/)
- [GitHub Codespaces](https://github.com/features/codespaces)
- [z.ai](https://z.ai/)
