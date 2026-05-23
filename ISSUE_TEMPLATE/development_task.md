---
name: 開発タスク (M層が起票)
about: 機能追加・改善 — M層が要件確定後に起票する作業発注書
labels: enhancement
---

## 経緯

(Slack thread の議論サマリ。なぜこの要件になったか / トレードオフ / 検討した代替案。要件未確定なら起票せず Slack thread で詰める)

## 要件

(確定した実装内容を箇条書きで)

- 

## 受け入れ条件

(Done の定義。テスト可能な記述で。auto-merge ラベル付ける場合はここを満たせば自動マージ)

- [ ] 
- [ ] 

## 影響範囲

(変更対象のファイル・機能・他リポへの影響など、分かる範囲で)

## メタデータ

- 依頼者: <SlackユーザーID or "自発">
- M層: <chief / platform / ba / consulting / thebotch / shift / web / events / sns / spotify>
- Slack thread: <URL or thread_ts>
- 関連 Issue / PR: 

@claude

---

### ラベル運用ガイド

- `auto-merge` を付けると、CI 通過後に自動 squash merge + Issue auto-close されます（軽微変更向け）
- ラベル無しなら、@claude が PR を作成し、M層 / CEO がレビュー後にマージします
- 影響大・要設計判断のものは `auto-merge` を付けないでください
