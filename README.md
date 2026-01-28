# OpenCode Web on GitHub Codespaces

iPhone などのモバイルデバイスからブラウザ経由で OpenCode Web にアクセスするための環境です。

## セットアップ手順

### 1. リポジトリの準備

このリポジトリを GitHub にプッシュするか、フォークしてください。

### 2. Codespaces の起動

1. GitHub リポジトリページを開く
2. 緑色の「Code」ボタンをクリック
3. 「Codespaces」タブを選択
4. 「Create codespace on main」をクリック

初回起動時は環境構築に数分かかります。

### 3. OpenCode Web へのアクセス

Codespaces が起動すると、ターミナルに以下のような URL が表示されます：

```
============================================
🚀 OpenCode Web is starting...

📱 Access URL (copy this for iPhone):

https://xxx-3000.app.github.dev

============================================
```

この URL をコピーしてブラウザで開いてください。

## iPhone からのアクセス方法

1. Codespaces を起動
2. ターミナルに表示される URL を長押ししてコピー
3. Safari で開く
4. GitHub アカウントでログイン（初回のみ）

## 初回起動時のプロバイダー設定

OpenCode Web を初めて使う場合、LLM プロバイダーの設定が必要です。

### z.ai を使用する場合

z.ai は月額$3 で Claude API を利用できるサービスです。

1. **z.ai でサブスクリプション登録**

   - https://z.ai/subscribe にアクセス
   - サブスクリプションに登録
   - API キーを取得

2. **OpenCode Web でプロバイダー設定**
   - OpenCode Web の画面で `/connect` と入力
   - 「Others」を選択
   - Base URL: `https://api.z.ai/api/anthropic`
   - API キーを入力

### 他のプロバイダーを使用する場合

`/connect` コマンドから各プロバイダーを選択し、必要な情報を入力してください。

## ディレクトリ構成

```
root/
├── .devcontainer/
│   └── devcontainer.json  # Codespaces設定
├── scripts/
│   └── start-opencode-web.sh  # 起動スクリプト
├── .gitignore
└── README.md
```

## トラブルシューティング

### URL が表示されない

ターミナルで手動で起動スクリプトを実行してください：

```bash
bash /workspaces/opencode-workspace/scripts/start-opencode-web.sh
```

### ポートが公開されていない

1. VS Code の「PORTS」タブを開く
2. ポート 3000 の行を右クリック
3. 「Port Visibility」→「Public」を選択

### 接続できない

- Codespaces が実行中であることを確認
- URL が正しいことを確認（`-3000`が含まれている）
- GitHub にログインしているか確認

## 参考リンク

- [OpenCode 公式ドキュメント](https://opencode.ai/docs/web/)
- [GitHub Codespaces](https://github.com/features/codespaces)
- [z.ai](https://z.ai/)
