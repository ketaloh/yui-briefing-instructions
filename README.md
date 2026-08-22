# Yui Secretary Channel Instructions

常駐秘書チャンネル解析指示書。GAS（Google Apps Script）から `raw.githubusercontent.com` 経由で参照される。

**2026-08-21 更新**：夜便（ナイトブリーフィング）は全面撤去済み。旧 `nightly_briefing_instruction.md`（夜便生成指示書）は本リポジトリから削除した。現在は秘書チャンネル指示書のみを管理する。

## ファイル

- `secretary_command_instruction.md` — 常駐秘書チャンネル解析指示書（つぶやきメール／実績相手からの受信メールを解析し、予定・ToDo・日程打診の登録可否をJSONで判定する。GAS `processYuiCommands()` / `detectMailAppointments()` が system prompt として使用）

## 参照経路

GAS は以下の raw URL から指示書を取得：

```
https://raw.githubusercontent.com/ketaloh/yui-briefing-instructions/main/secretary_command_instruction.md
```

`UrlFetchApp.fetch()` を使用（認証ヘッダ不要・Public リポジトリのため）。

## 個人情報の扱い

本リポジトリは Public のため、個人情報（氏名・住所・電話番号・メールアドレス等）は一切含まない。半固有情報（地区名・町丁）も汎用化済み。

組織コア（経験ログ・個人情報を含むファイル）は別 Private リポジトリ `ketaloh/claude-organization` で管理。

## 更新運用

指示書の変更は本リポジトリで直接編集し、commit/push で反映する。

## 関連

- 関連 RULE: `~/.claude/rules/RULE_SILENT_FAIL_DETECTION.md`（自動配信運用の正本・§Z にGAS自動送信を統合）
