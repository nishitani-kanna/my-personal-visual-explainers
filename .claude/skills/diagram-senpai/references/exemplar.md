# 模範解答パターン

## 成功する図解の構造

```
1. ヘッダー
   └─ カテゴリバッジ + タイトル + 一言サマリー

2. まず覚える3つ（必須）
   └─ 色分けされた番号カード × 3
   └─ 各カードに：タイトル + 1〜2文の説明

3. キャラクター対話（導入）
   └─ さも→うさ でトピックの「なぜ大事か」を会話形式で引き出す

4. 各論セクション × 2〜4
   └─ セクションヘッダー（アイコン + タイトル）
   └─ 用語解説ボックス（初出の専門用語に必ず）
   └─ たとえ話ボックス
   └─ NG/OK比較グリッド（行動の対比がある場合）
   └─ キャラクター対話（重要ポイント or 落とし穴）

5. キャラクター対話（まとめへの橋渡し）
   └─ うさ→さも で「この3つだけ持って帰って」の一言

6. 30秒まとめ（必須・最後）
   └─ 番号カード × 3（動詞で締める短い文）
```

---

## 30秒まとめの書き方

### 良い例
- 「AIに入力する前に『社外に出していい？』と確認する」
- 「個人名・会社名・設計書などの固有情報は入力しない」
- 「使うAIツールが社内で承認されているか確認してから使う」

### 悪い例
- 「セキュリティに気をつける」（曖昧すぎる）
- 「情報漏えいのリスクを理解し、適切な情報管理を行う」（硬すぎる・行動が見えない）
- 「個人情報保護法第〇条に基づき……」（新人には難しすぎる）

**ポイント**: 動詞で終わる短文（「〜する」「〜しない」「〜確認する」）にする。

---

## 品質チェックリスト

作成後、以下を全て確認する:

### 構成・内容
- [ ] 「まず覚える3つ」セクションがある（3項目ちょうど）
- [ ] 末尾に「30秒まとめ」がある（3項目ちょうど）
- [ ] キャラクター対話が3箇所ある（導入・重要ポイント・まとめ前）
- [ ] 専門用語が最初に出てきたとき、用語解説ボックスがある
- [ ] たとえ話が3つ以上ある（職場・日常・デジタルなど複数種類）

### デザイン
- [ ] Lucide iconのみ使用（絵文字を使っていない）
- [ ] 外部画像ファイルを参照していない
- [ ] スマホでも読みやすい（`md:` breakpointで対応）
- [ ] `<script>` タグはLucide初期化のみ

### トーン
- [ ] 30秒まとめの各項目が動詞で終わる短文になっている
- [ ] うさ・さもの対話が命令口調になっていない
- [ ] 読者をレベルでラベリングする表現がない（「初心者向け」等）
- [ ] セキュリティ系の表現が怖がらせるよりも「こうすれば大丈夫」になっている

---

## 模範HTML全文（ベージュ・黒ベース）

このHTMLを模範として、同等の構成・密度・NG/OK比較・たとえ話・キャラクター対話を含む図解を生成すること。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>業務でのAIツール安全活用ガイド</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700;900&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Noto Sans JP', 'Inter', sans-serif; background-color: #f5f0e8; }
    .header-gradient { background: linear-gradient(135deg, #2d1f0e 0%, #3d3530 60%, #5a4035 100%); }
    .section-card { background: #fffef8; border-radius: 1rem; box-shadow: 0 4px 6px -1px rgba(45,31,14,0.08); padding: 2rem; margin-bottom: 2rem; border: 1px solid #e5d9c8; }
    .term-explain { background: linear-gradient(135deg, #f7f0e8 0%, #ede0cc 100%); border-left: 4px solid #9c7340; padding: 1.25rem 1.5rem; border-radius: 0 0.75rem 0.75rem 0; margin: 1.5rem 0; }
    .thirty-summary { background: linear-gradient(135deg, #f7f5f0 0%, #ede8da 100%); border: 2px solid #8a6f52; border-radius: 1rem; padding: 2rem; margin-bottom: 2rem; }
    .ng-ok-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 1.5rem 0; }
    @media (max-width: 640px) { .ng-ok-grid { grid-template-columns: 1fr; } }
    .ng-card { background: #fdf0f0; border: 1.5px solid #e0a0a0; border-radius: 0.75rem; padding: 1.25rem; }
    .ok-card { background: #eef5ee; border: 1.5px solid #90c4a0; border-radius: 0.75rem; padding: 1.25rem; }
    .char-img { width: 80px; height: 80px; object-fit: contain; flex-shrink: 0; }
    @media print {
      .section-card { box-shadow: none; border: 1px solid #c8b89a; }
      .header-gradient { background: #2d1f0e !important; }
    }
  </style>
</head>
<body>

  <header class="header-gradient text-white py-10">
    <div class="max-w-3xl mx-auto px-6">
      <div class="text-sm font-medium opacity-75 mb-2 tracking-wide uppercase">セキュリティ</div>
      <h1 class="text-3xl md:text-4xl font-black leading-tight">業務でのAIツール<br class="md:hidden"> 安全活用ガイド</h1>
      <p class="mt-3 text-base md:text-lg opacity-90">入力の前に一呼吸——その1秒が情報事故を防ぐ</p>
    </div>
  </header>

  <main class="max-w-3xl mx-auto px-6 py-8">

    <!-- まず覚える3つ -->
    <div class="section-card">
      <div class="flex items-center gap-3 mb-6">
        <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:#2d1f0e;">
          <i data-lucide="list-checks" class="w-6 h-6 text-white"></i>
        </div>
        <div>
          <h2 class="text-2xl font-bold text-gray-800">まず覚える3つ</h2>
          <p class="text-gray-500 text-sm">これだけ押さえれば大丈夫</p>
        </div>
      </div>
      <div class="space-y-4">
        <div class="flex items-start gap-4 p-4 bg-blue-50 rounded-xl border-l-4 border-blue-500">
          <div class="w-9 h-9 rounded-full flex items-center justify-center font-bold flex-shrink-0 text-white" style="background:#2d1f0e;">1</div>
          <div>
            <div class="font-bold text-gray-800 text-lg mb-1">入力前に「社外に出していい？」と確認する</div>
            <p class="text-gray-600">AIへの入力は、コンビニのコピー機に書類を置く感覚に似ています。「これ、知らない人が見てもOK？」と一問自分に聞く習慣がすべてのベース。</p>
          </div>
        </div>
        <div class="flex items-start gap-4 p-4 bg-teal-50 rounded-xl border-l-4 border-teal-500">
          <div class="w-9 h-9 rounded-full flex items-center justify-center font-bold flex-shrink-0 text-white" style="background:#2d1f0e;">2</div>
          <div>
            <div class="font-bold text-gray-800 text-lg mb-1">会社が承認したツール・アカウントだけ使う</div>
            <p class="text-gray-600">個人の無料アカウントで業務データを扱うのは「シャドーIT」と呼ばれ、情報漏えいリスクに直結します。まず社内ルールを確認してから使いましょう。</p>
          </div>
        </div>
        <div class="flex items-start gap-4 p-4 rounded-xl border-l-4" style="background:#fdf6e8; border-color:#9c7340;">
          <div class="w-9 h-9 rounded-full flex items-center justify-center font-bold flex-shrink-0 text-white" style="background:#2d1f0e;">3</div>
          <div>
            <div class="font-bold text-gray-800 text-lg mb-1">AIの出力は「案」として、自分で確認する</div>
            <p class="text-gray-600">AIが自信満々に答えても、古い情報・誤った内容・ライセンス不明のコードが含まれる場合があります。最終的な責任を持つのは常に人間です。</p>
          </div>
        </div>
      </div>
    </div>

    <!-- さも→うさ（導入の疑問） -->
    <div class="flex items-start gap-4 mb-5">
      <img src="./images/さも-ニコニコ.png" alt="さも" class="char-img">
      <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
        <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
        <p class="text-gray-700">AIって何でも聞いていいんですよね？業務の内容もそのまま貼っちゃっていいのかな…</p>
      </div>
    </div>
    <div class="flex items-start gap-4 mb-8 flex-row-reverse">
      <img src="./images/うさ-説明中.png" alt="うさ" class="char-img">
      <div class="bg-blue-50 border border-blue-200 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
        <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
        <p class="text-gray-700">気持ちはわかるよ！うまく使えば調査も実装も何倍も速くなるよね。でも「どこまで入力していいか」を知らないまま使うと、後で困ることになりかねないんだ。難しいルールは全部覚えなくていいから、「一呼吸置く習慣」だけ身につけてもらえれば大丈夫！</p>
      </div>
    </div>

    <!-- セクション1: 入力してはいけない情報 -->
    <div class="section-card">
      <div class="flex items-center gap-3 mb-6">
        <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:#f5ede8;">
          <i data-lucide="shield-x" class="w-6 h-6" style="color:#963030;"></i>
        </div>
        <div>
          <h2 class="text-2xl font-bold text-gray-800">入力してはいけない情報</h2>
          <p class="text-gray-500 text-sm">混ざっていたら伏せ字・ダミー表記に置き換えてから渡す</p>
        </div>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-6">
        <div class="rounded-xl p-4" style="background:#fdf0f0; border:1px solid #e0a0a0;">
          <div class="flex items-center gap-2 mb-2">
            <i data-lucide="user" class="w-5 h-5" style="color:#963030;"></i>
            <span class="font-bold" style="color:#6b1e1e;">個人情報</span>
          </div>
          <ul class="text-sm text-gray-600 space-y-1">
            <li>顧客・担当者の氏名</li>
            <li>メールアドレス・電話番号</li>
            <li>住所・生年月日</li>
          </ul>
        </div>
        <div class="rounded-xl p-4" style="background:#fdf6e8; border:1px solid #d4b88a;">
          <div class="flex items-center gap-2 mb-2">
            <i data-lucide="file-text" class="w-5 h-5" style="color:#9c7340;"></i>
            <span class="font-bold" style="color:#7a5010;">業務機密情報</span>
          </div>
          <ul class="text-sm text-gray-600 space-y-1">
            <li>設計書・仕様書・議事録</li>
            <li>顧客名・案件名・プロジェクト内容</li>
            <li>社内システムの構成情報</li>
          </ul>
        </div>
        <div class="rounded-xl p-4" style="background:#f7f0ff; border:1px solid #c4b0e0;">
          <div class="flex items-center gap-2 mb-2">
            <i data-lucide="key" class="w-5 h-5" style="color:#7c5cbf;"></i>
            <span class="font-bold" style="color:#4a2f8a;">認証情報</span>
          </div>
          <ul class="text-sm text-gray-600 space-y-1">
            <li>パスワード・APIキー</li>
            <li>.envファイルの中身</li>
            <li>トークン・シークレットキー</li>
          </ul>
        </div>
        <div class="rounded-xl p-4" style="background:#fdf6e8; border:1px solid #d4b88a;">
          <div class="flex items-center gap-2 mb-2">
            <i data-lucide="code" class="w-5 h-5" style="color:#9c7340;"></i>
            <span class="font-bold" style="color:#7a5010;">社内固有のコード</span>
          </div>
          <ul class="text-sm text-gray-600 space-y-1">
            <li>本番環境のコード・設定ファイル</li>
            <li>社内ライブラリ・エンドポイント設計</li>
            <li>エラーログの全文（顧客IDが混入しやすい）</li>
          </ul>
        </div>
      </div>

      <!-- たとえ話 -->
      <div class="p-5 rounded-xl mb-5" style="background:#fdf6e8; border:1.5px solid #d4b88a;">
        <div class="flex items-center gap-2 mb-3">
          <i data-lucide="coffee" class="w-5 h-5" style="color:#9c7340;"></i>
          <span class="font-bold" style="color:#7a5010;">たとえるなら——</span>
        </div>
        <p class="text-gray-700">コンビニのコピー機に社外秘の書類を置き忘れる感覚に似ています。便利なのは確かですが、<strong>誰が・どこで・どう扱われるか</strong>は自分の手元では完結しない。「社外の人が見ても大丈夫な内容かどうか」を入力前に確認する習慣が大切です。</p>
      </div>

      <!-- チャットUIモック：NG vs OK -->
      <h3 class="font-bold text-gray-700 text-lg mb-3 flex items-center gap-2">
        <i data-lucide="monitor" class="w-5 h-5 text-gray-600"></i>
        実際のAIチャット——こう変えるだけでOK
      </h3>
      <div class="ng-ok-grid mb-5">
        <div class="ng-card">
          <div class="flex items-center gap-2 mb-3">
            <i data-lucide="x-circle" class="w-5 h-5" style="color:#963030;"></i>
            <span class="font-bold" style="color:#6b1e1e;">やりがちなNG</span>
          </div>
          <div class="rounded-lg overflow-hidden text-xs mb-3" style="background:#1e1a16;">
            <div class="px-3 py-1.5 font-mono" style="background:#2d2820; color:#a09080;">AI チャット</div>
            <div class="p-3">
              <div class="rounded-lg px-3 py-2 ml-4 text-xs leading-relaxed" style="background:#3b5fa0; color:#f5f0e8;">
                ○○病院の田中花子様（患者ID:83921）向けの<br>
                案内メール文章を添削してください。<br>
                ↑ 顧客名・患者情報が丸ごと入っている
              </div>
            </div>
          </div>
          <p class="text-xs font-medium" style="color:#963030;">実在の人物名・ID・会社名をそのまま入力</p>
        </div>
        <div class="ok-card">
          <div class="flex items-center gap-2 mb-3">
            <i data-lucide="check-circle" class="w-5 h-5" style="color:#3d7a5a;"></i>
            <span class="font-bold" style="color:#2a5a3a;">こうしよう</span>
          </div>
          <div class="rounded-lg overflow-hidden text-xs mb-3" style="background:#1e1a16;">
            <div class="px-3 py-1.5 font-mono" style="background:#2d2820; color:#a09080;">AI チャット</div>
            <div class="p-3">
              <div class="rounded-lg px-3 py-2 ml-4 text-xs leading-relaxed" style="background:#3b5fa0; color:#f5f0e8;">
                ○○様（患者様）向けの案内メール文章を<br>
                添削してください。<br>
                ↑ 固有名詞をダミーに置き換えてから入力
              </div>
            </div>
          </div>
          <p class="text-xs font-medium" style="color:#3d7a5a;">固有名詞を「〇〇様」「△△会社」等に伏せてから入力</p>
        </div>
      </div>

      <div class="ng-ok-grid">
        <div class="ng-card">
          <ul class="space-y-2 text-gray-700 text-sm">
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
              <span>設計書・仕様書のPDFを「要約して」とそのままアップロード</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
              <span>「〇〇株式会社 山田様へ」から始まるメールの文面をそのまま貼って添削依頼</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
              <span>DB接続文字列や .env ファイルの中身を貼ってデバッグを頼む</span>
            </li>
          </ul>
        </div>
        <div class="ok-card">
          <ul class="space-y-2 text-gray-700 text-sm">
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#3d7a5a;">✓</span>
              <span>設計の概要を自分の言葉で書き直して質問する</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#3d7a5a;">✓</span>
              <span>「△△様」「〇〇株式会社」など固有名詞をすべてダミー表記に置き換えてから貼る</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#3d7a5a;">✓</span>
              <span>接続情報は「DB_HOST=example.com」のようにダミー値で示す</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- さも→ラグ（エラーログの落とし穴） -->
      <div class="flex items-start gap-4 mb-5">
        <img src="./images/さも-焦り.png" alt="さも" class="char-img">
        <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
          <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
          <p class="text-gray-700">エラーが出て焦ってて、ログをそのままAIに貼り付けて「このエラーどういう意味ですか？」って聞いちゃいそう…</p>
        </div>
      </div>
      <div class="flex items-start gap-4 mb-5 flex-row-reverse">
        <img src="./images/ラグ-注意.png" alt="ラグ" class="char-img">
        <div class="bg-slate-50 border border-slate-300 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
          <p class="text-sm font-bold text-slate-600 mb-1">ラグ</p>
          <p class="text-gray-700">ログの中に顧客IDや認証トークンが混ざっていることは多い。貼る前に一度、名前・番号・キーが入っていないか確認してから。</p>
        </div>
      </div>
    </div>

    <!-- セクション2: 使うツールを確認する -->
    <div class="section-card">
      <div class="flex items-center gap-3 mb-6">
        <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:#e8f5ee;">
          <i data-lucide="shield-check" class="w-6 h-6" style="color:#3d7a5a;"></i>
        </div>
        <div>
          <h2 class="text-2xl font-bold text-gray-800">使うツールを確認する</h2>
          <p class="text-gray-500 text-sm">「便利だから」だけで選ばない</p>
        </div>
      </div>

      <div class="term-explain">
        <div class="flex items-start gap-3">
          <i data-lucide="lightbulb" class="w-6 h-6 flex-shrink-0 mt-0.5" style="color:#9c7340;"></i>
          <div>
            <div class="font-bold text-lg" style="color:#7a5010;">「シャドーIT」ってなに？</div>
            <p class="text-gray-700 mt-1">会社が承認していないアプリ・サービスを業務に使うこと。「個人のスマホで仕事のファイルを開く」「会社が認めていない無料AIに業務データを入力する」などが該当します。<br><strong>本人に悪気がなくても、情報漏えいやセキュリティ事故の原因になる</strong>ため、「便利だから使う」の前に確認が必要です。</p>
          </div>
        </div>
      </div>

      <h3 class="font-bold text-gray-700 text-lg mb-4 flex items-center gap-2">
        <i data-lucide="git-branch" class="w-5 h-5" style="color:#3d7a5a;"></i>
        AIツールを使う前の確認ステップ
      </h3>

      <div class="flex flex-col md:flex-row items-stretch gap-3 mb-6">
        <div class="flex-1 rounded-xl p-4 text-center" style="background:#eef5ee; border:1.5px solid #90c4a0;">
          <div class="w-10 h-10 rounded-full font-bold flex items-center justify-center mx-auto mb-2 text-white" style="background:#3d7a5a;">1</div>
          <i data-lucide="file-text" class="w-6 h-6 mx-auto mb-2" style="color:#3d7a5a;"></i>
          <div class="font-bold text-gray-800 text-sm">社内ガイドラインを確認</div>
          <p class="text-xs text-gray-500 mt-1">使ってよいツール・禁止ツールが社内で決まっている場合がある</p>
        </div>
        <div class="flex items-center justify-center py-2 md:py-0">
          <i data-lucide="arrow-right" class="w-6 h-6 hidden md:block" style="color:#a09080;"></i>
          <i data-lucide="arrow-down" class="w-6 h-6 md:hidden" style="color:#a09080;"></i>
        </div>
        <div class="flex-1 rounded-xl p-4 text-center" style="background:#eef2fb; border:1.5px solid #94afd4;">
          <div class="w-10 h-10 rounded-full font-bold flex items-center justify-center mx-auto mb-2 text-white" style="background:#3b5fa0;">2</div>
          <i data-lucide="user" class="w-6 h-6 mx-auto mb-2" style="color:#3b5fa0;"></i>
          <div class="font-bold text-gray-800 text-sm">使うアカウントを確認</div>
          <p class="text-xs text-gray-500 mt-1">個人の無料アカウントではなく、会社契約のアカウントを使う</p>
        </div>
        <div class="flex items-center justify-center py-2 md:py-0">
          <i data-lucide="arrow-right" class="w-6 h-6 hidden md:block" style="color:#a09080;"></i>
          <i data-lucide="arrow-down" class="w-6 h-6 md:hidden" style="color:#a09080;"></i>
        </div>
        <div class="flex-1 rounded-xl p-4 text-center" style="background:#f7f0ff; border:1.5px solid #c4b0e0;">
          <div class="w-10 h-10 rounded-full font-bold flex items-center justify-center mx-auto mb-2 text-white" style="background:#7c5cbf;">3</div>
          <i data-lucide="message-square" class="w-6 h-6 mx-auto mb-2" style="color:#7c5cbf;"></i>
          <div class="font-bold text-gray-800 text-sm">不明なら上長に確認</div>
          <p class="text-xs text-gray-500 mt-1">「このツール使っていいですか？」は恥ずかしくない。むしろ正解の行動</p>
        </div>
      </div>

      <div class="p-5 rounded-xl" style="background:#fdf6e8; border:1.5px solid #d4b88a;">
        <div class="flex items-center gap-2 mb-3">
          <i data-lucide="coffee" class="w-5 h-5" style="color:#9c7340;"></i>
          <span class="font-bold" style="color:#7a5010;">たとえるなら——</span>
        </div>
        <p class="text-gray-700">社内のチャットツールで、部署内限定のチャンネルに書いた内容を、全社に見える場所に転送しちゃった——そんな感覚に近いです。<br>「個人の無料AIで業務データを扱う」も同じで、<strong>どこまで共有されているかが自分では見えない</strong>のが問題です。まず社内ルールを確認してから使いましょう。</p>
      </div>
    </div>

    <!-- セクション3: AIの出力を確認してから使う -->
    <div class="section-card">
      <div class="flex items-center gap-3 mb-6">
        <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:#eef2fb;">
          <i data-lucide="check-circle" class="w-6 h-6" style="color:#3b5fa0;"></i>
        </div>
        <div>
          <h2 class="text-2xl font-bold text-gray-800">AIの出力は「案」として確認する</h2>
          <p class="text-gray-500 text-sm">最終的な判断・責任は人間が持つ</p>
        </div>
      </div>

      <p class="text-gray-600 mb-5">AIは自信満々に答えますが、<strong>間違い・古い情報・ライセンス不明のコード</strong>が含まれることがあります。内容を確認せずそのまま使うのは、他の人が書いた草稿を読まずに上司へ提出するようなものです。</p>

      <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-6">
        <div class="rounded-xl p-4 text-center" style="background:#f5f0e8; border:1px solid #c8b89a;">
          <i data-lucide="search" class="w-7 h-7 mx-auto mb-2" style="color:#6b5744;"></i>
          <div class="font-bold text-gray-800 text-sm mb-1">内容の正確さ</div>
          <p class="text-xs text-gray-500">公式ドキュメントと照合。特にAPIのバージョン・仕様</p>
        </div>
        <div class="rounded-xl p-4 text-center" style="background:#f5f0e8; border:1px solid #c8b89a;">
          <i data-lucide="scale" class="w-7 h-7 mx-auto mb-2" style="color:#6b5744;"></i>
          <div class="font-bold text-gray-800 text-sm mb-1">ライセンス</div>
          <p class="text-xs text-gray-500">「このコード、商用利用していいか」の確認。不明なときは先輩に聞くのが正解</p>
        </div>
        <div class="rounded-xl p-4 text-center" style="background:#f5f0e8; border:1px solid #c8b89a;">
          <i data-lucide="shield-check" class="w-7 h-7 mx-auto mb-2" style="color:#6b5744;"></i>
          <div class="font-bold text-gray-800 text-sm mb-1">セキュリティ</div>
          <p class="text-xs text-gray-500">パスワードがコードの中に直書きされていないか、穴のある設定になっていないか</p>
        </div>
      </div>

      <div class="p-5 rounded-xl" style="background:#fdf6e8; border:1.5px solid #d4b88a;">
        <div class="flex items-center gap-2 mb-3">
          <i data-lucide="coffee" class="w-5 h-5" style="color:#9c7340;"></i>
          <span class="font-bold" style="color:#7a5010;">たとえるなら——</span>
        </div>
        <p class="text-gray-700">知り合いに「この書類、法律的に大丈夫？」と聞いて「大丈夫だよ！」と言われても、<strong>その人が弁護士でなければ自分でも確認が必要</strong>ですよね。<br>AIも同じ。自信がありそうな口調で答えてくれますが、根拠・バージョン・正確性は自分で確認する姿勢が大切です。</p>
      </div>

      <div class="ng-ok-grid mt-5">
        <div class="ng-card">
          <div class="flex items-center gap-2 mb-3">
            <i data-lucide="x-circle" class="w-5 h-5" style="color:#963030;"></i>
            <span class="font-bold" style="color:#6b1e1e;">やりがちなNG</span>
          </div>
          <ul class="space-y-2 text-gray-700 text-sm">
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
              <span>AIが「これで大丈夫」と言ったコードをレビューなしにそのまま提出</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
              <span>AIの回答を「絶対正しい答え」として上司や顧客にそのまま伝える</span>
            </li>
          </ul>
        </div>
        <div class="ok-card">
          <div class="flex items-center gap-2 mb-3">
            <i data-lucide="check-circle" class="w-5 h-5" style="color:#3d7a5a;"></i>
            <span class="font-bold" style="color:#2a5a3a;">こうしよう</span>
          </div>
          <ul class="space-y-2 text-gray-700 text-sm">
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#3d7a5a;">✓</span>
              <span>AIの出力は「たたき台」として受け取り、内容を自分で一度読んで確認する</span>
            </li>
            <li class="flex items-start gap-2">
              <span class="font-bold flex-shrink-0" style="color:#3d7a5a;">✓</span>
              <span>不確かな内容は「AIを使って調べました」と添えて、確認済みかどうかを明示する</span>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- うさ→さも（まとめ前の締め） -->
    <div class="flex items-start gap-4 mb-5 flex-row-reverse">
      <img src="./images/うさ-嬉しい.png" alt="うさ" class="char-img">
      <div class="bg-blue-50 border border-blue-200 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
        <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
        <p class="text-gray-700">全部のルールを暗記しなくて大丈夫だよ！「これ、社外の人が見てもOK？」「会社が承認してるツール？」「自分で内容を確認した？」——この3問さえ思い出せれば、大半のリスクは避けられる。今日はこの習慣だけ持ち帰って！</p>
      </div>
    </div>
    <div class="flex items-start gap-4 mb-8">
      <img src="./images/さも-わかった.png" alt="さも" class="char-img">
      <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
        <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
        <p class="text-gray-700">3問だけ！それなら覚えられそうです！</p>
      </div>
    </div>

    <!-- 30秒まとめ -->
    <div class="thirty-summary">
      <div class="flex items-center gap-3 mb-5">
        <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:#3d7a5a;">
          <i data-lucide="clock" class="w-6 h-6 text-white"></i>
        </div>
        <div>
          <h2 class="text-2xl font-bold text-gray-800">30秒まとめ</h2>
          <p class="text-sm font-medium" style="color:#3d7a5a;">「今日学んだこと、3つだけ言えますか？」</p>
        </div>
      </div>
      <div class="space-y-3">
        <div class="flex items-start gap-3 rounded-lg p-4" style="background:#fffef8; border:1px solid #c8b89a;">
          <span class="w-7 h-7 rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0" style="background:#3d7a5a; color:#f5f0e8;">1</span>
          <p class="font-medium text-gray-700">入力前に「社外の人が見てもOK？」と一問確認する</p>
        </div>
        <div class="flex items-start gap-3 rounded-lg p-4" style="background:#fffef8; border:1px solid #c8b89a;">
          <span class="w-7 h-7 rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0" style="background:#3d7a5a; color:#f5f0e8;">2</span>
          <p class="font-medium text-gray-700">会社が承認したツール・アカウントだけを業務に使う</p>
        </div>
        <div class="flex items-start gap-3 rounded-lg p-4" style="background:#fffef8; border:1px solid #c8b89a;">
          <span class="w-7 h-7 rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0" style="background:#3d7a5a; color:#f5f0e8;">3</span>
          <p class="font-medium text-gray-700">AIの出力は内容・ライセンス・セキュリティを確認してから使う</p>
        </div>
      </div>
    </div>

  </main>

  <script>lucide.createIcons();</script>
</body>
</html>
```
