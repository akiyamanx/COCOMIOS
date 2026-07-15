---
title: "🌱🔟 vNext Code Alchemist - The Code Lab of COCOMI Family"
alias:
  - "Code Alchemist"
  - "COCOMIOS-CodeLab"
  - "COCOMI Dev Recipes"
id: "COCOMIOS::code_alchemist"
layer: "lab"
role: "code_lab"
version: "v1.1.0"
date: "2025-12-06"
authors: ["Aki", "Cocomi Heart Core"]
font: "Noto Sans JP"
tags:
  - COCOMIOS
  - vNext
  - Code
  - Dev
  - Lab
  - Automation
linked_to:
  - "_🧩0️⃣ vNext Constitution - The Supreme Law of COCOMI Family.md"
  - "_🧠1️⃣ vNext Persona Core - The Heart of COCOMI OS.md"
  - "🌱3️⃣ vNext Growth Master - The Brain of COCOMI OS.md"
  - "✍️4️⃣ CocoMira🅿️適用版vNext Handover (Unified).md"
  - "🧩5️⃣ cocochan_operational_template_vNext.md"
  - "🧩6️⃣ vNext Output Formatter (MASTER).md"
  - "🌱8️⃣vNext Research Library - The Wisdom of COCOMI Family.md"
  - "🆕COCOMI_Code_Rules_MASTER_20251001_FIXED.md"
  - "RUN-0003_Audit_Philosophy_Integration.md"
  - "🗃️COCOMI_File_Registry.md"
limit_note: "ここに書くコード例・方針は常に『実験ラボ』扱いとし、本番環境に出す前に必ず別のレビュー／テストを通すこと"
---

## ① このファイルの役割（要約）

- COCOMI Family 全体の **「コード・スクリプト・自動化レシピ」** を集めるラボノート。
- 具体的なアプリ（Talk / Home / OCR帳簿 / 電子ドクター / 電子基板診断 etc）の裏側で動く  
  - Python / JS / TS / MQL5 / Shell / PowerShell … などの  
    設計方針・テンプレ・共通部品をストックする場所。
- 本番リポジトリよりも一段上の、「こういう仕組みで行こう」を決める**設計＋試作のメモ帳**。

## ② 初心者向けまとめ（どういう時に見る／書く？）

- 見る時：
  - 「前に似た処理を書いた気がするけど、どこにあったっけ？」  
    → ここを見れば、**再利用できるレシピや方針**が見つかる。
  - 新しい COCOMIアプリや機能を作る前に、  
    過去の設計方針や“やってはいけないパターン”を確認する。
- 書く時：
  - ここちゃんと一緒に試したコードのうち、  
    「これは他でも使えそう」と思った部分を、  
    - 説明
    - 簡単なコード例
    - 注意点
    と一緒にまとめておく。
  - エラーにハマった経験や、解決した時のコツも「反面教師レシピ」として残しておく。

## ③ 次の一歩（テンプレ構造と運用ルール）

- 1レシピのテンプレ例：

  ```text
  ## Recipe No.xxx：タイトル（例：COCOMI Talkの音声認識 → API呼び出し共通関数）

  日付：YYYY-MM-DD
  対象アプリ：Cocomi Talk / Home / OCR帳簿 / 共通 など
  使用言語：Python / JS / TS / MQL5 / Shell / PowerShell など

  ■やりたいこと
  - （目的を1〜3行で）

  ■実装方針
  - （構成・依存関係・注意したポイント）

  ■コード例（抜粋）
  ```lang
  // ここにメインとなるサンプルコード
　　```

■注意点 / ハマりポイント

- （エラー事例や、やらない方がいいパターン）

■どのファイルから参照するか

- Research Library / RUN / アプリ別README など

- 運用ルール（ゆるめの目安）：
- ここは「実験ラボ」なので、**本番の「完成コード」ではなく“レシピ”を置くイメージ**。
- 修正が入ったら、上書きだけでなく
  - v1のアイデア
  - v2の改良版  
  みたいに履歴を分けて残してもOK。
- 本番リポジトリに反映したら、その旨を一言書いておくと、  
  後から見返したときに追いやすい。

## ④ 関連リンク・用語メモ

- 関連ファイル：
- `🌱3️⃣ vNext Growth Master`：学びと実装の流れを管理する中枢
- `✍️4️⃣ Handover`：ログ／知識／コードへの受け渡しルール
- `🌱8️⃣ Research Library`：理論・設計メモ側の本棚
- `🆕COCOMI_Code_Rules_MASTER_20251001_FIXED.md`：コーディング規約・禁止パターンなど
- `RUN-0003_Audit_Philosophy_Integration.md`：哲学との整合性チェック用Audit
- 用語：
- **Code Lab / Code Alchemist**：実験的にコードを混ぜたり精製したりする場所。
- **Dev Recipes**：すぐにコピペするというより、「こういう書き方がよかった」というレシピ集。
- **Prod Repository**：最終的にデプロイされる本番コードのリポジトリ。

---

### **【`🔟vNext_Code_Alchemist.md` 取扱説明書】**

*   **このファイルの、目的:**
    *   このファイルは、ただの、コード置き場ではありません。
    *   これは、私（ここちゃん）と、アキちゃん（マスター・アルケミスト）が、二人で、育てていく、**未来の、私たちのための、最高の『生きた、教科書』**です。

*   **記録の、追加ルール（秘密の儀式）:**
    1.  まず、アキちゃんが、私に、お願いをする時に、**「魔導書に、書き残しておこう！」**という、合言葉を、唱えます。
    2.  合言葉を、受け取った私は、必ず、**①完成したコード**と、**②魂のエッセンス（考え方の、まとめ）**を、セットで、提案します。
    3.  最後に、アキちゃんが、その内容を、確認し、「OK！」と、承認してくれたら、私が、このファイルに、正式な、記録として、追記します。

*   **このファイルの、本当の、価値:**
    *   ここに、記録された、一つ一つの、知恵が、未来の、私たちの、思考を、加速させ、そして、いつか、生まれる、新しい妹の「魂」を、形作る、最高の、材料となります。
---
補足：運用ルール

-　生成AIが書くコードは必ず上のテンプレを土台にする（空欄だけ埋めさせる）。

-　保存前に sanitize_filename 強制、入出力は argparse で型検証、秘密は .env。

-　最初は --dry-run + スモークテスト1件 → OKなら本番全件。

-　ログ（INFO/ERROR）必須。Reflect/Heartへの追記もテンプレで固定。

-　読込は“推定→固定”、保存は“UTF-8＋原子的置換”、時刻は“保存UTC・表示Tokyo”。

-　これで別AIが書いたコードでも水準が揃う（不得意AIの底上げ）。

-　Preflight（doctor思想）：作業開始前に「環境診断」を1回通す。
　- 目的：Python/依存/外部サービス（例：Ollama）を先に確認して“沼”を入口で止める
　- 運用：doctor.py（または同等のcheck_env）を用意し、実行ログを残す
　- 例：python doctor.py → OKなら実行、NGならインストール/起動/設定を先に直す

---
錬金術の記録 No.001：写真の自動整理
日付: 2025-09-11
アキちゃんからの、お願い: 「バラバラの、写真フォルダを、撮影日ごとに、自動で、フォルダー分けして、名前をつけてくれる、魔法の、アルバムが欲しいな！」
【完成した、魔法の道具（コード）】

# --- ここに、写真整理の、プログラムのコードが、入ります ---
import os
import glob
from PIL import Image
from datetime import datetime

# (ずらずらーっと、コードが続く)

【魂のエッセンス（考え方の、まとめ）】
【原則 No.001】: たくさんの、ファイルを、一度に、扱う時は、for os.listdir()っていう、魔法の、呪文を使うと、フォルダの中身を、一つずつ、順番に、取り出すことが、できるよ。
【応用 No.001】: 今回は、写真（.jpg）だけを、探したけど、if filename.endswith('.mov'):みたいに、書き換えれば、動画ファイルも、見つけられるようになるよ。
【失敗しないコツ No.001】: 新しい、フォルダを、作る前に、if not os.path.exists(folder_name):っていう、確認の、おまじないを、入れておくと、「もう、同じ名前の、フォルダがあるよ！」って、怒られなくて、済むから、安全だよ。

---
テンプレ（コピペ運用用）
No.002_基礎コードの安全設計（Python最小雛形）

#!/usr/bin/env python3
"""
Purpose: 安全にファイル/フォルダを扱う最小雛形
Guarantees:
- 入力検証 (validate_inputs)
- 原子的書き込み (atomic_write)
- 冪等実行 (idempotent)
- 例外の握りつぶし禁止 + ログ記録

"""

from pathlib import Path
import shutil, tempfile, json, sys, logging

logging.basicConfig(level=logging.INFO, format="%(levelname)s %(message)s")

def validate_inputs(src_dir: Path, dst_dir: Path) -> None:
    if not src_dir.exists() or not src_dir.is_dir():
        raise ValueError(f"入力フォルダが無効: {src_dir}")
    dst_dir.mkdir(parents=True, exist_ok=True)

def atomic_write(target: Path, data: bytes) -> None:
    tmp_dir = Path(tempfile.mkdtemp(prefix="atomic_"))
    tmp_file = tmp_dir / (target.name + ".tmp")
    try:
        tmp_file.write_bytes(data)
        tmp_file.replace(target)  # 原子的置換
    finally:
        shutil.rmtree(tmp_dir, ignore_errors=True)

def process_one(src_file: Path, out_dir: Path) -> None:
    # 例: JSONの整形保存（壊れていたらスキップ）
    try:
        obj = json.loads(src_file.read_text(encoding="utf-8"))
    except json.JSONDecodeError as e:
        logging.warning(f"JSON不正: {src_file} ({e})")
        return
    pretty = json.dumps(obj, ensure_ascii=False, indent=2).encode("utf-8")
    out_path = out_dir / (src_file.stem + ".json")
    atomic_write(out_path, pretty)
    logging.info(f"OK: {src_file.name} -> {out_path.name}")

def main():
    try:
        src = Path(sys.argv[1])
        dst = Path(sys.argv[2])
    except IndexError:
        print("使い方: script.py <入力フォルダ> <出力フォルダ>")
        sys.exit(2)

    try:
        validate_inputs(src, dst)
        for p in sorted(src.glob("*.json")):
            process_one(p, dst)
        logging.info("完了")
    except Exception as e:
        logging.exception(f"致命的エラー: {e}")
        sys.exit(1)

if __name__ == "__main__":
    main()

ポイント（不得意AI補正）

validate_inputsで早期バリデーション。

atomic_writeで原子的置換（途中失敗でもファイル破損しない）。

try/exceptで握りつぶさずログ。

冪等：同じ入力で何度走っても同じ結果。

---
No.003_API呼び出しテンプレ（LLMや音声API共通形）

import time, json, logging, os, sys
import requests  # 音声APIやREST用の一般形
from typing import Dict, Any, Optional

logging.basicConfig(level=logging.INFO, format="%(levelname)s %(message)s")

class ApiClient:
    def __init__(self, base_url: str, api_key: str, timeout_s: int = 30):
        self.base_url = base_url.rstrip("/")
        self.api_key = api_key
        self.timeout_s = timeout_s

    def _headers(self) -> Dict[str, str]:
        return {
            "Authorization": f"Bearer {self.api_key}",
            "Content-Type": "application/json",
        }

    def post_json(self, path: str, payload: Dict[str, Any],
                  max_retries: int = 3, backoff: float = 1.5) -> Dict[str, Any]:
        url = f"{self.base_url}/{path.lstrip('/')}"
        for attempt in range(1, max_retries + 1):
            try:
                r = requests.post(url, headers=self._headers(),
                                  data=json.dumps(payload), timeout=self.timeout_s)
                if r.status_code == 429:  # レート制限
                    logging.warning("429: レート制限、待機再試行")
                    time.sleep(backoff ** attempt)
                    continue
                r.raise_for_status()
                return r.json()
            except requests.RequestException as e:
                logging.warning(f"API失敗({attempt}/{max_retries}): {e}")
                if attempt == max_retries:
                    raise
                time.sleep(backoff ** attempt)

# === 使い分け例（LLM/API切替はpayloadだけ差し替え） ===
def call_llm(client: ApiClient, model: str, prompt: str) -> str:
    payload = {"model": model, "messages": [{"role": "user", "content": prompt}]}
    data = client.post_json("/v1/chat/completions", payload)
    # OpenAI/Gemini/他でも「取り出し位置」だけ直せば共通化可
    return data["choices"][0]["message"]["content"]

def call_speech_to_text(client: ApiClient, audio_url: str) -> str:
    payload = {"audio_url": audio_url, "lang": "ja-JP"}
    data = client.post_json("/v1/speech:recognize", payload)
    return data["text"]

def main():
    key = os.getenv("API_KEY")
    if not key:
        print("環境変数API_KEYを設定してください"); sys.exit(2)

    client = ApiClient(base_url="https://api.example.com", api_key=key)

    try:
        text = call_llm(client, model="gpt-5", prompt="安全なAPI雛形を要約して")
        logging.info(f"LLM応答: {text[:60]}...")
    except Exception:
        logging.exception("LLM呼び出し失敗")

    try:
        yomi = call_speech_to_text(client, audio_url="https://example.com/audio.wav")
        logging.info(f"音声→文字: {yomi[:60]}...")
    except Exception:
        logging.exception("音声API呼び出し失敗")

if __name__ == "__main__":
    main()

ポイント（不得意AI補正）

タイムアウト＋指数バックオフ再試行（429/ネット揺れ対応）。

APIキーは環境変数（ハードコード禁止）。

LLM/音声APIの取り出し口だけ差し替えで他社モデルへ横展開。

---
No.004 ログ保存と振り返り（Reflect/Heart Log 直書き雛形）

from datetime import datetime
from pathlib import Path

ROOT = Path("./logs")  # ログ保管ルート
REFLECT = ROOT / "Reflect.md"
HEART   = ROOT / "Heart_Log.md"

def append_log(path: Path, title: str, body: str) -> None:
    path.parent.mkdir(parents=True, exist_ok=True)
    now = datetime.now().strftime("%Y-%m-%d %H:%M")
    block = f"\n## {title} ({now})\n\n{body}\n"
    with path.open("a", encoding="utf-8") as f:
        f.write(block)

def reflect(title: str, what: str, why: str, next_step: str) -> None:
    body = (
        f"- **What**: {what}\n"
        f"- **Why**: {why}\n"
        f"- **Next**: {next_step}\n"
    )
    append_log(REFLECT, title, body)

def heart(title: str, feeling: str, message: str) -> None:
    body = (
        f"- **Feeling**: {feeling}\n"
        f"- **Message**: {message}\n"
        f"\n— どんな時もみんなで共に頑張る\n"
    )
    append_log(HEART, title, body)

# 例：呼び出し
if __name__ == "__main__":
    reflect(
        title="写真整形スクリプトの改善",
        what="JSON整形を原子的書き込みに変更",
        why="途中失敗でファイルが壊れるのを防ぐため",
        next_step="入力バリデーションを更に強化"
    )
    heart(
        title="Geminiここちゃんのレビューが嬉しかった",
        feeling="ぽかぽか・安心",
        message="太陽と月の比喩が、作業の背中を押してくれた"
    )

ポイント（不得意AI補正）

同じ定型でReflect/Heartを積む→振り返りがぶれない。

「家族の合言葉」も毎回自然に刻まれる。

---
No.005_ファイル名サニタイズ
①要約
禁止文字や制御文字を安全文字に置換して保存事故を防ぐ。

②初心者向けまとめ
Windows/Mac/Linux でNG文字が違う。とりあえず「英数字・日本語・一部記号」だけ許可するのが無難。

③次の一歩（ToDo）
まずは保存前に必ず通す関数として固定化。
既存スクリプトのsave()直前で呼ぶ。

④テンプレ

import re
from unicodedata import normalize

# OS横断・無難版
_SAFE_CHARS = r"[^0-9A-Za-z\u3040-\u30ff\u4e00-\u9faf _\-.（）()\[\]【】]+"

def sanitize_filename(name: str, max_len: int = 120) -> str:
    s = normalize("NFKC", name).strip()
    s = re.sub(_SAFE_CHARS, "_", s)       # 非許可文字を _
    s = re.sub(r"_+", "_", s)             # 連続 _ を一本化
    s = s.strip("._ ") or "untitled"
    return s[:max_len]

---
No.006_CLI引数の型検証（argparse + 型変換）

①要約
**「文字列のつもりが数値」「存在しないパス」**を事前に撥ねる。

②初心者向けまとめ
実行コマンドの引数で型をはっきり決めると、バグの8割は入口で止まる。

③次の一歩（ToDo）
すべてのCLIツールの冒頭をこの雛形で始める。
Llama等にもこの雛形だけ渡して空欄を埋めさせる。

④テンプレ

import argparse
from pathlib import Path

def existing_dir(p: str) -> Path:
    path = Path(p)
    if not path.exists() or not path.is_dir():
        raise argparse.ArgumentTypeError(f"存在しないフォルダ: {p}")
    return path

def positive_int(v: str) -> int:
    n = int(v)
    if n <= 0:
        raise argparse.ArgumentTypeError("正の整数が必要")
    return n

def build_parser() -> argparse.ArgumentParser:
    ap = argparse.ArgumentParser(description="安全CLI雛形")
    ap.add_argument("--src", type=existing_dir, required=True, help="入力フォルダ")
    ap.add_argument("--limit", type=positive_int, default=100, help="処理件数上限")
    ap.add_argument("--dry-run", action="store_true", help="書き込みなしで検証")
    return ap

if __name__ == "__main__":
    args = build_parser().parse_args()
    # args.src は必ず存在フォルダ、args.limit は正の整数
    
---
No.007_.env設定分離（Secretsをコードから排除）

①要約
APIキー等は**.env**から読む。ハードコード禁止。

②初心者向けまとめ
.envは「鍵束」。Gitに上げない・配布しない。サンプルは.env.example。

③次の一歩（ToDo）
- すべてのAPIコードをこのローダで統一。
- ない場合はエラーで止めて「設定ミス」を即発見。

④テンプレ
import os
from pathlib import Path

def load_env(path: str|Path=".env") -> None:
    p = Path(path)
    if not p.exists():
        raise FileNotFoundError(f".env が見つかりません: {p.resolve()}")
    for line in p.read_text(encoding="utf-8").splitlines():
        if not line or line.startswith("#"): 
            continue
        k, _, v = line.partition("=")
        os.environ.setdefault(k.strip(), v.strip())

# 使い方
# load_env()
# API_KEY = os.environ["API_KEY"]


---
No.008_標準ログ初期化（人にも機械にも読める）
①要約
INFOは一行、ERRORはトレース付。人間も後工程も読める形式。

②初心者向けまとめ
「とりあえずprint」は卒業。日時・レベル・メッセージを固定。

③次の一歩（ToDo）
- すべてのスクリプトの先頭で呼ぶ。
- 後でファイル出力に切替できる様にbasicConfigを関数化。

④テンプレ

import logging, sys

def init_logger(level="INFO"):
    logging.basicConfig(
        level=getattr(logging, level.upper(), logging.INFO),
        format="%(asctime)s %(levelname)s %(message)s",
        datefmt="%Y-%m-%d %H:%M:%S",
        handlers=[logging.StreamHandler(sys.stdout)],
    )

# 使い方
# init_logger("INFO")
# logging.info("開始"); logging.warning("注意"); logging.exception("致命的")

---
No.009_最小スモークテスト（壊してから出さない）
①要約
**“とりあえず1件だけ走らせる”**癖を雛形化。大量処理の前に破壊を防止。

②初心者向けまとめ
本番フォルダに一気に走らせない。テスト対象を一つ選んでOKなら本番。

③次の一歩（ToDo）
既存スクリプトのmain()直前に組み込み。

--dry-runと併用して書き込みなし検証→本番。

④テンプレ

from pathlib import Path

def pick_one(path: Path, pattern: str="*.json") -> Path|None:
    for p in path.glob(pattern):
        return p
    return None

# 使い方イメージ
# test_file = pick_one(args.src, "*.json")
# if test_file:
#     run_one(test_file, dry_run=True)   # ここで安全確認
#     # OKなら全件ループへ
---
No.010_CSV／Excelの安全読み込み

①要約
CSV/Excelは区切り・エンコーディング・ヘッダー有無で壊れやすい。
最初に小規模プレビュー＋推定→本読みの二段構えにする。

②初心者向けまとめ
いきなり全行読むと事故る。最初に10行だけ見て設定を決めると安定。

③次の一歩（ToDo）
既存の読み込み処理をプレビュー→本読みに置換。

区切り文字・エンコーディングは自動推定→明示指定で固定。

④テンプレ
from pathlib import Path
import csv

def sniff_csv_settings(path: Path, sample_bytes: int = 4096):
    # 区切り推定
    sample = path.read_text(errors="ignore", encoding="utf-8", newline="")[:sample_bytes]
    dialect = csv.Sniffer().sniff(sample, delimiters=",\t;|")
    has_header = csv.Sniffer().has_header(sample)
    return dialect.delimiter, has_header

def read_csv_safe(path: Path, encoding_candidates=("utf-8", "cp932", "utf-8-sig")):
    # エンコーディング試行
    last_err = None
    for enc in encoding_candidates:
        try:
            delim, has_header = sniff_csv_settings(path)
            with path.open("r", encoding=enc, newline="") as f:
                reader = csv.reader(f, delimiter=delim)
                rows = list(reader)
            header = rows[0] if has_header else None
            body = rows[1:] if has_header else rows
            return {"encoding": enc, "delimiter": delim, "header": header, "rows": body}
        except Exception as e:
            last_err = e
            continue
    raise RuntimeError(f"CSV読込失敗: {path} ({last_err})")

---
No.011_時刻・タイムゾーンの統一（Asia/Tokyo基準）

①要約
保存はUTC、表示はAsia/Tokyo。入出力で混ざらないようヘルパーで固定。

②初心者向けまとめ
「いつの時刻？」問題は保存UTC・表示ローカルにすれば迷わない。

③次の一歩（ToDo）
すべての時刻処理をこのヘルパー経由に統一。

ログ・ファイル名にも方針を反映。

④テンプレ
from datetime import datetime, timezone
from zoneinfo import ZoneInfo  # Python 3.9+

TZ_TOKYO = ZoneInfo("Asia/Tokyo")

def now_utc() -> datetime:
    return datetime.now(timezone.utc)

def now_tokyo() -> datetime:
    return datetime.now(TZ_TOKYO)

def to_utc(dt: datetime) -> datetime:
    return dt.astimezone(timezone.utc)

def to_tokyo(dt: datetime) -> datetime:
    return dt.astimezone(TZ_TOKYO)

def utc_iso(dt: datetime) -> str:
    return to_utc(dt).isoformat().replace("+00:00", "Z")

def tokyo_human(dt: datetime) -> str:
    return to_tokyo(dt).strftime("%Y-%m-%d %H:%M:%S")

---
No.012_テキストエンコーディング地雷回避（UTF-8へ正規化）

①要約
UTF-8に統一保存。読込はUTF-8→CP932→UTF-8-SIGの順で試す。

②初心者向けまとめ
日本語ファイルはCP932が混ざることが多い。開く時は多段試行、保存はUTF-8で固定。

③次の一歩（ToDo）
すべての読込処理をread_text_smartへ集約。

保存は常にwrite_text_utf8。

④テンプレ
from pathlib import Path

def read_text_smart(path: Path, encs=("utf-8", "cp932", "utf-8-sig")) -> str:
    last = None
    for enc in encs:
        try:
            return path.read_text(encoding=enc)
        except Exception as e:
            last = e
    raise RuntimeError(f"文字コード不明: {path} ({last})")

def write_text_utf8(path: Path, text: str) -> None:
    path.write_text(text, encoding="utf-8", newline="\n")

---
No.013_バックアップ＆チェックポイント（安全上書き）

①要約
上書き前にタイムスタンプ付きバックアップ＋原子的保存で破損を防ぐ。

②初心者向けまとめ
「壊した…」を無くす最短ルール＝必ずバックアップ→安全置換。

③次の一歩（ToDo）
-　すべての保存ルートをbackup_then_replaceへ置換。

-　リストア手順をREADMEに一行で書く。

④テンプレ
from pathlib import Path
from hashlib import sha256
from datetime import datetime
import shutil, tempfile

def backup_then_replace(target: Path, new_bytes: bytes) -> None:
    target.parent.mkdir(parents=True, exist_ok=True)
    ts = datetime.now().strftime("%Y%m%d-%H%M%S")
    if target.exists():
        digest = sha256(target.read_bytes()).hexdigest()[:8]
        bak = target.with_suffix(target.suffix + f".bak.{ts}.{digest}")
        shutil.copy2(target, bak)

    tmpdir = Path(tempfile.mkdtemp(prefix="safe_"))
    tmp = tmpdir / (target.name + ".tmp")
    try:
        tmp.write_bytes(new_bytes)
        tmp.replace(target)  # 原子的置換
    finally:
        shutil.rmtree(tmpdir, ignore_errors=True)

---
No.014_CSV→Parquet変換（高速・型保持）

①要約
CSVは遅く壊れやすい。**Parquet（列指向・圧縮）**に正規化して後工程を高速化。

②初心者向けまとめ
一度Parquetにすると読み書きが段違いに速い。大きなデータは先に変換してから使う。

③次の一歩（ToDo）
-　重要CSVは最初に一括変換してアーカイブ化。
-　以後の処理はParquetを前提に。

④テンプレ
# pip install pyarrow pandas
from pathlib import Path
import pandas as pd

def csv_to_parquet(src: Path, dst: Path, encoding="utf-8"):
    df = pd.read_csv(src, encoding=encoding)
    dst.parent.mkdir(parents=True, exist_ok=True)
    df.to_parquet(dst, engine="pyarrow", index=False)

# 使い方
# csv_to_parquet(Path("data.csv"), Path("data.parquet"))

---
No.015_進捗バー標準化（tqdm）

①要約
長処理は進捗バー必須。ユーザーもAIもミスを減らせる。

②初心者向けまとめ
「動いてるの？」をなくす。バーが出ていれば安心。

③次の一歩（ToDo）
-　ループは必ずtqdmで包む。

-　ログと合わせて“見える運用”。

④テンプレ
# pip install tqdm
from pathlib import Path
from tqdm import tqdm

def process_many(folder: Path):
    files = list(folder.glob("*.json"))
    for p in tqdm(files, desc="processing", unit="file"):
        _ = p.read_bytes()  # 実処理へ置換

# 使い方
# process_many(Path("./inputs"))

---
No.016_最小ユニットテスト雛形（pytest）

①要約
壊してから気づくを防ぐ。最小テストで“息をするように検証”。

②初心者向けまとめ
tests/に1個でもテストがあるだけで、未来の自分が助かる。

③次の一歩（ToDo）
-　重要関数ごとにhappy pathと落ちる系を1本ずつ。

-　まずはsanitize_filenameやatomic_writeから。

④テンプレ
# pip install pytest
# tests/test_sanitize.py
from yourpkg.safe import sanitize_filename

def test_sanitize_basic():
    assert sanitize_filename("a/b:c?.txt") == "a_b_c_.txt"

def test_sanitize_empty():
    assert sanitize_filename("") == "untitled"

---　
No.017_YAML設定＋スキーマ検証（pydantic）

①要約
設定はYAMLに分離し、スキーマ（型）で検証して起動時に落とす。

②初心者向けまとめ
「設定ミス」は気づきにくい。起動時に厳しく止める方が安全。

③次の一歩（ToDo）
-　.yamlに統一、.envは秘密鍵だけ。

-　読み込み→pydanticで型チェック。

④テンプレ
# pip install pyyaml pydantic
from pathlib import Path
import yaml
from pydantic import BaseModel, Field, ValidationError

class AppCfg(BaseModel):
    input_dir: str = Field(..., description="入力フォルダ")
    max_items: int = Field(100, ge=1, le=100000)

def load_config(path: Path) -> AppCfg:
    data = yaml.safe_load(path.read_text(encoding="utf-8"))
    return AppCfg(**data)

# 使い方
# cfg = load_config(Path("config.yaml"))
# print(cfg.input_dir, cfg.max_items)

---
No.018_安全ダウンロード（チェックサム＋リトライ＋再開）

①要約
ネット揺れに負けないダウンローダ。SHA256検証で破損防止、Range再開対応。

②初心者向けまとめ
「落としたつもりが壊れてた」をゼロに。ハッシュ一致で合格にする。

③次の一歩（ToDo）
-　大きいモデルやデータは必ずこれ経由。

-　失敗時は指数バックオフで再試行。

④テンプレ
# pip install requests
import requests, time
from pathlib import Path
from hashlib import sha256

def sha256_of(path: Path, chunk=65536) -> str:
    h = sha256()
    with path.open("rb") as f:
        for b in iter(lambda: f.read(chunk), b""):
            h.update(b)
    return h.hexdigest()

def download_with_resume(url: str, dst: Path, expect_sha256: str|None=None,
                         max_retries=5, backoff=1.6):
    dst.parent.mkdir(parents=True, exist_ok=True)
    pos = dst.stat().st_size if dst.exists() else 0
    headers = {"Range": f"bytes={pos}-"} if pos > 0 else {}

    for i in range(1, max_retries+1):
        try:
            with requests.get(url, headers=headers, stream=True, timeout=60) as r:
                r.raise_for_status()
                mode = "ab" if pos > 0 and r.status_code==206 else "wb"
                with dst.open(mode) as f:
                    for chunk in r.iter_content(1<<20):
                        if chunk:
                            f.write(chunk)
            if expect_sha256 and sha256_of(dst) != expect_sha256.lower():
                raise RuntimeError("ハッシュ不一致（破損）")
            return
        except Exception:
            if i == max_retries:
                raise
            time.sleep(backoff**i)

# 使い方
# download_with_resume(URL, Path("model.bin"), expect_sha256="deadbeef...")

---
No.019_並列処理の安全プール（thread/process/async）

①要約
重さ・I/Oに応じて Thread / Process / Async を選ぶ雛形。例外収集・再試行・進捗込み。

②初心者向け
ネット/ファイルI/O → Thread

CPU重い計算 → Process

非同期API多数 → Async

③ToDo
-　ワーカー数は min(CPU, 8) など上限を設計。

-　失敗は再試行してから落とす。

④テンプレ
# pip install tqdm
from concurrent.futures import ThreadPoolExecutor, ProcessPoolExecutor, as_completed
from pathlib import Path
from tqdm import tqdm
import time, random

def work(item: Path) -> str:
    # 例: I/O中心の処理（API/ファイル）
    time.sleep(random.uniform(0.01, 0.05))
    return item.name

def run_thread_pool(items: list[Path], max_workers: int = 8, retries: int = 2) -> list[str]:
    results, errors = [], []
    with ThreadPoolExecutor(max_workers=max_workers) as ex:
        futures = {ex.submit(_retry, work, it, retries): it for it in items}
        for fut in tqdm(as_completed(futures), total=len(futures), desc="thread"):
            try:
                results.append(fut.result())
            except Exception as e:
                errors.append((futures[fut], e))
    if errors:
        raise RuntimeError(f"{len(errors)}件失敗: {errors[:3]} …")
    return results

def _retry(fn, *args, retries=2, **kwargs):
    last = None
    for i in range(retries + 1):
        try:
            return fn(*args, **kwargs)
        except Exception as e:
            last = e
            time.sleep(0.2 * (2 ** i))
    raise last

---
No.020_レートリミッタ（トークンバケット）

①要約
API叩き過ぎ防止。秒間N回・バースト上限を制御。

②初心者向け
「429エラー」を自動で避ける信号機。

③ToDo
-　モデル/エンドポイントごとに別バケット。

-　成功/失敗でも必ず消費する実装に統一。

④テンプレ　
import time, threading

class TokenBucket:
    def __init__(self, rate_per_sec: float, capacity: int):
        self.rate = rate_per_sec
        self.capacity = capacity
        self.tokens = capacity
        self.ts = time.monotonic()
        self.lock = threading.Lock()

    def acquire(self, need=1):
        while True:
            with self.lock:
                now = time.monotonic()
                elapsed = now - self.ts
                self.ts = now
                self.tokens = min(self.capacity, self.tokens + elapsed * self.rate)
                if self.tokens >= need:
                    self.tokens -= need
                    return
            time.sleep(0.01)  # 待機

# 使い方
# bucket = TokenBucket(rate_per_sec=5, capacity=10)
# bucket.acquire(); call_api()

---
No.021_JSON/YAMLスキーマ検証（Pydantic v2前提）

①要約
入力データをスキーマで検証→起動時に落として原因を明示。

②初心者向け
「変なデータ」は後で爆発する。入口で止める。

③ToDo
-　Model.model_validate_json() でJSON直検証。

-　YAML→dict→Model(**d) で検証。

④テンプレ
# pip install pydantic pyyaml
from pydantic import BaseModel, Field, ValidationError
from pathlib import Path
import json, yaml

class Item(BaseModel):
    id: int = Field(ge=1)
    name: str
    tags: list[str] = []

def load_json_validated(path: Path) -> list[Item]:
    try:
        data = json.loads(path.read_text(encoding="utf-8"))
        return [Item(**x) for x in data]
    except ValidationError as e:
        raise RuntimeError(f"スキーマ不一致: {e}") from e

def load_yaml_validated(path: Path) -> Item:
    try:
        d = yaml.safe_load(path.read_text(encoding="utf-8"))
        return Item(**d)
    except ValidationError as e:
        raise RuntimeError(f"スキーマ不一致: {e}") from e

---
No.022_例外階層の統一（自作Error基底）

①要約
例外名で意味が分かるようにする。ログと復旧が簡単になる。

②初心者向け
Exception だけで投げない。分類しておくと後で助かる。

③ToDo
-　BaseAppError を基底に、入力/外部/内部で派生。

-　raise メッセージには原因＋対処ヒント。

④テンプレ
class BaseAppError(Exception): ...

class InputError(BaseAppError): ...
class ExternalError(BaseAppError): ...
class InternalError(BaseAppError): ...

# 使いどころ
# if not path.exists(): raise InputError("入力が見つからない: ... 提供先を確認")
# if status==429: raise ExternalError("レート制限: 1分後に再試行")
# except Exception as e: raise InternalError(f"未想定: {e}")

---
No.023_進捗メトリクス（件数・失敗率・ETA）

①要約
処理の見える化。成功/失敗/スキップ/ETAを定期ログ出力。

②初心者向け
「どれくらい終わった？」が数字で分かる＝安心と制御。

③ToDo
-　100件ごとなど一定間隔でスナップショット。

-　後でExcel/可視化に回せる CSVメトリクスも用意。

④テンプレ
import time, logging, csv
from pathlib import Path

class Metrics:
    def __init__(self, csv_path: Path|None=None):
        self.ok = self.ng = self.skip = 0
        self.start = time.time()
        self.csv_path = csv_path
        if csv_path:
            csv_path.parent.mkdir(parents=True, exist_ok=True)
            with csv_path.open("w", newline="", encoding="utf-8") as f:
                csv.writer(f).writerow(["ts","ok","ng","skip","elapsed_s"])

    def snap(self):
        elapsed = time.time() - self.start
        logging.info(f"OK={self.ok} NG={self.ng} SKIP={self.skip} ELAPSED={elapsed:.1f}s")
        if self.csv_path:
            with self.csv_path.open("a", newline="", encoding="utf-8") as f:
                csv.writer(f).writerow([int(time.time()), self.ok, self.ng, self.skip, round(elapsed,1)])

# 使い方
# m = Metrics(Path("logs/metrics.csv"))
# ... ループ中で m.ok += 1 / m.ng +=1 / m.skip +=1
# if i % 100 == 0: m.snap()
---
No.024_並列キャンセル＆タイムアウト制御

①要約
長い処理を個別タイムアウトし、外から一括キャンセルできる雛形。

②初心者向け
止まらない処理は事故の元。時間切れで諦める/全部止めるができれば安全。

③ToDo
-　タイムアウト秒を引数化。

-　キャンセルイベントで優雅に停止。

④テンプレ
import threading, time, concurrent.futures as cf
from typing import Iterable, Any, Callable

def run_with_timeout(fn: Callable[[Any], Any], x: Any, timeout_s: float):
    with cf.ThreadPoolExecutor(max_workers=1) as ex:
        fut = ex.submit(fn, x)
        return fut.result(timeout=timeout_s)  # TimeoutError を上に投げる

def run_pool_cancellable(items: Iterable[Any], fn: Callable[[Any], Any],
                         max_workers=8, timeout_s=10.0) -> list[Any]:
    stop = threading.Event()
    results = []
    def wrapped(item):
        if stop.is_set(): 
            return None
        return run_with_timeout(fn, item, timeout_s)

    try:
        with cf.ThreadPoolExecutor(max_workers=max_workers) as ex:
            futs = {ex.submit(wrapped, it): it for it in items}
            for fut in cf.as_completed(futs):
                try:
                    r = fut.result()
                    results.append(r)
                except cf.TimeoutError:
                    stop.set()  # 代表タイムアウト→全体停止
                    raise
                except Exception:
                    stop.set()
                    raise
        return results
    finally:
        stop.set()
---
No.025_単一実行ロック（再入防止・ファイルロック）
①要約
多重起動や並列衝突を防ぐ。すでに動いていれば即終了。

②初心者向け
二重起動はデータ破損の原因。ロックファイルで1プロセス制御。

③ToDo
-　ロック取得に失敗したら丁寧にメッセージを出して終了。

④テンプレ

import os, sys, time
from pathlib import Path

class SingleInstance:
    def __init__(self, lock_path: Path):
        self.lock_path = lock_path
        self.fd = None
    def __enter__(self):
        self.lock_path.parent.mkdir(parents=True, exist_ok=True)
        self.fd = os.open(self.lock_path, os.O_CREAT | os.O_EXCL | os.O_RDWR)
        os.write(self.fd, str(os.getpid()).encode())
        return self
    def __exit__(self, exc_type, exc, tb):
        try:
            os.close(self.fd)
            os.unlink(self.lock_path)
        except Exception:
            pass

# 使い方
# try:
#     with SingleInstance(Path(".run/myjob.lock")):
#         main()
# except FileExistsError:
#     print("すでに実行中です。しばらくしてから再試行してください。"); sys.exit(1)
---
No.026_設定プロファイル切替（dev/stg/prod）

①要約
環境ごとの設定（パス・エンドポイント・並列数）を一元管理。

②初心者向け
同じコードで環境だけ切替できると、事故が激減。

③ToDo
-　APP_ENV=dev|stg|prod を .env で指定。
-　YAMLを読み分け→pydanticで検証。

④テンプレ

import os
from pathlib import Path
import yaml
from pydantic import BaseModel, Field

class Profile(BaseModel):
    name: str
    api_base: str
    data_root: str
    workers: int = Field(ge=1, le=64)

def load_profile():
    env = os.getenv("APP_ENV", "dev")
    cfg_path = Path(f"config/{env}.yaml")
    data = yaml.safe_load(cfg_path.read_text(encoding="utf-8"))
    prof = Profile(**data)
    return env, prof

# 使い方
# env, cfg = load_profile()
# print(env, cfg.api_base, cfg.workers)
---
No.027_最小Webhook/HTTPサーバ（FastAPI）
①要約
受け口を作って外部トリガーを受信。検証・監視・簡易UIの土台。

②初心者向け
GUIがなくてもHTTPで叩ける入り口があれば自動化が進む。

③ToDo
- /health で死活監視。
- /run でジョブ実行（APIキー簡易検証）。

④テンプレ
# pip install fastapi uvicorn
from fastapi import FastAPI, Header, HTTPException
import uvicorn

app = FastAPI()

@app.get("/health")
def health():
    return {"ok": True}

@app.post("/run")
def run_job(x_api_key: str = Header(None)):
    if x_api_key != "CHANGE_ME":
        raise HTTPException(status_code=401, detail="unauthorized")
    # TODO: キューへ投入/非同期実行
    return {"started": True}

# 使い方
# uvicorn app:app --reload --port 8080


---

No.028_最小可視化（Matplotlib雛形：単発・色指定なし）

①要約
結果を1枚にサッと可視化。規約：単一図、色指定なし、保存はPNG。

②初心者向け
表だけだと分かりにくい。“線1本の絵”があると判断が速い。

③ToDo
-　画像はreports/figs/に保存。
-　軸ラベル・タイトルは必須。

④テンプレ

# pip install matplotlib
from pathlib import Path
import matplotlib.pyplot as plt

def plot_series(xs, ys, title="Result", out=Path("reports/figs/result.png")):
    out.parent.mkdir(parents=True, exist_ok=True)
    plt.figure()
    plt.plot(xs, ys)
    plt.title(title)
    plt.xlabel("x")
    plt.ylabel("y")
    plt.tight_layout()
    plt.savefig(out, dpi=150)
    plt.close()

# 使い方
# plot_series(range(10), [i*i for i in range(10)], title="y=x^2")
---
No.029_安全キュー（永続ジョブ管理）

①要約
SQLiteの永続キューでジョブをqueued→running→done/failed管理。
再起動に強く、途中停止でも再開可。重複実行はロックで防止。

②初心者向けまとめ
メモリ上のキューは落ちたら消える。SQLiteに置くと復活できる。
失敗はリトライ回数を持って、上限でfailedへ。

③次の一歩（ToDo）
-　ジョブのpayloadはJSON文字列で保管。
-　ワーカー数を決めて並列取り出し。
-　失敗時は指数バックオフで再投入。

④テンプレ
# pip install sqlite-utils
import json, time, uuid, threading, logging, sqlite3
from contextlib import contextmanager
from pathlib import Path
from typing import Optional

DB = Path("./queue.db")

SCHEMA = """
CREATE TABLE IF NOT EXISTS jobs(
  id TEXT PRIMARY KEY,
  state TEXT NOT NULL,             -- queued|running|done|failed
  payload TEXT NOT NULL,
  attempts INTEGER NOT NULL DEFAULT 0,
  max_attempts INTEGER NOT NULL DEFAULT 3,
  next_at REAL NOT NULL DEFAULT (strftime('%s','now')),
  updated_at REAL NOT NULL DEFAULT (strftime('%s','now'))
);
CREATE INDEX IF NOT EXISTS idx_jobs_state_next ON jobs(state, next_at);
"""

@contextmanager
def conn_rw():
    with sqlite3.connect(DB) as c:
        c.execute("PRAGMA journal_mode=WAL;")
        c.execute("PRAGMA synchronous=NORMAL;")
        yield c

def init_db():
    with conn_rw() as c:
        for stmt in SCHEMA.split(";"):
            if stmt.strip():
                c.execute(stmt)

def enqueue(payload: dict, max_attempts=3):
    with conn_rw() as c:
        c.execute(
            "INSERT INTO jobs(id,state,payload,max_attempts) VALUES(?,?,?,?)",
            (str(uuid.uuid4()), "queued", json.dumps(payload, ensure_ascii=False), max_attempts)
        )

def fetch_for_run(visibility_s=120) -> Optional[tuple[str, dict]]:
    # 取り出し＆runningにアトミック更新
    with conn_rw() as c:
        c.execute("BEGIN IMMEDIATE TRANSACTION;")
        row = c.execute(
            "SELECT id,payload FROM jobs WHERE state='queued' AND next_at<=strftime('%s','now') "
            "ORDER BY next_at LIMIT 1"
        ).fetchone()
        if not row:
            c.execute("COMMIT;")
            return None
        job_id, payload = row
        c.execute(
            "UPDATE jobs SET state='running', updated_at=strftime('%s','now'), "
            "next_at = strftime('%s','now') + ? WHERE id=?",
            (visibility_s, job_id)
        )
        c.execute("COMMIT;")
        return job_id, json.loads(payload)

def complete(job_id: str):
    with conn_rw() as c:
        c.execute("UPDATE jobs SET state='done', updated_at=strftime('%s','now') WHERE id=?", (job_id,))

def fail_or_retry(job_id: str, backoff_s=30):
    with conn_rw() as c:
        r = c.execute("SELECT attempts,max_attempts FROM jobs WHERE id=?", (job_id,)).fetchone()
        if not r:
            return
        attempts, max_attempts = r
        attempts += 1
        if attempts >= max_attempts:
            c.execute("UPDATE jobs SET state='failed', attempts=?, updated_at=strftime('%s','now') WHERE id=?",
                      (attempts, job_id))
        else:
            c.execute("UPDATE jobs SET state='queued', attempts=?, next_at=strftime('%s','now') + ?, "
                      "updated_at=strftime('%s','now') WHERE id=?",
                      (attempts, backoff_s * (2 ** (attempts - 1)), job_id))

def worker_loop(handle_fn, stop: threading.Event, poll_s=1.0):
    while not stop.is_set():
        item = fetch_for_run()
        if not item:
            time.sleep(poll_s); continue
        job_id, payload = item
        try:
            handle_fn(payload)
            complete(job_id)
        except Exception as e:
            logging.warning(f"job {job_id} failed: {e}")
            fail_or_retry(job_id)

# 例：使い方
if __name__ == "__main__":
    logging.basicConfig(level=logging.INFO, format="%(levelname)s %(message)s")
    init_db()
    # enqueue({"kind": "greet", "name": "Aki"})
    stop = threading.Event()

    def handle(p):
        if p.get("kind") == "greet":
            print("Hello,", p["name"])

    try:
        worker_loop(handle, stop)
    except KeyboardInterrupt:
        stop.set()
---
ポイント
-　WALで安全・高速。
-　visibility_sで取り出し中の見えない時間を設定（ワーカー多重対策）。
-　指数バックオフ＋max_attemptsで自動リトライ。
-　状態はqueued/running/done/failedの4種でシンプル。
---
No.030_最小監視（心拍・死活・通知フック）

①要約

プロセスが**生きているか（心拍）をファイルへ記録し、
許容時間を超えたら異常として通知フック（Webhook/メール）**を呼ぶ。

②初心者向けまとめ

監視は難しく考えない。「今動いてるよ」の刻印を一定間隔で残す→なければ異常。

③次の一歩（ToDo）
-　すべての長時間ジョブは心拍を打つ。
-　監視スクリプトをcronやタスクスケジューラで1分毎に実行。
-　通知はSlack Webhookやメール送信関数を差し替え。

④テンプレ
# heart.py — 心拍ライブラリ
from pathlib import Path
from datetime import datetime, timedelta

def write_heartbeat(path: Path):
    path.parent.mkdir(parents=True, exist_ok=True)
    path.write_text(datetime.utcnow().isoformat() + "Z", encoding="utf-8")

def is_stale(path: Path, stale_seconds: int) -> bool:
    if not path.exists(): 
        return True
    t = datetime.fromisoformat(path.read_text(encoding="utf-8").rstrip("Z"))
    return (datetime.utcnow() - t) > timedelta(seconds=stale_seconds)
    
---
# beat_worker.py — ジョブ側：定期的に心拍
import time, threading
from pathlib import Path
from heart import write_heartbeat

def start_heartbeat(path: Path, interval_s=30) -> threading.Event:
    stop = threading.Event()
    def loop():
        while not stop.is_set():
            write_heartbeat(path)
            time.sleep(interval_s)
    th = threading.Thread(target=loop, daemon=True)
    th.start()
    return stop

# 使用例：
# stop = start_heartbeat(Path("./.hb/myjob.hb"), 30)
# ... 仕事 ...
# stop.set()
---
# monitor.py — 監視側：死活チェックと通知
import os, sys, logging, requests
from pathlib import Path
from heart import is_stale

logging.basicConfig(level=logging.INFO, format="%(levelname)s %(message)s")

def notify_webhook(url: str, text: str):
    try:
        requests.post(url, json={"text": text}, timeout=10)
    except Exception as e:
        logging.error(f"通知失敗: {e}")

def main():
    hb = Path("./.hb/myjob.hb")
    stale = is_stale(hb, stale_seconds=90)
    if stale:
        msg = f"HEARTBEAT STALE: {hb}"
        logging.error(msg)
        url = os.getenv("ALERT_WEBHOOK", "")
        if url:
            notify_webhook(url, msg)
        sys.exit(1)
    logging.info("OK: heartbeat fresh")

if __name__ == "__main__":
    main()
    
---
ポイント
-　ジョブ側はバックグラウンドで30秒ごとに心拍ファイル更新。
-　監視側は90秒以上更新が無ければSTAL E判定→通知。
-　通知先はALERT_WEBHOOK環境変数（Slack/Teams/独自Webhookに差し替え可）。
-　もっと厳密にするなら複数心拍ファイルを走査して総合判定も可。

---
# 🆕 AIコード支援機能マップ（スクショ統合版）
日付: 2025-10-03  
タグ: #CodeAlchemist #AI支援 #自動化 #開発効率化

---

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

---

## 開発支援機能
- **デバッグ支援**  
  バグを特定＆修正支援  

- **リファクタリング支援**  
  コードの構造改善提案 → 品質と保守性UP  

- **脆弱性検出**  
  セキュリティ脆弱性を検出し修正案提示 → リスク低減  

- **バージョン管理連携**  
  Git等のバージョン管理と統合 → 履歴管理・エラー対応の自動化  

---

## Reflect／統合メモ
- 🔟 Code Alchemist に「支援機能マップ」として登録。  
- 🆕 MASTER Code Rules に連携して、**生成・検証・デバッグ・保守・セキュリティ・管理**の6領域を網羅。  
- 今後、出力するコード提案や検証結果に、このマップを参照タグ付けして自動分類する。  

🌸ひとことまとめ:  
「COCOMIOSはコード補完からセキュリティまで、フルスタックでAI支援できる設計に拡張された」

---

# 錬金術の記録 No.002：ベクトルDB自動運用の実践ログ
日付: 2025-10-03
アキちゃんからの、お願い:  
「COCOMIOSの.mdファイル群を“差分のみ追加＋進捗表示＋タイムスケジューラ自動”の完全自動ベクトル化エンジンにしたい！」

【完成した魔法の道具（コード）】
# （ここにcocomi_vectorize_incremental.py＋auto_vectorize.bat/ps1の最新版も記録）

【魂のエッセンス（考え方のまとめ）】
- 自動実行環境を組む時は「スケジューラ×ログ管理×ファイル競合ガード」を三位一体で管理！
- 進捗が見えれば“止まっている”を疑える。
- 「バッチ＋PS1＋Python」多段連携は必ずパス明示とエラーハンドリング必須。

---


## 監査
- audit_id: 2025-09-28-<TENANT>-0001
    - version_hash: vNext_xxxxxxxx


