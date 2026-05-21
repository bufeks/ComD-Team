# ComD Team — Claude 作業コンテキスト

このファイルは、Claude Code セッションが切り替わっても即座に作業を再開できるよう、プロジェクトの全体像・運用ルール・未完了タスクをまとめたものです。

---

## プロジェクト概要

- **組織**: 株式会社kiCk
- **チーム**: Communication Design Team（ComD）
- **目的**: チームメンバー7名の情報をJSON形式で集約し、マネジメントに活用する
- **運用者**: 宮崎太郎（クリエイティブディレクター / チームリーダー）
- **共通目標**: 「全員がプロジェクトの中心人物になる」

---

## Git 運用ルール

- **開発ブランチ**: `claude/team-member-management-DrqoW`
- **リモート**: `bufeks/comd-team`（GitHub MCP 経由でアクセス）
- プッシュは必ず `git push -u origin claude/team-member-management-DrqoW`
- PRは明示的に依頼された場合のみ作成する

---

## ファイル構成

```
ComD-Team/
├── team.json                            # チーム全体インデックス
├── members/
│   ├── member-001_miyazaki-taro.json    # 宮崎太郎（リーダー）
│   ├── member-002_onoma-ryo.json        # 小野間良（サブリーダー・育休中）
│   ├── member-003_suzuki-masaaki.json   # 鈴木雅昭（コピーライター）
│   ├── member-004_sakai-taisei.json     # 坂井大生（コピーライター）
│   ├── member-005_sanai-ayumi.json      # 佐内歩（プランナー）
│   ├── member-006_inagaki-kana.json     # 稲垣香奈（プランナー）
│   └── member-007_furuhashi-ryo.json    # 古橋亮羽（コピーライター・2026年〜）
└── CLAUDE.md                            # このファイル
```

---

## メンバー一覧

| ID | 氏名 | 役割 | 状態 | data_completeness |
|---|---|---|---|---|
| member-001 | 宮崎 太郎 | CD / チームリーダー | active | full |
| member-002 | 小野間 良 | サブリーダー / プランナー | on_leave（育休中） | minimal |
| member-003 | 鈴木 雅昭 | コピーライター | active | minimal |
| member-004 | 坂井 大生 | コピーライター | active | full |
| member-005 | 佐内 歩 | プランナー | active | full |
| member-006 | 稲垣 香奈 | プランナー | active | full |
| member-007 | 古橋 亮羽 | コピーライター（2026年〜） | active | minimal |

---

## CliftonStrengths 34 — 反映状況

PDFレポートから全34資質順位データを各メンバーJSONに反映済み（2026-05-21）。

| メンバー | primary_domain | top5 |
|---|---|---|
| 宮崎太郎（001） | 戦略的思考力 | 着想・未来志向・達成欲・活発性・戦略性 |
| 小野間良（002） | 影響力 | 最上志向・活発性・原点思考・適応性・自我 |
| 坂井大生（004） | 影響力 | 最上志向・親密性・適応性・達成欲・着想 |
| 佐内歩（005） | 影響力 | 最上志向・着想・競争性・達成欲・包含 |
| 古橋亮羽（007） | 戦略的思考力 | 戦略性・親密性・着想・最上志向・分析思考 |

- member-003（鈴木）: 2026-05-21 反映済み（primary_domain=人間関係構築力）
- member-006（稲垣）のPDFは未取得のため未反映

---

## JSONスキーマ — 主要フィールド

各メンバーJSONの`clifton_strengths`フィールド構造：

```json
"clifton_strengths": {
  "primary_domain": "戦略的思考力 | 影響力 | 人間関係構築力 | 実行力",
  "top5": ["資質1", "資質2", "資質3", "資質4", "資質5"],
  "top10": ["..."],      // 任意
  "all34": ["1位", "2位", ..., "34位"],
  "summary": "..."       // 任意
}
```

`data_quality.evaluation_completeness`の値：`full` / `partial` / `minimal`

---

## 未完了タスク（TODO）

### 優先度：高
- [ ] **2026年3月1on1メモの原文展開**（宮崎によるログ）
  - 対象: member-004（坂井）、member-005（佐内）、member-006（稲垣）、member-007（古橋）
  - 原文提供待ち → 提供されたら各JSONの`one_on_ones`に反映

### 優先度：中
- [ ] **member-003（鈴木雅昭）の評価情報充実**
  - CliftonStrengths 34: 反映済み（2026-05-21）
  - 残課題: 2025上期自己評価・ADフィードバック原文が未取得
- [ ] **member-002（小野間良）の復帰後ロール再定義**
  - 育休復帰のタイミングで`status`を`active`に更新
  - 復帰後評価・役割定義を追加

### 優先度：低
- [ ] **member-006（稲垣香奈）のCliftonStrengths反映**（PDFが手元にある場合）
- [ ] `team.json`の`data_pending`リストを更新（1on1メモ展開後に削除）

---

## 参照情報の時点

- 評価コメント・自己評価データ: **2025年12月時点**
- CliftonStrengths 34: **PDFレポートより（取得日不明）**
- 1on1ログ: **2026年3月**

---

## セッション開始時のクイックスタート

新しいセッションで作業を再開する際は、このファイルを読めば即座にコンテキストが復元されます。

具体的な作業に入る前に確認すること：
1. `git status` でブランチと変更状況を確認
2. 対象メンバーのJSONファイルを `Read` ツールで読み込む
3. 変更後は必ずコミット・プッシュ（`claude/team-member-management-DrqoW`ブランチ）
