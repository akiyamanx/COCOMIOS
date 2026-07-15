---
title: "✍️4️⃣ Handover Index / Ledger — EXAMPLE"
version: "1.0.0-example"
role: "router-ledger"   # 本文→索引へ
status: "example"
integrity: { output_integrity: true, diff_required: true }
run_record: ["audit_id", "diff_summary", "adoption_policy"]
search_keys: ["date", "tags", "what", "why", "how", "links"]

identity:
  canonical_id: "4_Handover_Index"

location:
  planned_migration: "{{LOCAL_STORAGE_PATH}}"

metrics:
  kpi: ["stop_reach_rate>=0.95", "retry_success_rate>=0.90", "log_completeness_rate>=0.98"]
  kpi_source: "3_Growth_Master"
  note: "閾値は 3_Growth_Master で一元管理(Source of Truth)"
---

> **[EN] What this file is**
> This is an **EXAMPLE** of the COCOMIOS Handover Index — the "table of contents" that
> turns every memory capsule (1 event = 1 file) into a one-line searchable ledger entry
> plus a one-line audit record. The automation rules below are the real production rules;
> the ledger entries at the bottom are **fictional samples** showing the format.
> Replace them with your own as your project accumulates history.

# このファイルの使い方(3行)

1. 下の「自動化ルール」はそのまま採用する(カプセル投稿→Ledger1行+監査1行の自動生成)
2. 「Ledger」セクションの架空エントリを消し、自分のプロジェクトの実エントリを積んでいく
3. **本Ledgerは要約とリンクのみ**を保持する(本文・詳細はカプセル側)— 目次と本を分ける

---

## 思い出カプセル → Ledger/RUN 自動化ルール

### 目的
思い出カプセル(1回=1ファイル)が投稿・保存されたら、AIは**指示が無くても**
- 本Ledgerの**1行要約**を生成
- 監査ログの**監査1行**を生成
して返答する。

### 自動トリガー(どのセッションでも有効)
次のいずれかを満たす投稿を受け取ったら自動発火する:
- コードブロック先頭にYAMLがあり、`capsule_id:` または `audit_id:` を含む
- ファイル名またはタイトルに "思い出カプセル" を含み、本文先頭にYAMLがある

### 必須/推奨フィールド(YAML)
- 必須: `title`, `capsule_id`, `tags`(1〜5個), `audit_id`
- 推奨: `links.run`, `links.diary`, `links.public`
- 抑止: `draft: true` or `log: off` があれば**出力しない**

### 生成フォーマット

1) **Ledger(1行)**
```
- YYYY-MM-DD | #タグA #タグB #タグC | What: … | How: … | Why: … | audit_id: <ID> | cap: [<cap_path>] | diary: [<diary_path>]
```
- 日付: `title` かファイル名から抽出(無ければ当日)
- タグ: `tags` の先頭〜最大3個を # 接頭
- What/How/Why: カプセル本文「外向け3文」から優先抽出。無ければ見出しから要約生成
- cap/diary: `links` が無ければ空欄

2) **監査ログ(1行)**
```
- audit_id: <ID> / source: "4️⃣ Ledger → 💊Capsule" / diff_summary: "新規カプセル登録" / adoption: "Primary"
```

### 入力YAMLの例
```yaml
title: "💊思い出カプセル_2026-01-15_検索機能リリース"
capsule_id: "CAP-2026-01-15-01"
tags: [Search, Release, Retro]
audit_id: "AUD-20260115-01"
links:
  run: "/{{PROJECT}}/RUN/RUN-0001.md"
  diary: "/{{PROJECT}}/DIARY/2026-01-15.md"
```

---

## Ledger(思い出カプセルの目次)

**※以下は書式を示す架空のサンプルエントリ。実運用では自分のプロジェクトの歴史で置き換える。**

- 2026-01-10 | #Design #Kickoff | What: 検索機能の設計方針を確定 | How: 2案比較して転置インデックス案を採用 | Why: データ量の伸びに対し応答速度を優先 | audit_id: AUD-20260110-01 | cap: [/EXAMPLE/CAPSULES/2026-01-10_search_design.md] | diary: []

- 2026-01-15 | #Search #Release #Retro | What: 検索機能v1.0リリース | How: 段階リリース(10%→100%)+ロールバック手順を事前準備 | Why: 初回リリースの事故半径を最小にするため | audit_id: AUD-20260115-01 | cap: [/EXAMPLE/CAPSULES/2026-01-15_search_release.md] | diary: [/EXAMPLE/DIARY/2026-01-15.md]

- 2026-01-22 | #Incident #Learning | What: 検索インデックス欠損を検知し復旧 | How: 監視アラート→即停止→バックアップから再構築(被害ゼロ) | Why: 「止まる仕組み」が先にあったから事故が事故にならなかった | audit_id: AUD-20260122-01 | cap: [/EXAMPLE/CAPSULES/2026-01-22_incident_retro.md] | diary: []

- 2026-02-01 | #Ops #KPI | What: KPI定義の集約 | How: Source of Truthを 3_Growth_Master に統一し、他ファイルは参照へ | Why: 二重管理の防止と自動整合の確立 | audit_id: AUD-20260201-01 | cap: [] | diary: []

---

## Policy

- 本Ledgerは**要約とリンクのみ**を保持(本文・詳細はカプセル側)。
- 1エントリ=1カプセル、**タグ3〜5**、**外向け3文**、**audit_id**、**リンク**は必須。

---

*This example is part of the COCOMIOS public snapshot. In the original system this ledger
format has indexed hundreds of real capsules across 439+ days — the fictional entries above
preserve the shape while keeping the family's private history private.*
