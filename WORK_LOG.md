# AWS Exam Coach プロジェクト作業記録

## 2025 年 7 月 25 日（金）- プロジェクト初期設定

### 完了した作業

#### 1. MCP Server 環境構築

- **uv インストール**: Homebrew を使用して uv と uvx をインストール
- **MCP 設定ファイル作成**: `.kiro/settings/mcp.json`でワークスペースレベルの MCP 設定
- **Git MCP Server 設定**: `mcp-server-git`を設定して Git 操作を可能に

#### 2. GitHub 連携設定

- **Personal Access Token 作成**: 90 日有効期限の classic トークンを生成
- **環境変数設定**: `.env`ファイルにトークンを安全に保存
- **GitHub API 接続確認**: リポジトリ一覧取得で動作確認完了

#### 3. GitHub リポジトリ作成

- **リポジトリ作成**: `kobank-t/aws-exam-coach`を Public リポジトリとして作成
- **説明**: "AWS 試験対策コーチングアプリケーション"
- **URL**: https://github.com/kobank-t/aws-exam-coach

#### 4. ローカル開発環境セットアップ

- **Git リポジトリ初期化**: ローカルで Git リポジトリを初期化
- **ブランチ設定**: デフォルトブランチを main に変更
- **リモート接続**: GitHub リポジトリとの接続設定
- **基本ファイル作成**:
  - `README.md`: プロジェクト概要
  - `.gitignore`: 環境変数とログファイルを除外
  - `.env`: GitHub Personal Access Token 保存
  - `.kiro/settings/mcp.json`: MCP Server 設定

#### 5. 初回コミット＆プッシュ

- **コミット**: "Initial commit: Setup project structure and MCP configuration"
- **プッシュ**: main ブランチにプッシュ完了

### 設定済みファイル構成

```
aws-exam-coach/
├── .env                      # GitHub Personal Access Token
├── .gitignore               # Git除外設定
├── .kiro/
│   └── settings/
│       └── mcp.json         # MCP Server設定
├── .vscode/
│   └── settings.json        # VS Code設定
├── README.md                # プロジェクト概要
└── WORK_LOG.md             # 作業記録（このファイル）
```

### 技術環境

- **MCP Server**: Git 操作対応
- **GitHub API**: 認証済み、リポジトリ操作可能
- **開発ツール**: uv/uvx インストール済み
- **リポジトリ**: GitHub 連携完了

### 次回作業予定

1. **開発要件策定**: Spec 作成ワークフローを使用

   - 要件定義（requirements.md）
   - 設計書作成（design.md）
   - タスクリスト作成（tasks.md）

2. **技術スタック決定**:

   - フロントエンド技術選定
   - バックエンド技術選定
   - データベース選定

3. **プロジェクト構造設計**:
   - ディレクトリ構造
   - 開発環境設定
   - CI/CD 設定

### メモ

- GitHub Personal Access Token は 90 日で期限切れ（2025 年 10 月頃）
- MCP Server 設定はワークスペースレベルで完了
- 現在のプロジェクトは Public リポジトリとして設定済み

---

## 2025 年 7 月 26 日（土）- ステアリング設定追加

### 完了した作業

#### 1. Kiro ステアリング機能設定

- **プロジェクトコンテキスト設定**: `.kiro/steering/project-context.md`作成

  - プロジェクト概要とコンテキスト情報
  - 作業記録参照の必須化
  - 日本語回答設定
  - ファイル参照時の明示設定

- **作業記録参照ルール設定**: `.kiro/steering/work-log-reference.md`作成
  - 新しいセッション開始時の必須アクション定義
  - 作業記録更新タイミングの明確化
  - WORK_LOG.md ファイルの自動参照設定

#### 2. セッション継続性の確保

- **自動コンテキスト維持**: 新しいセッションでも前回作業内容を自動参照
- **言語設定の固定**: 常に日本語での回答を保証
- **透明性の向上**: ファイル参照時の明示を義務化

### 設定済みステアリングファイル

```
.kiro/steering/
├── project-context.md      # プロジェクト全体のコンテキスト
└── work-log-reference.md   # 作業記録参照ルール
```

### 次回作業予定

1. **開発要件策定**: Spec 作成ワークフローを使用
   - 要件定義（requirements.md）
   - 設計書作成（design.md）
   - タスクリスト作成（tasks.md）

---

**作業者**: kobank-t  
**作業日**: 2025 年 7 月 25 日（初期設定）、2025 年 7 月 26 日（ステアリング設定）  
**次回作業予定日**: 2025 年 7 月 27 日以降
