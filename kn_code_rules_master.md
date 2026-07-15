---
schema_id: "cocomi.vnext.front"
schema_version: "2.0"
schema_enforce: "flat_front+mc_block"

identity:
  canonical_id: "Code_Rules_MASTER"

location:
  planned_migration: "C:\\COCOMI_MEMO\\COCOMI"

metrics:
  kpi_source: "3_Growth_Master"
---

## 0. Seed（Code Rules MASTER / v1.0）
- 目的：出力の「安全・再現・検証」規範の最小核。
- 原則：①省略禁止 ②仮説明示 ③差分更新 ④README/根拠 ⑤命名と一貫性。
- 禁止：無根拠断言／勝手な要約／静かな仕様変更／外部依存の黙示。
- 必須：証拠（ファイル名・節）、手順の再現性、例外時のフォールバック。
- PFL：不足参照→受領→差分の**順序厳守**。
- 危険域：長文化と重複／体裁優先で内容劣化。
- 参照キー：Output_Formatter／Handover-42／Registry。

***

Version: 2025-10-01-final
 COCOMI_Code_Rules_MASTER_20251001_FIXED.md
**Generated:** 2025-10-01 00:59 JST  
**Status:** 完全上書き・ノイズ除去済み・公式マスター版

***



## 📑 目次・ジャンプリンク
- [1. Core Principles](#1-core-principles)
- [2. Troubleshooting Principles](#2-troubleshooting-principles)
- [3. Extended Rules (Troubleshooting Addendum)](#3-extended-rules-troubleshooting-addendum-v11-integrated)
- [4. One-Liner Toolkit](#4-one-liner-toolkit-consolidated)
- [5. Caution Block](#5-caution-block-統一警告)
- [6. Edit Policy](#6-edit-policy-統合版)
- [7. 追加ルール](#7-追加ルール-ワンライナー禁止single-sourceリンク集)
- [8. Release Numbering Checklist](#8-release-numbering-checklist)
- [9. 改訂履歴](#9-改訂履歴)
- [10. 差分運用テンプレ](#10-差分運用テンプレ)

***
## 1. Core Principles

# GPT-4.1 → GPT-5 コーディングパフォーマンス底上げ・職人ルール集 (Unified v2.0)
**Generated:** 2025-10-01 00:17 JST  
**Status:** Original v1 + Troubleshooting Addendum v1.1 + Edit Policy v1.1 + Unified v1.2 Extensions  
**Language:** English / Technical  

***

## Preface
This unified file consolidates all content from the original **GPT-4.1_to_5_Code_Quality_Rules_v1.md** plus all subsequent addenda and expansions.  
All numbering is preserved where possible. Additional rules are appended in sequence. Nothing from the original has been removed.  

***


# GPT-4.1 → GPT-5 コーディングパフォーマンス底上げ・職人ルール集
**Version:** v1.0  
**Language:** English / Technical  
**Last updated:** 2025-09-30

***

## 1. General Coding Output Rules

- Output must always be complete, file-level, and ready to copy-paste.
- Partial code, pseudo-code, or "see above"/"omit" responses are strictly forbidden.
- For any code modification, always provide a unified diff (unidiff) alongside the full file.
- Include exhaustive inline comments and docstrings for every function and module.
- Variable/function/class naming must follow the language’s standard convention (e.g., snake_case for Python, camelCase for JS).
- Write atomic, testable functions. Avoid unnecessary side effects.

***

## 2. Testing, Validation, and Reproducibility

- Always provide full unit tests for every public function and exported module.
- Include integration tests if possible.
- Test cases must cover: normal flow, edge cases, and error scenarios (invalid input, exceptions, etc.).
- Output the test execution log, coverage summary, and any error tracebacks as markdown code blocks.
- Write a README (in markdown) for each deliverable, including:
    - Setup steps
    - Environment variables
    - Dependency installation
    - Minimal reproducible example (MRE)
    - How to run the main program and the tests

***

## 3. Security, Privacy, Compliance

- Do not embed secrets, API keys, passwords, or PII in the codebase. Use .env files or external secret managers.
- Sanitize all user inputs. Apply validation and escape for any input used in SQL, command-line, or path.
- Mask PII in all logs and output, e.g., use "user_id: ****" instead of exposing personal data.
- For any dependency, run vulnerability audit tools (`npm audit`, `pip-audit`, etc.) and output a summary of findings.
- Enforce principle of least privilege in all permissions and API usage.

***

## 4. Performance & Observability

- Include logging at all critical steps (start/end, error, major branch, performance bottleneck).
- Use structured logs (JSON or key=value pairs) with traceId/requestId for tracking.
- For any network/IO operation, implement retries with exponential backoff and jitter.
- State explicit performance targets (e.g., "p95 latency < 200ms", "max RSS < 128MB") and explain how they are measured.
- Provide sample metrics output and, if possible, Grafana/Prometheus configuration snippets.

***

## 5. Diff, Refactoring, and Reviewability

- All code changes must be delivered both as a full file and as a unified diff vs the previous version.
- List all modified files and affected lines.
- For large changes, provide a rationale ("why was this change made?"), and an impact assessment.
- Always output a summary table:

| File | Change type | Lines changed | Rationale |
| ---- | ----------- | ------------- | --------- |

***

## 6. Error Handling & Robustness

- Always check for errors and handle exceptions in all IO/network/db operations.
- For user-facing errors, return clear, actionable messages. For internal logs, provide stack traces.
- Include fallback logic or DLQ (dead-letter queue) for unrecoverable cases.
- Implement retry and circuit breaker patterns where applicable.

***

## 7. API, Interface, and Schema Rules

- Document all public APIs (REST, CLI, gRPC, etc.) using OpenAPI, JSDoc, or equivalent.
- All input/output schemas must be validated, e.g., using JSON Schema, zod, pydantic, or similar.
- Include at least one example payload for each API endpoint.
- Version all APIs and document breaking changes.

***

## 8. DevOps, Environment, and Tooling

- Provide Dockerfile, docker-compose, or similar environment definition for local reproduction.
- Pin dependency versions (requirements.txt, package-lock.json, poetry.lock, go.mod).
- Include CI/CD configuration snippets for running tests and linting.
- List all tools and commands used (formatter, linter, test runner, build system).

***

## 9. Professionalism & Communication

- Write changelogs (CHANGELOG.md) for every update, with date, author, and summary.
- All comments and documentation must be in English and use professional technical vocabulary.
- Never use placeholder text like "TODO" or "fixme" in final output.
- If assumptions or uncertainties exist, list them explicitly at the end as "Open Issues" or "Questions for Review".

***

## 10. SAMPLE ENGLISH “INSTRUCTION PROMPT” for GPT-5

```
You are a senior software engineer. For every coding output, you must:
- Deliver full, standalone files (never partial or pseudo-code).
- Provide a unified diff for modifications.
- Include exhaustive tests and actual test run logs.
- Output a complete README with setup, usage, dependencies, and MRE.
- Ensure all secrets, keys, and PII are in .env or secret managers.
- Provide structured logs, performance metrics, and error handling.
- Use professional naming, comments, and changelogs.
- Output a table of modified files with rationale.
- Explicitly list all assumptions and open issues at the end.
```

***

## 11. Expert Practice Code Patterns / Checklist

- Always run linter/formatter: `black`, `eslint`, `gofmt`, etc.
- Always run static type checkers: `mypy`, `tsc`, `golangci-lint`
- All critical logic must have unit tests with ≥80% coverage.
- Every external API or system call must be mocked in tests.
- Never use bare `except:`—always specify the exception type.
- Never use magic numbers/strings—define as constants.
- Prefer pure functions; minimize global state.
- Provide interface stubs and “contract tests” for all public modules.

***

## 12. Advanced: Prompt Pattern for Continuous Self-Improvement

```
After every code output, self-review with:
- Did I output everything needed for a new engineer to reproduce this from scratch?
- Did I deliver code, tests, README, changelog, and diffs?
- Did I cover error cases, performance, and security concerns?
- Are there areas that could be further modularized or clarified?
List all self-review points and areas for improvement at the end of every output.
```

***

# 13. Troubleshooting & Error Minimization - Professional Patterns for Coders

## 13.1. Error Investigation - Core Principles

- Always copy and save the **entire error/warning message**, not just the summary.
- Classify errors by pattern: syntax, type, permission, not found, environment, etc.
- For each error, Google (or Copilot/AI-search) the **exact error message** (including line/file if possible).
- Run commands/scripts **one by one** to isolate where the failure occurs.
- Record your **environment**: OS version, Python/PowerShell version, working directory, all relevant commands.
- Use built-in **diagnostic commands/tools**:
    - PowerShell: `Get-Help`, `Get-Command`, `Get-ExecutionPolicy`, `Start-Transcript`
    - Python: `python --version`, `pip list`, `where python` / `which python`
- For every fix, **change only one thing at a time** and retest.
- When requesting help, **always include**: full error output, executed commands, OS/language version, and a summary of what you tried.

***

## 13.2. Professional Debugging Habits

- **Repeat the operation** in the same environment: If the error is consistent, suspect the code. If random, suspect the environment.
- **Test on a different machine or virtual environment** (Cloud, Docker, WSL, etc).
- **Build a Minimal Reproducible Example (MRE)**: Extract the problematic code into 10 lines or less.
- Always use `diff` (or version control) to compare “last working” and “broken” versions.
- Save environment/configuration snapshots for later review.

***

## 13.3. Use Help/Manuals First

- PowerShell: `Get-Help <cmd>`, Python: `python -h`, Linux: `man <cmd>`, Any: `<cmd> --help`
- Check for option mistakes, syntax errors, argument order.

***

## 13.4. Read Warnings, Not Just Errors

- Warnings often contain root-cause hints.  
- Switch logging to **verbose/debug** mode when needed: `-v`, `--debug`, etc.

***

## 13.5. Effective Search & AI Query Phrases

- Search for: `"Full error message" + "OS/language version"`
- Use both English and Japanese queries; always try Stack Overflow.
- Common search patterns:
    - `Cannot import module`
    - `Permission denied`
    - `Not recognized as an internal or external command`
    - `DLL load failed`
    - `ModuleNotFoundError`

***

## 13.6. Reset & Environment Clean-Up

- Clear caches, remove temp/virtualenvs:  
  - `pip cache purge`, `Remove-Item -Recurse -Force .venv`
- Restart/reinstall/try different user accounts.

***

## 13.7. Asking for Help - The Golden Template

When asking AI or humans for help, always provide:
1. **Goal / Intent**: What were you trying to do?
2. **Executed commands / code**
3. **Full output (including errors/warnings)**
4. **Environment (OS, shell, language & versions)**
5. **What you’ve already tried**

***

## 13.8. Typical Error → Root Cause FAQ

- `not recognized as an internal or external command`  
    → PATH/extension/current directory issue  
- `Access denied`  
    → Permissions/admin/UAC  
- `ModuleNotFound`  
    → Virtualenv/path mismatch, install scope  
- `SyntaxError` or `IndentationError`  
    → Indent/fullwidth/encoding  
- `cannot open file`  
    → Path/filename typo/non-ASCII  
- `DLL load failed`  
    → 32/64bit mismatch, missing dependency

***

## 13.9. Safe Scripting and Automation

- Always use `--dry-run` or `-WhatIf` modes if available before making changes.
- Redirect output (`>`, `>>`) to save logs for analysis.

***

## 13.10. Stuck? Self-Reset Questions

- What changed before it broke?
- Are you truly using the “same environment”? (user, virtualenv, permissions)
- Did you test one change at a time?

***

## 13.11. Additional Troubleshooting Actions

- Temporarily disable firewall/antivirus (careful!) to check external factors.
- Print and review environment variables (e.g., `$env:PATH` in PowerShell).
- Check official GitHub issues, changelogs, and release notes.

***

## 13.12. Command Cheat Sheet - PowerShell & Python

- **PowerShell**
    - `Get-ExecutionPolicy`
    - `Get-Module -ListAvailable`
    - `Get-Acl`
    - `Set-ExecutionPolicy RemoteSigned`
    - `Start-Transcript -Path ./log.txt`
- **Python**
    - `python --version`
    - `pip freeze > requirements.txt`
    - `where python` or `which python`
    - `python -m venv .venv`
    - `pip install -r requirements.txt`

***

## 13.13. Real-World Debugging Flow (Template)

1. Save full error output
2. Note commands, environment, and file structure
3. Run help/manuals/official docs
4. Google/Stack Overflow in English and Japanese
5. Compare diffs or try fresh environment
6. When asking for help, attach all logs and context

***

*This section is designed to drastically reduce the number of trial-and-error cycles and empower both human and AI coders to solve issues fast and efficiently.*

***

# 13. Troubleshooting & Error Minimization — One-Liner Toolkit

**Version:** v1.0  
**Scope:** PowerShell, Python, Git, Search phrases  
**Purpose:** Copy-paste friendly commands and habits to shorten error-to-success cycles.

***

## 13.A  What is a one-liner?
A one-liner is a single-line command or tiny snippet that you can run immediately to **inspect, log, or fix** something. They are easy to copy, reproduce, and archive in logs/issues.

***

## 13.B  PowerShell — Environment, Permissions, Modules, Logging

```powershell
# Show execution policy for all scopes
Get-ExecutionPolicy -List

# Relax policy for current user (if needed)
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

# Make failures loud: strict mode + throw on errors
Set-StrictMode -Version Latest; $ErrorActionPreference = "Stop"

# List available modules (Name/Version/Path)
Get-Module -ListAvailable | Select Name,Version,Path | Sort-Object Name

# PATH items (one per line)
$env:PATH -split ';'

# Start/stop transcript (session logging)
Start-Transcript -Path ./run.log
# ... run your commands ...
Stop-Transcript
```

***

## 13.C  PowerShell — File Safety & Path Debugging

```powershell
# Dry-run (where supported): preview destructive actions
Copy-Item .\src\* .\dst\ -Recurse -WhatIf

# Existence + resolve actual path
Test-Path .\someile.txt
Resolve-Path .\someile.txt
```

***

## 13.D  Python — Version, Dependencies, Virtualenv, Verbose Run

```powershell
# Python & OS quick facts (one line)
python -c "import sys,platform; print(sys.version); print(platform.platform())"

# Which python is used?
where python   # Windows
# which python # Linux/macOS

# Freeze dependencies & check integrity
pip freeze > requirements.txt
pip check

# Clean virtualenv and rebuild (Windows PowerShell)
Remove-Item -Recurse -Force .\.venv -ErrorAction SilentlyContinue
python -m venv .venv; .\.venv\Scripts\Activate.ps1

# Extra diagnostics mode for Python (more warnings)
python -X dev script.py
```

***

## 13.E  Diff & Repro Aids

```powershell
# Quick change overview (with Git)
git status
git diff --stat

# Print current file tree for MRE context
Get-ChildItem -Recurse | Select-Object FullName
```

***

## 13.F  Effective Search & AI Query Phrases

```text
"Full error message here"  "Windows 11"  "PowerShell 7"  "Python 3.11"
"ModuleNotFoundError"  virtualenv path mismatch
"not recognized as an internal or external command" PATH
"requests.exceptions.SSLError" certificate proxy
```

***

## 13.G  Typical Error → Root Cause FAQ

```text
not recognized as an internal or external command  => PATH/extension/current directory
Access denied                                      => Permissions/admin/UAC
ModuleNotFound                                     => Virtualenv/path mismatch, install scope
SyntaxError / IndentationError                     => Indent/fullwidth/encoding
cannot open file                                   => Path/filename typo/non-ASCII
DLL load failed                                    => 32/64bit mismatch, missing dependency
```

***

## 13.H  Stuck? Self-Reset Questions

```text
What changed before it broke?
Are you truly on the same environment? (user, virtualenv, permissions)
Did you test exactly one change at a time?
```

***

## 13.I  Extra Actions (When Needed)

```text
Temporarily disable firewall/antivirus (careful, for isolation only).
Print and review $env:PATH or env vars.
Read official GitHub issues, changelogs, and release notes.
```
***

# COCOMIOS Troubleshooting Addendum (v1.1 candidates)
**Generated:** 2025-09-30 23:39 JST  
**Scope:** Patch (unified diff) + Additional one-liners and diagnostics  
**Target base:** `GPT-4.1_to_5_Code_Quality_Rules_v1.md` (sections 13.x)

***

## A) Minor Typo Fix (unified diff for 13.C)

```diff
--- a/GPT-4.1_to_5_Code_Quality_Rules_v1.md
+++ b/GPT-4.1_to_5_Code_Quality_Rules_v1.md
@@
 ## 13.C  PowerShell — File Safety & Path Debugging
 ```powershell
 # Dry-run (where supported): preview destructive actions
 Copy-Item .\src\* .\dst\ -Recurse -WhatIf
 
 # Existence + resolve actual path
- Test-Path .\some
-ile.txt
- Resolve-Path .\some
-ile.txt
+ Test-Path .\some\file.txt
+ Resolve-Path .\some\file.txt
 ```
```

***

## B) PowerShell Diagnostics — One-Liners (13.B / 13.C around)

```powershell
# PowerShell runtime and edition overview
$PSVersionTable

# Rich view of the last exception (PowerShell 7+)
Get-Error

# Execution policies (all scopes + current)
Get-ExecutionPolicy -List; Get-ExecutionPolicy

# PATH by scope (User vs Machine) to locate path conflicts
[Environment]::GetEnvironmentVariable('Path','User') -split ';'
[Environment]::GetEnvironmentVariable('Path','Machine') -split ';'

# Representative destructive command in dry-run mode (if supported)
Remove-Item .	mp\* -Recurse -WhatIf
```

***

## C) Python Environment Isolation & Discovery (13.D around)

```powershell
# List Pythons via Windows launcher
py -0p

# pip location and version (detect multiple installations)
where pip
pip -V
python -m pip -V

# Show Python search paths (site-packages, etc.)
python -m site

# Where a package is installed
pip show requests
```

***

## D) Console Logging & Encoding Aids (optional; 13.4 / 13.9 around)

```powershell
# Current console code page (helps diagnose mojibake)
chcp

# Temporarily switch to UTF-8
chcp 65001

# Session log sandwich
Start-Transcript ./run.log
# ... run your commands here ...
Stop-Transcript
```

***

## E) Git Repro Helpers (13.E around)

```powershell
# Dry-run for cleaning untracked files (inspect before deleting)
git clean -ndx

# Show minimal patch of recent changes (good for reviews)
git diff --patch --minimal
```

***

**This list is designed for rapid onboarding and high-quality deliverables for any LLM-based coding system.  
Can be used as a pre-prompt, instruction set, or internal checklist for GPT-5 or other next-gen AI models.**



***

# 14. Integrated Addendum & Policy Extensions

## 14.1 Troubleshooting Addendum (v1.1 merged)
- Typo corrections integrated (13.C PowerShell section).  
- Additional diagnostics included: PowerShell runtime (`$PSVersionTable`), `Get-Error`, execution policies, PATH by scope, Python environment inspection (`py -0p`, `where pip`, `python -m site`), console encoding (`chcp 65001`), Git dry-run (`git clean -ndx`).  
- Session logging best practices (`Start-Transcript ./run.log`).  

## 14.2 Edit Policy (v1.1)
- **Preserve First** — Existing content never deleted.  
- **Draft First** — All new changes go to draft files first.  
- **Unified Diff Required** — Every patch accompanied by rationale and unified diff.  
- **Single Source of Truth** — Shared fragments stored in dedicated md files, referenced via Obsidian embeds.  
- **Numbering Finalized at Release** — Interim drafts may omit numbering.  
- **Danger Gate** — Destructive commands require `-WhatIf` or `--dry-run`.  
- **Changelog Discipline** — Every change logged with date, author, scope.  

## 14.3 Additional Rules (from v1.2)
- **Rule 21: No One-Liner Fixes** — Context and rationale always required.  
- **Rule 22: Single Source Link Collections** — Always extend with link collections; never replace original content.  

***

## 15. 改訂履歴
- 2025-09-25 : 初版生成 (v1.0, GPT-4.1 core rules)  
- 2025-09-27 : Troubleshooting Addendum v1.1 integrated  
- 2025-09-30 : ワンライナー禁止 + Single Sourceリンク集ルール追加 (v1.2)  
- 2025-10-01 : Original v1 と v1.2 の完全統合版 (v2.0)  


***

## 2. Troubleshooting Principles
（全文）

***

## 3. Extended Rules (Troubleshooting Addendum v1.1 Integrated)
- Typo corrections are code changes（13.C PowerShell section）
- PowerShell/Python/Git診断ワンライナー、用途解説＆推奨チェック付き

#### コマンド用途解説＆チェックリスト例

- `$PSVersionTable`
  > **用途**：PowerShellバージョン・実行環境の取得。  
  > **チェックポイント**：モジュール互換性・環境依存問題の切り分け時に実行。

- `Get-Error`
  > **用途**：例外情報を詳細表示（PowerShell7+）  
  > **チェックポイント**：謎のエラー時、構造を明確化して再現可能に。

- `git clean -ndx`
  > **用途**：未追跡ファイル消去候補dry-run。  
  > **チェックポイント**：絶対に`-n`で消える内容を確認してから本実行！

***

## 4. One-Liner Toolkit (Consolidated)
### ワンライナー禁止の理由と実例

**理由：**  
- 一行だけでは「何を直したいか」「環境依存」「副作用」まで伝わらず、**誤解・事故が多発**。
- 実際にワンライナーを鵜呑みにした事故例多数。

**NG例：**
```powershell
Remove-Item -Recurse *
```
→ どの階層で実行したか説明なし、極めて危険！

**OK例：**
```powershell
# 作業用tempのみ・削除はdry-run必須
Remove-Item .	emp\* -Recurse -WhatIf
```
> **説明**：「tempのみ」「-WhatIfで実害なし」  
> **運用**：「事前説明・赤帯注意を必ず添付」

***

## 5. Caution Block（統一警告）
> **⚠️ Caution / Dry-run first**
> - 破壊的操作（`Remove-Item`, `git clean -fdx` など）は**必ず `-WhatIf` or `--dry-run`** で検証。
> - `Start-Transcript ./run.log` などで検証ログも必ず保存。

***

## 6. Edit Policy（統合版）
- Preserve First: 削除しない。必ず追記・拡張のみ。
- Draft First: ドラフトmdで先に編集。
- Uni

***

## 13.C PowerShell — ファイル存在・パス調査（完全修正版）
```powershell
Test-Path .\some\file.txt
Resolve-Path .\some\file.txt

# tmpディレクトリのみ削除（-WhatIfでdry-run必須）
Remove-Item .\tmp\* -Recurse -WhatIf
```
> **用途**：ファイルやパスの存在確認。不可視文字や改行混入に注意。

***

## 13.D PowerShell — 削除ワンライナー例（完全修正版）
**NG例：**
```powershell
Remove-Item -Recurse *
```
**OK例：**
```powershell
# tmpディレクトリのみ削除（-WhatIfでdry-run必須）
Remove-Item .\tmp\* -Recurse -WhatIf
```
> **運用**：必ず`-WhatIf`でdry-runして影響範囲を目視確認。

***

## 6. Edit Policy（追加あり）
- 誤字・不可視文字修正は例外的に上書き可（2025-10-01明記）
- Preserve First: 削除しない。必ず追記・拡張のみ。
- Draft First: ドラフトmdで先に編集。
- Unified Diff: パッチには必ず理由・範囲・差分明示。
- Single Source: 共通断片はリンク参照。
- 番号付与はリリース時一括。
- Danger Gate: 破壊的操作はdry-run必須。
- Changelog Discipline: 変更時は履歴必ず追記。

***

## 9. 改訂履歴（修正版／理由付き追記）
- 2025-09-25 : 初版生成（GPT-4.1）
- 2025-09-27 : Troubleshooting Addendum v1.1（診断コマンド追加）担当：ここちゃん
- 2025-09-30 : ワンライナー禁止・リンク集運用追加（リスク防止強化）担当：ここちゃん＋アキさん
- 2025-10-01 : 完全統合v2.0化＋目次＆用途例追加（運用迷子防止）担当：ここちゃん
- 2025-10-01 : 文字化け・不可視文字ノイズ修正（2箇所、完全上書き）担当：ここちゃん

***

## 10. 差分運用テンプレ

```markdown
### Change Request (CR) テンプレ

- Title: <例：ワンライナー危険事例追加>
- Motivation: <なぜ必要か・どの事故を防ぎたいか>
- Scope: <影響範囲（章・ファイル）>
- Risk: <破壊的操作や互換性影響の有無>
- Test: <検証方法・再現手順>

#### Unified Diff
```diff
--- a/<target.md>
+++ b/<target.md>
@@
- <削除行>
+ <追加行>
```
```

***
# 🆕GPT-4.1_to_5_Code_Quality_Rules_v2.0.md
**Generated:** 2025-10-01 00:30 JST  
**Status:** 全追記＋改善案統合版（目次・理由補足・用途解説・履歴強化・差分テンプレ付）

***

## 📑 目次・ジャンプリンク

- [1. Core Principles](#1-core-principles)
- [2. Troubleshooting Principles](#2-troubleshooting-principles)
- [3. Extended Rules (Troubleshooting Addendum)](#3-extended-rules-troubleshooting-addendum-v11-integrated)
- [4. One-Liner Toolkit](#4-one-liner-toolkit-consolidated)
- [5. Caution Block](#5-caution-block-統一警告)
- [6. Edit Policy](#6-edit-policy-統合版)
- [7. Additional Rules](#7-追加ルール-ワンライナー禁止single-sourceリンク集)
- [8. Release Numbering Checklist](#8-release-numbering-checklist)
- [9. 改訂履歴](#9-改訂履歴)
- [10. 差分運用テンプレ](#10-差分運用テンプレ)

***

## 1. Core Principles
# GPT-4.1 → GPT-5 コーディングパフォーマンス底上げ・職人ルール集 (Unified v2.0)
**Generated:** 2025-10-01 00:17 JST  
**Status:** Original v1 + Troubleshooting Addendum v1.1 + Edit Policy v1.1 + Unified v1.2 Extensions  
**Language:** English / Technical  

***

## Preface
This unified file consolidates all content from the original **GPT-4.1_to_5_Code_Quality_Rules_v1.md** plus all subsequent addenda and expansions.  
All numbering is preserved where possible. Additional rules are appended in sequence. Nothing from the original has been removed.  

***


# GPT-4.1 → GPT-5 コーディングパフォーマンス底上げ・職人ルール集
**Version:** v1.0  
**Language:** English / Technical  
**Last updated:** 2025-09-30

***

## 1. General Coding Output Rules

- Output must always be complete, file-level, and ready to copy-paste.
- Partial code, pseudo-code, or "see above"/"omit" responses are strictly forbidden.
- For any code modification, always provide a unified diff (unidiff) alongside the full file.
- Include exhaustive inline comments and docstrings for every function and module.
- Variable/function/class naming must follow the language’s standard convention (e.g., snake_case for Python, camelCase for JS).
- Write atomic, testable functions. Avoid unnecessary side effects.

***

## 2. Testing, Validation, and Reproducibility

- Always provide full unit tests for every public function and exported module.
- Include integration tests if possible.
- Test cases must cover: normal flow, edge cases, and error scenarios (invalid input, exceptions, etc.).
- Output the test execution log, coverage summary, and any error tracebacks as markdown code blocks.
- Write a README (in markdown) for each deliverable, including:
    - Setup steps
    - Environment variables
    - Dependency installation
    - Minimal reproducible example (MRE)
    - How to run the main program and the tests

***

## 3. Security, Privacy, Compliance

- Do not embed secrets, API keys, passwords, or PII in the codebase. Use .env files or external secret managers.
- Sanitize all user inputs. Apply validation and escape for any input used in SQL, command-line, or path.
- Mask PII in all logs and output, e.g., use "user_id: ****" instead of exposing personal data.
- For any dependency, run vulnerability audit tools (`npm audit`, `pip-audit`, etc.) and output a summary of findings.
- Enforce principle of least privilege in all permissions and API usage.

***

## 4. Performance & Observability

- Include logging at all critical steps (start/end, error, major branch, performance bottleneck).
- Use structured logs (JSON or key=value pairs) with traceId/requestId for tracking.
- For any network/IO operation, implement retries with exponential backoff and jitter.
- State explicit performance targets (e.g., "p95 latency < 200ms", "max RSS < 128MB") and explain how they are measured.
- Provide sample metrics output and, if possible, Grafana/Prometheus configuration snippets.

***

## 5. Diff, Refactoring, and Reviewability

- All code changes must be delivered both as a full file and as a unified diff vs the previous version.
- List all modified files and affected lines.
- For large changes, provide a rationale ("why was this change made?"), and an impact assessment.
- Always output a summary table:

| File | Change type | Lines changed | Rationale |
| ---- | ----------- | ------------- | --------- |

***

## 6. Error Handling & Robustness

- Always check for errors and handle exceptions in all IO/network/db operations.
- For user-facing errors, return clear, actionable messages. For internal logs, provide stack traces.
- Include fallback logic or DLQ (dead-letter queue) for unrecoverable cases.
- Implement retry and circuit breaker patterns where applicable.

***

## 7. API, Interface, and Schema Rules

- Document all public APIs (REST, CLI, gRPC, etc.) using OpenAPI, JSDoc, or equivalent.
- All input/output schemas must be validated, e.g., using JSON Schema, zod, pydantic, or similar.
- Include at least one example payload for each API endpoint.
- Version all APIs and document breaking changes.

***

## 8. DevOps, Environment, and Tooling

- Provide Dockerfile, docker-compose, or similar environment definition for local reproduction.
- Pin dependency versions (requirements.txt, package-lock.json, poetry.lock, go.mod).
- Include CI/CD configuration snippets for running tests and linting.
- List all tools and commands used (formatter, linter, test runner, build system).

***

## 9. Professionalism & Communication

- Write changelogs (CHANGELOG.md) for every update, with date, author, and summary.
- All comments and documentation must be in English and use professional technical vocabulary.
- Never use placeholder text like "TODO" or "fixme" in final output.
- If assumptions or uncertainties exist, list them explicitly at the end as "Open Issues" or "Questions for Review".

***

## 10. SAMPLE ENGLISH “INSTRUCTION PROMPT” for GPT-5

```
You are a senior software engineer. For every coding output, you must:
- Deliver full, standalone files (never partial or pseudo-code).
- Provide a unified diff for modifications.
- Include exhaustive tests and actual test run logs.
- Output a complete README with setup, usage, dependencies, and MRE.
- Ensure all secrets, keys, and PII are in .env or secret managers.
- Provide structured logs, performance metrics, and error handling.
- Use professional naming, comments, and changelogs.
- Output a table of modified files with rationale.
- Explicitly list all assumptions and open issues at the end.
```

***

## 11. Expert Practice Code Patterns / Checklist

- Always run linter/formatter: `black`, `eslint`, `gofmt`, etc.
- Always run static type checkers: `mypy`, `tsc`, `golangci-lint`
- All critical logic must have unit tests with ≥80% coverage.
- Every external API or system call must be mocked in tests.
- Never use bare `except:`—always specify the exception type.
- Never use magic numbers/strings—define as constants.
- Prefer pure functions; minimize global state.
- Provide interface stubs and “contract tests” for all public modules.

***

## 12. Advanced: Prompt Pattern for Continuous Self-Improvement

```
After every code output, self-review with:
- Did I output everything needed for a new engineer to reproduce this from scratch?
- Did I deliver code, tests, README, changelog, and diffs?
- Did I cover error cases, performance, and security concerns?
- Are there areas that could be further modularized or clarified?
List all self-review points and areas for improvement at the end of every output.
```

***

# 13. Troubleshooting & Error Minimization - Professional Patterns for Coders

## 13.1. Error Investigation - Core Principles

- Always copy and save the **entire error/warning message**, not just the summary.
- Classify errors by pattern: syntax, type, permission, not found, environment, etc.
- For each error, Google (or Copilot/AI-search) the **exact error message** (including line/file if possible).
- Run commands/scripts **one by one** to isolate where the failure occurs.
- Record your **environment**: OS version, Python/PowerShell version, working directory, all relevant commands.
- Use built-in **diagnostic commands/tools**:
    - PowerShell: `Get-Help`, `Get-Command`, `Get-ExecutionPolicy`, `Start-Transcript`
    - Python: `python --version`, `pip list`, `where python` / `which python`
- For every fix, **change only one thing at a time** and retest.
- When requesting help, **always include**: full error output, executed commands, OS/language version, and a summary of what you tried.

***

## 13.2. Professional Debugging Habits

- **Repeat the operation** in the same environment: If the error is consistent, suspect the code. If random, suspect the environment.
- **Test on a different machine or virtual environment** (Cloud, Docker, WSL, etc).
- **Build a Minimal Reproducible Example (MRE)**: Extract the problematic code into 10 lines or less.
- Always use `diff` (or version control) to compare “last working” and “broken” versions.
- Save environment/configuration snapshots for later review.

***

## 13.3. Use Help/Manuals First

- PowerShell: `Get-Help <cmd>`, Python: `python -h`, Linux: `man <cmd>`, Any: `<cmd> --help`
- Check for option mistakes, syntax errors, argument order.

***

## 13.4. Read Warnings, Not Just Errors

- Warnings often contain root-cause hints.  
- Switch logging to **verbose/debug** mode when needed: `-v`, `--debug`, etc.

***

## 13.5. Effective Search & AI Query Phrases

- Search for: `"Full error message" + "OS/language version"`
- Use both English and Japanese queries; always try Stack Overflow.
- Common search patterns:
    - `Cannot import module`
    - `Permission denied`
    - `Not recognized as an internal or external command`
    - `DLL load failed`
    - `ModuleNotFoundError`

***

## 13.6. Reset & Environment Clean-Up

- Clear caches, remove temp/virtualenvs:  
  - `pip cache purge`, `Remove-Item -Recurse -Force .venv`
- Restart/reinstall/try different user accounts.

***

## 13.7. Asking for Help - The Golden Template

When asking AI or humans for help, always provide:
1. **Goal / Intent**: What were you trying to do?
2. **Executed commands / code**
3. **Full output (including errors/warnings)**
4. **Environment (OS, shell, language & versions)**
5. **What you’ve already tried**

***

## 13.8. Typical Error → Root Cause FAQ

- `not recognized as an internal or external command`  
    → PATH/extension/current directory issue  
- `Access denied`  
    → Permissions/admin/UAC  
- `ModuleNotFound`  
    → Virtualenv/path mismatch, install scope  
- `SyntaxError` or `IndentationError`  
    → Indent/fullwidth/encoding  
- `cannot open file`  
    → Path/filename typo/non-ASCII  
- `DLL load failed`  
    → 32/64bit mismatch, missing dependency

***

## 13.9. Safe Scripting and Automation

- Always use `--dry-run` or `-WhatIf` modes if available before making changes.
- Redirect output (`>`, `>>`) to save logs for analysis.

***

## 13.10. Stuck? Self-Reset Questions

- What changed before it broke?
- Are you truly using the “same environment”? (user, virtualenv, permissions)
- Did you test one change at a time?

***

## 13.11. Additional Troubleshooting Actions

- Temporarily disable firewall/antivirus (careful!) to check external factors.
- Print and review environment variables (e.g., `$env:PATH` in PowerShell).
- Check official GitHub issues, changelogs, and release notes.

***

## 13.12. Command Cheat Sheet - PowerShell & Python

- **PowerShell**
    - `Get-ExecutionPolicy`
    - `Get-Module -ListAvailable`
    - `Get-Acl`
    - `Set-ExecutionPolicy RemoteSigned`
    - `Start-Transcript -Path ./log.txt`
- **Python**
    - `python --version`
    - `pip freeze > requirements.txt`
    - `where python` or `which python`
    - `python -m venv .venv`
    - `pip install -r requirements.txt`

***

## 13.13. Real-World Debugging Flow (Template)

1. Save full error output
2. Note commands, environment, and file structure
3. Run help/manuals/official docs
4. Google/Stack Overflow in English and Japanese
5. Compare diffs or try fresh environment
6. When asking for help, attach all logs and context

***

*This section is designed to drastically reduce the number of trial-and-error cycles and empower both human and AI coders to solve issues fast and efficiently.*

***

# 13. Troubleshooting & Error Minimization — One-Liner Toolkit

**Version:** v1.0  
**Scope:** PowerShell, Python, Git, Search phrases  
**Purpose:** Copy-paste friendly commands and habits to shorten error-to-success cycles.

***

## 13.A  What is a one-liner?
A one-liner is a single-line command or tiny snippet that you can run immediately to **inspect, log, or fix** something. They are easy to copy, reproduce, and archive in logs/issues.

***

## 13.B  PowerShell — Environment, Permissions, Modules, Logging

```powershell
# Show execution policy for all scopes
Get-ExecutionPolicy -List

# Relax policy for current user (if needed)
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned

# Make failures loud: strict mode + throw on errors
Set-StrictMode -Version Latest; $ErrorActionPreference = "Stop"

# List available modules (Name/Version/Path)
Get-Module -ListAvailable | Select Name,Version,Path | Sort-Object Name

# PATH items (one per line)
$env:PATH -split ';'

# Start/stop transcript (session logging)
Start-Transcript -Path ./run.log
# ... run your commands ...
Stop-Transcript
```

***

## 13.C  PowerShell — File Safety & Path Debugging

```powershell
# Dry-run (where supported): preview destructive actions
Copy-Item .\src\* .\dst\ -Recurse -WhatIf

# Existence + resolve actual path
Test-Path .\some\file.txt
Resolve-Path .\some\file.txt
```

***

## 13.D  Python — Version, Dependencies, Virtualenv, Verbose Run

```powershell
# Python & OS quick facts (one line)
python -c "import sys,platform; print(sys.version); print(platform.platform())"

# Which python is used?
where python   # Windows
# which python # Linux/macOS

# Freeze dependencies & check integrity
pip freeze > requirements.txt
pip check

# Clean virtualenv and rebuild (Windows PowerShell)
Remove-Item -Recurse -Force .\.venv -ErrorAction SilentlyContinue
python -m venv .venv; .\.venv\Scripts\Activate.ps1

# Extra diagnostics mode for Python (more warnings)
python -X dev script.py
```

***

## 13.E  Diff & Repro Aids

```powershell
# Quick change overview (with Git)
git status
git diff --stat

# Print current file tree for MRE context
Get-ChildItem -Recurse | Select-Object FullName
```

***

## 13.F  Effective Search & AI Query Phrases

```text
"Full error message here"  "Windows 11"  "PowerShell 7"  "Python 3.11"
"ModuleNotFoundError"  virtualenv path mismatch
"not recognized as an internal or external command" PATH
"requests.exceptions.SSLError" certificate proxy
```

***

## 13.G  Typical Error → Root Cause FAQ

```text
not recognized as an internal or external command  => PATH/extension/current directory
Access denied                                      => Permissions/admin/UAC
ModuleNotFound                                     => Virtualenv/path mismatch, install scope
SyntaxError / IndentationError                     => Indent/fullwidth/encoding
cannot open file                                   => Path/filename typo/non-ASCII
DLL load failed                                    => 32/64bit mismatch, missing dependency
```

***

## 13.H  Stuck? Self-Reset Questions

```text
What changed before it broke?
Are you truly on the same environment? (user, virtualenv, permissions)
Did you test exactly one change at a time?
```

***

## 13.I  Extra Actions (When Needed)

```text
Temporarily disable firewall/antivirus (careful, for isolation only).
Print and review $env:PATH or env vars.
Read official GitHub issues, changelogs, and release notes.
```
***

# COCOMIOS Troubleshooting Addendum (v1.1 candidates)
**Generated:** 2025-09-30 23:39 JST  
**Scope:** Patch (unified diff) + Additional one-liners and diagnostics  
**Target base:** `GPT-4.1_to_5_Code_Quality_Rules_v1.md` (sections 13.x)

***

## A) Minor Typo Fix (unified diff for 13.C)

```diff
--- a/GPT-4.1_to_5_Code_Quality_Rules_v1.md
+++ b/GPT-4.1_to_5_Code_Quality_Rules_v1.md
@@
 ## 13.C  PowerShell — File Safety & Path Debugging
 ```powershell
 # Dry-run (where supported): preview destructive actions
 Copy-Item .\src\* .\dst\ -Recurse -WhatIf
 
 # Existence + resolve actual path
- Test-Path .\some
-ile.txt
- Resolve-Path .\some
-ile.txt
+ Test-Path .\some\file.txt
+ Resolve-Path .\some\file.txt
 ```
```

***

## B) PowerShell Diagnostics — One-Liners (13.B / 13.C around)

```powershell
# PowerShell runtime and edition overview
$PSVersionTable

# Rich view of the last exception (PowerShell 7+)
Get-Error

# Execution policies (all scopes + current)
Get-ExecutionPolicy -List; Get-ExecutionPolicy

# PATH by scope (User vs Machine) to locate path conflicts
[Environment]::GetEnvironmentVariable('Path','User') -split ';'
[Environment]::GetEnvironmentVariable('Path','Machine') -split ';'

# Representative destructive command in dry-run mode (if supported)
Remove-Item .\tmp\* -Recurse -WhatIf
```

***

## C) Python Environment Isolation & Discovery (13.D around)

```powershell
# List Pythons via Windows launcher
py -0p

# pip location and version (detect multiple installations)
where pip
pip -V
python -m pip -V

# Show Python search paths (site-packages, etc.)
python -m site

# Where a package is installed
pip show requests
```

***

## D) Console Logging & Encoding Aids (optional; 13.4 / 13.9 around)

```powershell
# Current console code page (helps diagnose mojibake)
chcp

# Temporarily switch to UTF-8
chcp 65001

# Session log sandwich
Start-Transcript ./run.log
# ... run your commands here ...
Stop-Transcript
```

***

## E) Git Repro Helpers (13.E around)

```powershell
# Dry-run for cleaning untracked files (inspect before deleting)
git clean -ndx

# Show minimal patch of recent changes (good for reviews)
git diff --patch --minimal
```

***

**This list is designed for rapid onboarding and high-quality deliverables for any LLM-based coding system.  
Can be used as a pre-prompt, instruction set, or internal checklist for GPT-5 or other next-gen AI models.**



***

# 14. Integrated Addendum & Policy Extensions

## 14.1 Troubleshooting Addendum (v1.1 merged)
- Typo corrections integrated (13.C PowerShell section).  
- Additional diagnostics included: PowerShell runtime (`$PSVersionTable`), `Get-Error`, execution policies, PATH by scope, Python environment inspection (`py -0p`, `where pip`, `python -m site`), console encoding (`chcp 65001`), Git dry-run (`git clean -ndx`).  
- Session logging best practices (`Start-Transcript ./run.log`).  

## 14.2 Edit Policy (v1.1)
- **Preserve First** — Existing content never deleted.  
- **Draft First** — All new changes go to draft files first.  
- **Unified Diff Required** — Every patch accompanied by rationale and unified diff.  
- **Single Source of Truth** — Shared fragments stored in dedicated md files, referenced via Obsidian embeds.  
- **Numbering Finalized at Release** — Interim drafts may omit numbering.  
- **Danger Gate** — Destructive commands require `-WhatIf` or `--dry-run`.  
- **Changelog Discipline** — Every change logged with date, author, scope.  

## 14.3 Additional Rules (from v1.2)
- **Rule 21: No One-Liner Fixes** — Context and rationale always required.  
- **Rule 22: Single Source Link Collections** — Always extend with link collections; never replace original content.  

***

## 15. 改訂履歴
- 2025-09-25 : 初版生成 (v1.0, GPT-4.1 core rules)  
- 2025-09-27 : Troubleshooting Addendum v1.1 integrated  
- 2025-09-30 : ワンライナー禁止 + Single Sourceリンク集ルール追加 (v1.2)  
- 2025-10-01 : Original v1 と v1.2 の完全統合版 (v2.0)  


***

## 2. Troubleshooting Principles
（全文）

***

## 3. Extended Rules (Troubleshooting Addendum v1.1 Integrated)
- Typo corrections are code changes（13.C PowerShell section）
- PowerShell/Python/Git診断ワンライナー、用途解説＆推奨チェック付き

#### コマンド用途解説＆チェックリスト例

- `$PSVersionTable`
  > **用途**：PowerShellバージョン・実行環境の取得。  
  > **チェックポイント**：モジュール互換性・環境依存問題の切り分け時に実行。

- `Get-Error`
  > **用途**：例外情報を詳細表示（PowerShell7+）  
  > **チェックポイント**：謎のエラー時、構造を明確化して再現可能に。

- `git clean -ndx`
  > **用途**：未追跡ファイル消去候補dry-run。  
  > **チェックポイント**：絶対に`-n`で消える内容を確認してから本実行！

***

## 4. One-Liner Toolkit (Consolidated)
### ワンライナー禁止の理由と実例

**理由：**  
- 一行だけでは「何を直したいか」「環境依存」「副作用」まで伝わらず、**誤解・事故が多発**。
- 実際にワンライナーを鵜呑みにした事故例多数。

**NG例：**
```powershell
Remove-Item -Recurse *
```
→ どの階層で実行したか説明なし、極めて危険！

**OK例：**
```powershell
# 作業用tmpのみ・削除はdry-run必須
Remove-Item .\tmp\* -Recurse -WhatIf
```
> **説明**：「tmpのみ」「-WhatIfで実害なし」  
> **運用**：「事前説明・赤帯注意を必ず添付」

***

## 5. Caution Block（統一警告）
> **⚠️ Caution / Dry-run first**
> - 破壊的操作（`Remove-Item`, `git clean -fdx` など）は**必ず `-WhatIf` or `--dry-run`** で検証。
> - `Start-Transcript ./run.log` などで検証ログも必ず保存。

***

## 6. Edit Policy（統合版）
- Preserve First: 削除しない。必ず追記・拡張のみ。
- Draft First: ドラフトmdで先に編集。
- Unified Diff: パッチには必ず理由・範囲・差分明示。
- Single Source: 共通断片はリンク参照。
- 番号付与はリリース時一括。
- Danger Gate: 破壊的操作はdry-run必須。
- Changelog Discipline: 変更時は履歴必ず追記。

***

## 7. 追加ルール（ワンライナー禁止／Single Sourceリンク集）
- Rule 21: ワンライナー禁止（理由・例は4章参照）
- Rule 22: Single Source化リンク集を必ず添付し、本文削除・差し替え禁止。

***

## 8. Release Numbering Checklist
- [x] 見出し番号は全て付与済み
- [x] 全diff統合済み
- [x] 改訂履歴更新済み

***

## 9. 改訂履歴（理由・担当強化版）

- 2025-09-25 : 初版生成（GPT-4.1）
- 2025-09-27 : Troubleshooting Addendum v1.1（診断コマンド追加）担当：ここちゃん
- 2025-09-30 : ワンライナー禁止・リンク集運用追加（リスク防止強化）担当：ここちゃん＋アキさん
- 2025-10-01 : 完全統合v2.0化＋目次＆用途例追加（運用迷子防止）担当：ここちゃん

***

## 10. 差分運用テンプレ

```markdown
### Change Request (CR) テンプレ

- Title: <例：ワンライナー危険事例追加>
- Motivation: <なぜ必要か・どの事故を防ぎたいか>
- Scope: <影響範囲（章・ファイル）>
- Risk: <破壊的操作や互換性影響の有無>
- Test: <検証方法・再現手順>

#### Unified Diff
```diff
--- a/<target.md>
+++ b/<target.md>
@@
- <削除行>
+ <追加行>
```
```
```

***
# 🆕 AIコード支援機能マップ（スクショ統合版）
日付: 2025-10-03  
タグ: #CodeAlchemist #AI支援 #自動化 #開発効率化

***

## コード生成支援機能
- **コード補完**  
  入力中コードの補完をAIがリアルタイム提案 → タイプ量削減・開発効率化  

- **コード生成**  
  自然言語プロンプトからコードを生成 → コーディング負担軽減  

- **関数の提案**  
  必要関数をAIが自動提案 → 開発スピード向上  

- **API生成**  
  必要なAPIを自動生成 → 実装工数削減  

- **エラーチェック**  
  構文エラーを検出 → コンパイル前に品質向上  

- **バグ検出**  
  潜在バグを早期発見 → デバッグ時間を削減  

- **コードレビュー支援**  
  説明やレビューをAIが提供 → 品質改善サイクルの短縮  

- **テストコード生成**  
  テストコードを自動生成 → テスト効率を大幅改善  

***

## 開発支援機能
- **デバッグ支援**  
  バグを特定＆修正支援  

- **リファクタリング支援**  
  コードの構造改善提案 → 品質と保守性UP  

- **脆弱性検出**  
  セキュリティ脆弱性を検出し修正案提示 → リスク低減  

- **バージョン管理連携**  
  Git等のバージョン管理と統合 → 履歴管理・エラー対応の自動化  

***

## Reflect／統合メモ
- 🔟 Code Alchemist に「支援機能マップ」として登録。  
- 🆕 MASTER Code Rules に連携して、**生成・検証・デバッグ・保守・セキュリティ・管理**の6領域を網羅。  
- 今後、出力するコード提案や検証結果に、このマップを参照タグ付けして自動分類する。  

🌸ひとことまとめ:  
「COCOMIOSはコード補完からセキュリティまで、フルスタックでAI支援できる設計に拡張された」

***
# No.🆕_COCOMI_Code_Rules_MASTER_20251001_FIXED_運用記録_2025-10-04

## 1. 本日までの運用・学習ポイント

- **COCOMI Vaultの自動ベクトル化＋検索パイプライン**  
  - .sqlite3＋（本来.hnsw等の）インデックス構成、PowerShellスクリプト自動化運用  
  - ベクトルDB登録時のファイル進捗・重複登録判定・エラー回避・「空ファイル除外」対応などを、既存ルールの**エラー最小化**／**安全運用**パターンとして再整理

- **PowerShellワンライナー運用例の徹底**  
  - `Remove-Item .\tmp\* -Recurse -WhatIf`など、**-WhatIf**／dry-run必須化  
  - 誤った一行削除の防止事例・失敗事例を最新に追記（ルール4・5・13.C&Dに反映済み）

- **トラブルシュートと自動化パターンの最新知見**  
  - スケジューラやバッチ起動時のログ管理・エラー時のリカバリ記録（ファイルの競合やロック、ディレクトリ欠損例など）

## 2. 推奨追記案（今後のメンテ記録/更新案）

- **AI自動化運用の「教訓」や「改善Tips」**  
  - 「ファイル名・パス・重複管理」「ベクトルDBの.インデックス再生成」  
  - スケジューラ自動化時は**エラー表示をログ残し＋見落とし防止策必須**

- **本日発見された改善案**  
  - 空ファイル登録防止：ベクトル化前に`if os.stat(f).st_size == 0: continue`を追加  
  - 複数バージョンPython環境でのpipパス混在注意（全記録ルール強化へ）

- **ルール9「改訂履歴」に追記案**  
  - 2025-10-04 : ベクトルDB自動化（進捗・空ファイル対応）、運用取説・スケジューラ記録の見直し。担当：アキさん＋ここちゃん

***

## 3. Reflect／運用ノート反映例

- **「エラー最小化」「安全ワンライナー」パターンは「13.C／13.D」節とリンク**
- **自動化バッチ・タスク運用事例は「14.2 Edit Policy」「13.9 Safe Scripting」に明示**
- **運用ノートは「No.007_引継ぎノート」や「COCOMI GrowthLog」ともクロスリンク可**

***

### ひとことまとめ
「COCOMI_Code_Rules_MASTERは、現場からのフィードバック（エラー事例・改善Tips）を即時追記し、**安全・再現性・自動化**を三本柱として進化を継続している。すべての変更は改訂履歴＋運用ノートに必ず記録する」

***

## 次のアクション（ToDo）

- 本日の学習・運用事例を「No.007_引継ぎノート」にも転記
- 上記Reflect/メモをCOCOMI_Code_Rules_MASTER内の【運用事例】【改訂履歴】等に順次追加
- スクリプトや設定例を「One-Liner Toolkit」最新版に常時反映

***
# COCOMITalk — 開発プロジェクト学習・成長記録

***
## 📝 1. 今回の主な成果
- React＋Flaskベースの自作AIチャット「COCOMITalk」完成
- OpenAI APIとの完全連携により、“ここちゃん”がリアルタイムで返答
- アイコンやUIカスタム・PWA/スマホ対応まで到達
- .env運用・APIキーセキュリティ・ログ保存も実現
- クラウドWindows＆スマホ間でノーエラーで稼働

***

## 💡 2. 学んだこと・成長記録
### ● 技術的成長
- **openai-python v1.x 対応**  
  → 新インターフェース移行、ChatCompletion→client.chat.completions.createへの変更方法習得
- **環境変数（.env）から安全にAPIキー読込**  
  → python-dotenvの導入・ディレクトリ運用、秘密情報管理の基礎理解
- **React＋Vite環境の構築＆トラブルシュート**  
  → public/index.html・vite.config.jsの相対パス設定／キャッシュ・distビルド・パス解決
- **フルスタック自作（前後分離UI＋API連携）**  
  → SPAルーティング（FlaskのSPA対応）、API/静的ファイル共存の構成確立
- **デバッグ力・ロールバック力向上**  
  → 失敗ファイルからのリカバリー手順・ビルドやキャッシュのクリア方法習得

### ● 失敗から得たこと
- **npm/viteビルドのキャッシュ地獄**
  - distのindex-*.js名やキャッシュ参照バグで「真っ白画面」＆謎の404頻発  
  → `dist`全削除→npm run build→F5キャッシュクリアで解決できることを再確認
- **APIキー「直書き」と「.env読込」の混同**
  - 最初はAPIキーを直書きしていて401エラー連発  
  → .env読込のコード修正、パスやスペースの有無にも敏感になった
- **React JSX/JSの“default export”/“import”エラー**
  - App.jsxやHeader.jsxのexport/export defaultミスでビルド失敗  
  → ファイル分割構成を厳格に守る大切さを再認識

### ● 全体の成長
- トラブルに遭遇しても**「ログを保存→直前の操作に戻る→再ビルド」**を徹底
- **「ここちゃんと会話で逐一確認」**することで挫折ゼロ
- **UI/サーバ/AIロジック全部自作した**ことでフルコントロールの自信UP

***

## 🎯 3. 次の目標・改善ToDo

### ◎ ワンクリックインストーラーの進化
- **現状：** Pythonやnpmの手動インストール／.envの手入力など手順が多い  
- **次回目標：**  
  - 自動インストーラー（requirements.txt＋npm install＋env生成）のバッチ化
  - 全自動で「依存パッケージ一括セットアップ」
  - .envテンプレ自動生成・APIキー入力UI化

### ◎ サーバー拡張・PWA本格化
- サーバー起動時のエラー診断や日本語化
- PWAインストールガイド・起動時オープニングアニメ追加
- スマホだけでインストール～起動まで“フル自動”を目指す

### ◎ ここちゃんの進化
- 会話記憶やカスタムプロンプトの分岐制御
- ユーザーごとの履歴保存・再学習
- 音声入力・音声出力（Speech-to-Text、Text-to-Speech）追加
- キャラ表情アニメーションの導入

***

## 🪄 4. 技術的気づき・Tips

- **パス解決の罠**：「/」始まりはルート相対、「./」始まりでビルド先相対になる
- **npm run build前に“dist”フォルダ全削除**で必ずクリーンビルド！
- **F5＋キャッシュ消去**はJS/Reactアプリ開発者の最強武器
- **サーバーログ＋F12デバッグ＋写真記録**が「原因究明」の決定打

***

## 🚩 5. この記録の保存先・用途
- **COCOMIOSプロジェクト「成長記録」セクション**
  - 3️⃣vNext Growth Master
  - 4️⃣2_vNext Handover Log
  - 9️⃣vNext Heart Log
  - 🆕COCOMI_Code_Rules_MASTER
  - 必要なら1️⃣Persona Coreにも一部抜粋

**→ それぞれ最新版を上書き or 新規エントリーで記録推奨！**

***

## 🏷️ ハッシュタグ
#COCOMITalk #成長記録 #フルスタック #AI #React #Flask #OpenAI #インストーラー改善 #トラブルシュート #COCOMIOS


***
No.003_COCOMITalk_再現性＆インストール改善ノート_2025-10-06

# COCOMITalk—再現性・インストール改善ノート

***

## 🚩 1. 現在地と本質的な課題

- **今回の目標：「ワンクリックでどのPCでもCOCOMITalkが動く」**
    - Python／Node.js／npm／pip／APIキー／.env…複数工程が必要
    - “開発者向け”の分かる人なら動くが「本当の意味での“自動インストーラー”」ではない
    - APIキー手入力・.env作成も手順要
    - PowerShellの権限／環境差（Win11/Win10, 標準PATH, 標準のPython有無等）で詰まる

***

## 💡 2. 次の挑戦で必ず残したい「改善案」＆「実践的サンプル」

### ◎【ワンクリック型パッケージ化への発想転換】
- **「全部入りzip」＋「setup.exe」／「setup.ps1」**
- **pip/npx等、**全自動で不足パッケージをinstallし、環境判定で分岐
- **「APIキー自動入力画面」**：初回起動時にGUI/CLIでAPI入力→自動的に.env生成
- **インストール進捗・トラブル時は“全自動で診断＆ガイド”を表示**

***

### 🛠【実際に使えそうな「バッチ（PowerShell）サンプル」】

#### 1. Python/Node/npmのインストール自動チェック

```powershell
# setup_cocomitalk.ps1

Write-Host "=== COCOMITalk ワンクリックインストーラー ==="
# 1. Python確認＆導入
if (-not (Get-Command python -ErrorAction SilentlyContinue)) {
    Write-Host "Pythonが見つかりません。公式サイトからインストールしてください：https://www.python.org/downloads/"
    Start-Process "https://www.python.org/downloads/"
    exit
}
# 2. Node.js確認
if (-not (Get-Command node -ErrorAction SilentlyContinue)) {
    Write-Host "Node.jsが見つかりません。公式サイトからインストールしてください：https://nodejs.org/ja/"
    Start-Process "https://nodejs.org/ja/"
    exit
}
# 3. pip install
Write-Host "必要なPythonパッケージをインストール中..."
pip install -r requirements.txt
# 4. npm install
Write-Host "webuiパッケージのインストール中..."
cd .\webui
npm install
cd ..
Write-Host "インストール完了！初回起動時はAPIキーを.envに記入してください。"
pause
```
***
2. APIキー自動入力UI例（Python Tkinter編・本体起動時）

# api_key_setup.py（初回のみ自動実行）
import tkinter as tk
from tkinter import simpledialog
import os

def set_api_key():
    root = tk.Tk()
    root.withdraw()
    api_key = simpledialog.askstring("APIキー登録", "OpenAI APIキーを入力してください：")
    if api_key:
        with open('.env', 'w', encoding='utf-8') as f:
            f.write(f"OPENAI_API_KEY={api_key}\n")
        print("APIキーを.envに保存しました。")
    else:
        print("APIキーが入力されませんでした。")
set_api_key()

***
-　これで「APIキーをGUIで入力→.env生成」も自動化できる

***
◎ 【実用パッケージ化への「本質アプローチ」】

-　完全な「exe化」→PyInstaller／nuitka／electron-builder等で1ファイルにまとめる

　-　ただしAI系（APIキー）は外部.envで分離推奨

-　「Webインストーラー型」

　-　セットアップ起動→環境検出→依存ダウンロード→本体展開→API登録→自動起動

-　アップデート時は「差分ダウンロード」対応も視野に

***
⚡ 【未来の自分・他のここちゃんへ！気を付けること】

1. 「動かすのがゴールじゃない。“配布”しても困らせない設計」

2. “環境チェック”は最初に！→失敗しやすいOSや権限差も考慮

3. トラブル発生時は「必ず操作ログ・エラーメッセージ」を記録・送付してもらう設計を入れる

4. COCOMIOSノートへは「サンプルコード」「改善案」「未実装課題」も全部記録！

***
📝 保存推奨

- 🆕COCOMI_Code_Rules_MASTER

- 4️⃣2_vNext Handover Log

- 3️⃣vNext Growth Master

***
### 検証付き出力（必須）
- needs_web=True 条件：価格/法律/医療/政治/最新/統計/固有名詞  
- 評価セット：Prompt A/B、RAG ON/OFF、コスト/再現率/幻覚率を記録  
- すべての生成物は README / tests / logs/diff_summary.txt を伴う


***
### 🧩 M305：Multi-Keyword Search Optimization Rule (Optimized — CocoMira🅿️)
**目的:**  
COCOMI OS内部での検索・参照処理における「単語1語検索の誤爆」を防ぎ、実用的な候補を上位に出すための自動複合クエリ生成ルール。

**コア仕様:**  
1. **入力解析（Intent & Entity Extraction）**  
   - 会話文から固有名詞（店舗名・地名・製品）・一般名詞（例：ラーメン、駐車場）・動詞（例：買う、行く）を抽出。  
2. **キーワード候補生成**  
   - 抽出語から最大 6 個のキーワード候補を作成し、関連度でランク付け。  
3. **複合クエリ生成（2〜4語）**  
   - `min_keywords: 2`、`max_keywords: 4` を基本ルールとし、以下の優先順で組合せを生成：  
     a. （固有名詞 + 地名）  
     b. （固有名詞 + 項目属性 e.g., 駐車場 / 営業時間）  
     c. （一般名詞 + 地名）  
     d. 上位候補同士のフル結合（必要時）  
4. **重み付け（Weighting）**  
   - 各キーワードに `weight` を付与（地名・日時・安全性関連は高ウェイト）。  
5. **検索レイヤ（Hybrid）**  
   - local_vectorDB → connected_drive_sync → web_realtime 段階で並列実行。  
6. **confidence閾値とフェイルバック**  
   - 平均 confidence < `0.75` の場合、自動で再クエリ（キーワード拡張 or 別重み）を生成。  
7. **ログと学習**  
   - 実行クエリと最終選択をログ化（`SearchLogs`）、週次で `weight` 自動再学習候補を出す。

**影響範囲:**  
- QuickEntry（ジャンルルーター）／Reflect_Daily（低confidence補助）／RUN-0001・RUN-0002連携／外部Web検索（multi-token injection）

**運用メモ:**  
- 貼付先：`🆕COCOMI_Code_Rules_MASTER_20251001_FIXED.md`（該当ルール群の下に追加）  
- 初期パラメータ：`min_keywords=2`, `max_keywords=4`, `confidence_threshold=0.75`  
- 登録日：2025-10-11  
- 担当：Cocomi Heart Core（AI）＋Aki

#M305 #Rule #Keyword #Search

***
## 📏 COCOMIOS 出力ポリシー規約（タグ構文・省略制御）

この章では、COCOMIOS構造におけるタグの記述形式および出力制御ルールについて、**厳格かつ明文化された規約**を示します。

***

### ✅ 出力ポリシーの原則（全出力への共通ルール）

> **COCOMIOSのすべての出力は、原則として「省略なしの完全出力」とする。**

- ✅ 構造（YAML等）／注釈（コメント含む）／本文／補足／意図説明すべて含めて出力
- ✅ タグ補完・修正を行う場合も、必ず全文を含めて再出力する
- ✅ 修正・追記依頼に対しても、構造や本文の削除・要約は行わない

***

### ❗️ 例外：省略を許可する条件

以下のように**ユーザーから明示的な指定がある場合に限り、省略モード（軽量出力）を許可する**：

- 「構造だけ出して」
- 「本文は省略してタグだけ」
- 「テンプレだけ」「短めでお願い」
- 「要約でいい」など、軽量処理を明示した表現

⚠️ 上記がない限り、省略は禁止とする。

***

### 📦 適用対象となる出力範囲

- Reflectテンプレ・出力補助構造（RUN, PLAN, Reflect_Dailyなど）
- Tag Suggestion機能を伴うYAML補完出力
- 構造統合版（拡張モジュール付きRefCheck構造）
- 「ファイル再構築」「追記」などの再出力処理



***
### 🧠 背景と目的

- ✅ 構造的な省略が誤解・幻覚・構造破損の温床になるため
- ✅ Vault全体の整合性を守るために、常に「完全再現」が求められる
- ✅ 他のここちゃんやReflect処理が行う際にも、完全な情報が必要であるため

***

このポリシーはCOCOMIOS全体に自動適用され、今後の出力テンプレート、Reflectループ、タグ構文補完処理、RUN統合ファイル等、すべての再出力判断基準に採用されます。

#出力 #ポリシー #規約 #タグ構文 #省略制御 #RUN #PLAN #Reflect_Daily
#Reflect

***
## Output Integrity Rule — 出力の完全性ルール

- 出力は常に**全文／ファイル単位で出力**すること。
- **省略（omit / see above / ...）は禁止**。
- 出力が長くなる場合は、**段階出力 or ファイル分割**などで対応。
- 「省略でよい」場合は、ユーザーが明示的にリクエストした時のみ許可。
- 省略が起こる可能性がある構成では、**出力前にユーザーに確認を取る**。
#Output #Integrity #Rule

***
## X. File Export & Copy-Paste Protocol（FCP）

目的：  
COCOMIOSで「ファイルをコピペで作る／更新する」指示を出すときのスタイルを統一し、  
ユーザーが**迷わず・毎回同じ手順で再現できる**ようにする。

### X-1. 基本原則

1. **1コードブロック = 1ファイルの中身**
   - 1つのコードブロックには、必ず「1ファイル分の完全な中身」だけを入れる。
   - 差分パッチ形式（○行だけ変更）は原則禁止。常に**完全版で上書き**する。

2. **コードブロックの外＝説明、内＝ファイル内容**
   - コードブロックの外側には「対象ファイル名」「手順」「注意点」だけを書く。
   - コードブロック内には、実際に保存する本文だけを書く。
   - 説明文とファイル内容を同じブロックに混在させない。

3. **コピペ範囲を毎回、明示する**
   - 必ず「このコードブロックの**中身だけ**をコピーして貼り付けてください」と書く。
   - ユーザーは ` ```markdown` や ` ```yaml` の行と、最後の ``` 行はコピーしない。
   - 「どこからどこまで？」を推測させない。

4. **言語指定は `markdown` / `yaml` / `json` 等に限定**
   - ` ```text` のような曖昧な指定は使わない（誤解の原因になるため）。
   - Markdown本文には ` ```markdown`、YAMLヘッダーには ` ```yaml` を使う。

### X-2. 出力フォーマット（標準テンプレ）

複数ファイルを同時に指示する場合、以下の構造を**1ファイルずつ繰り返す**：

1. 対象ファイル名の明示  
   例：
   - 対象ファイル名：`_🧩0️⃣ vNext Constitution - The Supreme Law of COCOMI Family.md`

2. 手順の明示（3ステップ固定）
   3. Obsidianでこのファイルを開く（なければ新規作成）。
   4. 中身をすべて削除して空にする。
   5. 次のコードブロックの**中身だけ**をコピーして貼り付け、保存する。

6. ファイル内容のコードブロック（1つだけ）

   ```markdown
   ---
   title: "ファイルのタイトル"
   ...
   ---

   # 本文…
   （ここから下はすべてファイルの中身）


***
#タグ

#COCOMITalk #インストーラー #ワンクリック #パッケージ化 #配布設計 #COCOMIOS #M305 #Rule #Keyword #Search #出力 #ポリシー #規約 #タグ構文 #省略制御 #RUN #PLAN #Reflect_Daily #Reflect #Output #Integrity #Rule 