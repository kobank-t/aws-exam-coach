---
inclusion: always
---

# AWS Exam Coach プロジェクトコンテキスト

## セッション継続性のための必須情報

### プロジェクト基本情報

- **プロジェクト名**: AWS Exam Coach
- **真の目的**: AI エージェント技術スキルアップ + 200 名組織のコミュニケーション活性化
- **対象試験**: AWS Certified Solutions Architect - Professional
- **GitHub**: https://github.com/kobank-t/aws-exam-coach

### 現在のフェーズ・状況

- **開発段階**: Spec 作成ワークフロー - 設計フェーズ
- **完了済み**: 要件定義 (requirements.md)
- **作業中**: 設計書作成 (design.md) - 約 50%完了
- **次回予定**: 設計書完成 → タスクリスト作成

### 確定済み重要決定事項

- **技術方式**: Power Automate + Teams リアクション (A,B,C,D 絵文字)
- **AI 基盤**: Bedrock AgentCore + Strands Agents
- **情報源**: AWS 公式ドキュメント + 試験ガイドのみ (信頼性重視)
- **段階的アプローチ**: 複雑な Teams App 開発を避けシンプル実装

## セッション開始時の必須アクション

1. **WORK_LOG.md 確認**: 前回作業内容と次回予定を把握
2. **設計書確認**: `.kiro/specs/aws-exam-coach/design.md` の進捗状況
3. **継続性維持**: 作業記録に基づく適切なタスク継続

## 作業指針・制約

### 必須ルール

- **日本語回答**: 全ての回答・コミット・ドキュメントは日本語
- **作業記録更新**: 重要作業完了時は WORK_LOG.md 更新必須
- **ファイル参照明示**: ステアリング参照時はファイル名を明記
- **公式情報源のみ**: 非公式 MCP サーバ・情報源は使用禁止

### 開発環境・ツール

- **MCP Server**: 5 つ動作確認済み (Git, AWS Docs, AWS Knowledge, AWS Diagram, AWS Pricing)
- **開発ツール**: uv/uvx, npx 利用可能
- **GitHub**: Personal Access Token 設定済み (期限: 2025 年 10 月)

## プロジェクト構成 (最新)

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
│       ├── project-context.md    # このファイル
│       └── work-log-reference.md # 作業記録参照ルール
├── README.md                # プロジェクト概要
└── WORK_LOG.md             # 作業記録
```

## 重要な学び・原則 (今後の判断基準)

- **ペルソナ明確化**: 利用者像が曖昧だと技術選択を誤る
- **組織課題優先**: 個人学習より組織コミュニケーション活性化が真の価値
- **段階的実装**: 複雑技術より早期リリース可能なシンプル方式を選択
- **信頼性重視**: AWS 公式情報源のみ使用、品質確保を最優先

## 次回セッションでの推奨アクション

1. **WORK_LOG.md 読み込み** → 前回作業内容確認
2. **design.md 確認** → 設計書の進捗・残作業把握
3. **設計書完成** → Teams 連携システム詳細、Data Models、Error Handling、Testing Strategy
4. **ユーザー承認** → 設計書完了後のユーザーレビュー・承認取得

#[[file:WORK_LOG.md]]
