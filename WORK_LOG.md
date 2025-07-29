# AWS Exam Coach プロジェクト作業記録

## 目次

- [2025 年 7 月 25 日 - プロジェクト初期設定](#2025-年-7-月-25-日---プロジェクト初期設定)
- [2025 年 7 月 26 日 - ステアリング設定](#2025-年-7-月-26-日---ステアリング設定)
- [2025 年 7 月 27 日 - AWS MCP Server 設定・動作確認](#2025-年-7-月-27-日---aws-mcp-server-設定動作確認)
- [2025 年 7 月 28 日 - 要件定義・プロダクト方向性の確定](#2025-年-7-月-28-日---要件定義プロダクト方向性の確定)
- [2025 年 7 月 29 日 - 設計書作成・AWS Pricing MCP Server 追加](#2025-年-7-月-29-日---設計書作成aws-pricing-mcp-server-追加)
- [現在の環境状況](#現在の環境状況-1)
- [次回作業予定](#次回作業予定)

---

## 2025 年 7 月 25 日 - プロジェクト初期設定

### 完了した作業

#### 開発環境構築

- **uv/uvx インストール**: Homebrew 経由で Python パッケージ管理ツール導入
- **Git MCP Server 設定**: `.kiro/settings/mcp.json`で Git 操作を可能に

#### GitHub 連携

- **Personal Access Token 作成**: 90 日有効期限（2025 年 10 月頃期限切れ）
- **リポジトリ作成**: `kobank-t/aws-exam-coach` (Public)
- **初回コミット・プッシュ**: プロジェクト基盤ファイル群

#### 基本ファイル作成

- `README.md`: プロジェクト概要
- `.gitignore`: 環境変数・ログファイル除外設定
- `.env`: GitHub Personal Access Token 保存
- `WORK_LOG.md`: 作業記録（このファイル）

---

## 2025 年 7 月 26 日 - ステアリング設定

### 完了した作業

#### Kiro ステアリング機能設定

- **プロジェクトコンテキスト**: `.kiro/steering/project-context.md`
  - プロジェクト概要・技術環境情報
  - 日本語回答設定・作業記録参照の必須化
- **作業記録参照ルール**: `.kiro/steering/work-log-reference.md`
  - セッション開始時の自動コンテキスト維持
  - 作業記録更新タイミング定義

---

## 2025 年 7 月 27 日 - AWS MCP Server 設定・動作確認

### 完了した作業

#### AWS MCP Server 追加・設定

- **AWS Documentation MCP Server**: `awslabs.aws-documentation-mcp-server@latest`
- **AWS Knowledge MCP Server**: `npx mcp-remote https://knowledge-mcp.global.api.aws` (リモートサーバ)
- **AWS Diagram MCP Server**: `awslabs.aws-diagram-mcp-server@latest`

#### 動作確認結果

| MCP サーバ        | 状態        | 機能確認                                     |
| ----------------- | ----------- | -------------------------------------------- |
| Git               | ✅ 正常動作 | Git 操作                                     |
| AWS Documentation | ✅ 正常動作 | AWS 公式ドキュメント検索・参照               |
| AWS Knowledge     | ✅ 正常動作 | AWS 認定試験関連情報検索                     |
| AWS Diagram       | ✅ 正常動作 | AWS 構成図生成（全サービスアイコン利用可能） |

---

## 現在の環境状況

### プロジェクト構成

```
aws-exam-coach/
├── .env                      # GitHub Personal Access Token
├── .gitignore               # Git除外設定
├── .kiro/
│   ├── settings/
│   │   └── mcp.json         # MCP Server設定
│   └── steering/
│       ├── project-context.md
│       └── work-log-reference.md
├── README.md                # プロジェクト概要
└── WORK_LOG.md             # 作業記録
```

### 技術環境

- **GitHub**: リポジトリ連携完了
- **MCP Server**: 4 つのサーバが正常動作
- **開発ツール**: uv/uvx, npx 利用可能
- **Kiro ステアリング**: セッション継続性確保

### 利用可能な機能

- **AWS 認定試験知識ベース検索** (AWS Knowledge MCP)
- **AWS 公式ドキュメント参照** (AWS Documentation MCP)
- **AWS 構成図自動生成** (AWS Diagram MCP)
- **Git 操作** (Git MCP)

---

## 2025 年 7 月 28 日 - 要件定義・プロダクト方向性の確定

### 完了した作業

#### Spec 作成ワークフロー - 要件定義フェーズ

- **初期要件作成**: AWS Certified Solutions Architect - Professional 向け学習アプリ
- **重要な方向転換**: 個人学習ツール → 組織内コラボレーション学習プラットフォーム

#### プロダクト目的の明確化

**真の目的が判明:**

- **開発側**: AI エージェント技術のスキルアップ
- **利用側**: 200 名エンジニア組織のコミュニケーション活性化
- **共通**: ワイガヤを通じたスキルトランスファー促進

#### 技術方式の決定

**当初検討**: Teams App 開発（複雑・時間がかかる）
**最終決定**: Power Automate + Teams リアクション方式

- Teams Webhook 廃止予定のため Power Automate 採用
- リアクション（A,B,C,D 絵文字）による回答
- スレッドでの解説・議論

#### 要件仕様の確定

- **対象**: AWS Certified Solutions Architect - Professional
- **利用環境**: 社内、Teams チャネル、会社支給 PC・iPhone
- **情報源**: AWS 公式ドキュメント + 試験ガイド（MVP）
- **拡張予定**: FAQ、What's New、Well-Architected Framework

### 重要な学び・発見

1. **ペルソナの重要性**: 利用者像が曖昧だと適切な技術選択ができない
2. **組織課題の把握**: 個人学習ではなく組織コミュニケーション活性化が真の目的
3. **段階的アプローチ**: 複雑な技術より、シンプルで早期リリース可能な方式を選択
4. **公式情報源の重視**: 非公式 MCP Server は避け、信頼できる情報源のみ使用

---

## 2025 年 7 月 29 日 - 設計書作成・AWS Pricing MCP Server 追加

### 完了した作業

#### Spec 作成ワークフロー - 設計フェーズ

- **設計書作成開始**: `.kiro/specs/aws-exam-coach/design.md`
- **アーキテクチャ設計**: Power Automate + Teams 連携システム
- **AI 問題生成エンジン詳細設計**: Bedrock AgentCore + Strands Agents 構成
- **問題生成トリガー設計**: スケジュール・HTTP API・Teams コマンド方式

#### 技術スタック確定

**AI エージェント基盤:**

- **エージェントフレームワーク**: Strands Agents (オープンソース)
- **実行環境**: AWS Bedrock AgentCore Runtime (Preview)
- **LLM**: Amazon Bedrock (Claude 4 Sonnet, Claude 3.7 Sonnet)

**バックエンド:**

- **言語**: Python 3.11+
- **フレームワーク**: Strands Agents SDK + FastAPI
- **データベース**: PostgreSQL (問題・解析データ)
- **キャッシュ**: Redis (情報取得キャッシュ)

#### AWS Pricing MCP Server 追加

- **MCP Server 追加**: `awslabs.aws-pricing-mcp-server@latest`
- **設定完了**: `.kiro/settings/mcp.json` に追加
- **自動承認設定**: `get_pricing` ツール
- **用途**: 設計段階でのコスト試算・技術選択支援

#### 設計書進捗状況

**完了セクション:**

- Overview (システム概要・設計原則)
- Architecture (全体構成・主要コンポーネント)
- AI 問題生成エンジン詳細設計 (技術スタック・システム構成・シーケンス図)
- 問題生成トリガー設計 (3 つのトリガー方式)

**次回作業予定:**

- Teams 連携システム詳細
- Data Models
- Error Handling
- Testing Strategy

### 重要な技術決定

1. **Strands Agents 採用**: オープンソースエージェントフレームワーク
2. **Bedrock AgentCore Runtime**: サーバーレス実行環境
3. **MCP 統合**: 標準化されたコンテキスト提供プロトコル
4. **段階的トリガー実装**: HTTP API → Power Automate スケジュール → Teams コマンド

---

## 現在の環境状況

### プロジェクト構成

```
aws-exam-coach/
├── .env                      # GitHub Personal Access Token
├── .gitignore               # Git除外設定
├── .kiro/
│   ├── settings/
│   │   └── mcp.json         # MCP Server設定（5サーバ）
│   ├── specs/
│   │   └── aws-exam-coach/
│   │       ├── requirements.md  # 要件定義完了
│   │       └── design.md        # 設計書作成中
│   └── steering/
│       ├── project-context.md
│       └── work-log-reference.md
├── README.md                # プロジェクト概要
└── WORK_LOG.md             # 作業記録
```

### 技術環境

- **GitHub**: リポジトリ連携完了
- **MCP Server**: 5 つのサーバが正常動作（AWS 関連のみ、公式・信頼できるもの）
- **開発ツール**: uv/uvx, npx 利用可能
- **Kiro ステアリング**: セッション継続性確保

### 利用可能な機能

- **AWS 認定試験知識ベース検索** (AWS Knowledge MCP)
- **AWS 公式ドキュメント参照** (AWS Documentation MCP)
- **AWS 構成図自動生成** (AWS Diagram MCP)
- **AWS 料金情報取得** (AWS Pricing MCP)
- **Git 操作** (Git MCP)

---

## 次回作業予定

### Spec 作成ワークフロー継続

1. ✅ **要件定義** (`requirements.md`) - 完了
2. 🔄 **設計書作成** (`design.md`) - 作成中
3. ⏳ **タスクリスト作成** (`tasks.md`)

### 設計フェーズの重点項目

- Teams 連携システム詳細
- Data Models
- Error Handling
- Testing Strategy

### 備考

- GitHub Personal Access Token 期限: 2025 年 10 月頃
- 全 MCP サーバ動作確認済み（AWS 公式のみ）
- 要件定義完了、設計フェーズ準備完了

---

**作業者**: kobank-t  
**最終更新**: 2025 年 7 月 29 日
