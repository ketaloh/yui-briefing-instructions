# Yui Nightly Briefing Instructions

夜便（ナイトブリーフィング）生成指示書。GAS（Google Apps Script）から `raw.githubusercontent.com` 経由で参照される。

## ファイル

- `nightly_briefing_instruction.md` — 夜便生成の指示書本体（SPEC v5.2 の簡略版・GAS Claude API 呼び出し時の system prompt として使用）

## 参照経路

GAS は以下の raw URL から指示書を取得：

```
https://raw.githubusercontent.com/ketaloh/yui-briefing-instructions/main/nightly_briefing_instruction.md
```

`UrlFetchApp.fetch()` を使用（認証ヘッダ不要・Public リポジトリのため）。

## 個人情報の扱い

本リポジトリは Public のため、個人情報（氏名・住所・電話番号・メールアドレス等）は一切含まない。半固有情報（地区名・町丁）も汎用化済み。

組織コア（経験ログ・個人情報を含むファイル）は別 Private リポジトリ `ketaloh/claude-organization` で管理。

## 更新運用

指示書本体のマスターは `~/.claude/specs/nightly_briefing_instruction.md`（Private リポ側）。Public リポへの反映は手動コピー＋commit/push で行う。月1回程度の見直しタイミングで同期する。

## 関連

- 本家 SPEC: `~/.claude/specs/SPEC_yui_briefing.md` v5.2（Private 側・802行・詳細仕様）
- 関連 RULE: `~/.claude/rules/RULE_GAS_AUTO_SEND.md` / `~/.claude/rules/RULE_SILENT_FAIL_DETECTION.md`
