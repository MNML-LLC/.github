# コントリビューションガイド

MNML-LLC 組織への貢献ありがとうございます。このガイドでは開発フローとルールを説明します。

## 開発フロー

```
Slack（議論） → M層（要件確定） → GitHub Issue（@claude メンション）
  → claude-code-action（自動実装） → PR 作成 → レビュー → マージ
```

1. **Slack で要望を投げる** — CEO が Slack に投稿すると、IF層が M層に振り分けます
2. **M層が要件を確定** — M層が CEO と対話して実装内容を詰めます
3. **M層が Issue を起票** — 要件が固まったら M層が GitHub Issue を作成し `@claude` をメンションします
4. **@claude が自動実装** — claude-code-action 経由で Claude がブランチを作成しコードを書きます
5. **PR が自動作成** — 実装完了後、ワークフローが自動で PR を作成します
6. **レビュー → マージ** — `auto-merge` ラベルあり → CI 通過後に自動マージ。ラベルなし → M層 / CEO がレビューしてマージ

## Issue の書き方

Issue に `@claude` をメンションすると claude-code-action が起動して自動実装します。

```markdown
## 経緯
（なぜこの変更が必要か）

## 要件
- 実装したい内容を箇条書きで

## 受け入れ条件
- [ ] Done の定義

@claude
```

**必須ルール:**
- `@claude` メンションは Issue body の末尾に置く
- 要件は曖昧にしない（「いい感じに」は NG）
- 受け入れ条件を必ず書く（何をもって完了とするかを明確に）

## ラベル運用

| ラベル | 意味 | 動作 |
|--------|------|------|
| `auto-merge` | 軽微な変更。M層レビュー不要 | CI 通過後に自動 squash merge → Issue auto-close |
| `enhancement` | 機能追加 | — |
| `bug` | バグ修正 | — |

**`auto-merge` を付けてよいケース:**
- typo 修正、CLAUDE.md の微調整
- 設定値の変更（影響範囲が明確なもの）
- ドキュメント更新

**`auto-merge` を付けてはいけないケース:**
- 新機能追加・設計変更
- 外部 API・サービスとのインターフェース変更
- 複数リポにまたがる変更

## コミット・PR ルール

- コミットメッセージは英語
- ブランチ名: `claude/issue-<N>-<slug>` （claude-code-action が自動生成）
- PR タイトル: Issue タイトルと一致させる
- `.env`、`.tokens*.json`、credentials 等の機密ファイルはコミットしない
- force push は原則禁止（CEO 承認が必要）

## セキュリティ

脆弱性を発見した場合は、Public な Issue ではなく Slack の適切なチャンネルに報告してください。
