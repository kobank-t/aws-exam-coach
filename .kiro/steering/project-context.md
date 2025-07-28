---
inclusion: always
---

# AWS Exam Coach プロジェクトコンテキスト

## プロジェクト概要

- **プロジェクト名**: AWS Exam Coach
- **目的**: AWS 認定試験の学習をサポートするアプリケーション
- **GitHub リポジトリ**: https://github.com/kobank-t/aws-exam-coach

## 重要な指示

- **作業記録の参照**: 新しいセッション開始時は必ず WORK_LOG.md を確認して前回の作業内容と次回予定を把握すること
- **継続性の維持**: 作業記録に基づいて適切な作業フローを継続すること
- **記録の更新**: 重要な作業完了時は WORK_LOG.md を更新すること
- **言語設定**: 回答は常に日本語で行うこと
- **コミットメッセージ**: Git コミットメッセージは日本語で記述すること
- **ファイル参照の明示**: ステアリング機能などでファイルを参照した場合は、参照したファイル名を発言すること

## 現在の開発フェーズ

**Spec 作成ワークフロー開始準備完了** - 要件定義・設計・タスクリスト作成段階

## 技術環境

### MCP Server（全て動作確認済み）

- **Git MCP Server**: Git 操作
- **AWS Documentation MCP Server**: AWS 公式ドキュメント検索・参照
- **AWS Knowledge MCP Server**: 信頼できる AWS ナレッジを LLM 互換形式で提供
  - ドキュメント、ブログ記事、新着情報、Well-Architected ベストプラクティス
  - 正確な推論と一貫性のある実行を支援
- **AWS Diagram MCP Server**: AWS 構成図自動生成

### 開発環境

- **GitHub API**: 認証済み、リポジトリ操作可能
- **開発ツール**: uv/uvx, npx 利用可能
- **Kiro ステアリング**: セッション継続性確保済み

### 利用可能な機能

- 信頼できる AWS ナレッジ・ベストプラクティスへのアクセス
- AWS 公式ドキュメントへのアクセス
- AWS 構成図の自動生成（全サービスアイコン対応）
- Git 操作・バージョン管理

## プロジェクト構成

```
aws-exam-coach/
├── .env                      # GitHub Personal Access Token
├── .gitignore               # Git除外設定
├── .kiro/
│   ├── settings/
│   │   └── mcp.json         # MCP Server設定（4サーバ）
│   └── steering/
│       ├── project-context.md    # このファイル
│       └── work-log-reference.md # 作業記録参照ルール
├── README.md                # プロジェクト概要
└── WORK_LOG.md             # 作業記録
```

## 作業記録ファイル

プロジェクトルートの `WORK_LOG.md` を参照（構造化済み・目次付き）

## 重要な期限・備考

- GitHub Personal Access Token 期限: 2025 年 10 月頃
- 全 MCP サーバ動作確認済み
