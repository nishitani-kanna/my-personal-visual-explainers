# HTML構造ガイド

## 基本テンプレート

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>【図解タイトル】</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700;900&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Noto Sans JP', 'Inter', sans-serif;
    }

    /* ヘッダーグラデーション */
    .header-gradient {
      background: linear-gradient(135deg, #1e3a5f 0%, #1d4ed8 60%, #0891b2 100%);
    }

    /* セクションカード */
    .section-card {
      background: white;
      border-radius: 1rem;
      box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.08);
      padding: 2rem;
      margin-bottom: 2rem;
    }

    /* キャラクター吹き出し（うさ・わらび：右側） */
    .bubble-right {
      background: #eff6ff;
      border: 1.5px solid #bfdbfe;
      border-radius: 1rem;
      border-top-right-radius: 0;
      padding: 1rem 1.25rem;
    }

    /* キャラクター吹き出し（さも：左側） */
    .bubble-left {
      background: #fffbeb;
      border: 1.5px solid #fde68a;
      border-radius: 1rem;
      border-top-left-radius: 0;
      padding: 1rem 1.25rem;
    }

    /* キャラクター吹き出し（ラグ：右側・クール） */
    .bubble-lag {
      background: #f8fafc;
      border: 1.5px solid #cbd5e1;
      border-radius: 1rem;
      border-top-right-radius: 0;
      padding: 1rem 1.25rem;
    }

    /* キャラクター吹き出し（わらび：右側・ベテラン） */
    .bubble-warabi {
      background: #f0fdf4;
      border: 1.5px solid #bbf7d0;
      border-radius: 1rem;
      border-top-right-radius: 0;
      padding: 1rem 1.25rem;
    }

    /* 用語解説ボックス */
    .term-explain {
      background: linear-gradient(135deg, #f3e8ff 0%, #e9d5ff 100%);
      border-left: 4px solid #9333ea;
      padding: 1.25rem 1.5rem;
      border-radius: 0.75rem;
      margin: 1.5rem 0;
    }

    /* 先輩メモ */
    .senpai-memo {
      background: #eff6ff;
      border-left: 4px solid #2563eb;
      border-radius: 0 0.75rem 0.75rem 0;
      padding: 1.25rem 1.5rem;
      margin: 1.5rem 0;
    }

    /* セキュリティ警告（注意レベル）*/
    .security-caution {
      background: linear-gradient(135deg, #fffbeb 0%, #fef3c7 100%);
      border-left: 4px solid #d97706;
      padding: 1.25rem 1.5rem;
      border-radius: 0 0.75rem 0.75rem 0;
      margin: 1.5rem 0;
    }

    /* セキュリティ警告（危険レベル）*/
    .security-danger {
      background: linear-gradient(135deg, #fef2f2 0%, #fee2e2 100%);
      border-left: 4px solid #dc2626;
      padding: 1.25rem 1.5rem;
      border-radius: 0 0.75rem 0.75rem 0;
      margin: 1.5rem 0;
    }

    /* 30秒まとめ */
    .thirty-summary {
      background: linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%);
      border: 2px solid #16a34a;
      border-radius: 1rem;
      padding: 2rem;
      margin-bottom: 2rem;
    }

    /* コードブロック */
    .code-block {
      background: #1e293b;
      color: #e2e8f0;
      padding: 1.25rem 1.5rem;
      border-radius: 0.75rem;
      overflow-x: auto;
      font-family: 'Fira Code', 'Courier New', monospace;
      font-size: 0.875rem;
      line-height: 1.7;
    }

    /* NG/OK 比較グリッド */
    .ng-ok-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin: 1.5rem 0;
    }
    @media (max-width: 640px) {
      .ng-ok-grid { grid-template-columns: 1fr; }
    }
    .ng-card {
      background: #fef2f2;
      border: 1.5px solid #fca5a5;
      border-radius: 0.75rem;
      padding: 1.25rem;
    }
    .ok-card {
      background: #f0fdf4;
      border: 1.5px solid #86efac;
      border-radius: 0.75rem;
      padding: 1.25rem;
    }

    @media print {
      .section-card { box-shadow: none; border: 1px solid #e5e7eb; }
      .header-gradient { background: #1d4ed8 !important; }
    }
  </style>
</head>
<body class="bg-slate-50">

  <!-- ヘッダー -->
  <header class="header-gradient text-white py-10">
    <div class="max-w-3xl mx-auto px-6">
      <div class="text-sm font-medium opacity-75 mb-1 tracking-wide">【カテゴリ（例：セキュリティ / 開発ツール / IT基礎）】</div>
      <h1 class="text-3xl md:text-4xl font-black leading-tight">【図解タイトル】</h1>
      <p class="mt-3 text-base md:text-lg opacity-90">【一言サマリー：このトピックの核心を1文で】</p>
    </div>
  </header>

  <!-- メインコンテンツ -->
  <main class="max-w-3xl mx-auto px-6 py-8">

    <!-- ★ まず覚える3つ（必須セクション） -->
    <!-- ★ 各論セクション × 2〜4 -->
    <!-- ★ 30秒まとめ（必須セクション・最後に配置） -->

  </main>

  <script>lucide.createIcons();</script>
</body>
</html>
```

---

## セクションパターン

### まず覚える3つ

```html
<div class="section-card">
  <div class="flex items-center gap-3 mb-6">
    <div class="w-12 h-12 bg-gradient-to-br from-blue-600 to-cyan-500 rounded-xl flex items-center justify-center flex-shrink-0">
      <i data-lucide="list-checks" class="w-6 h-6 text-white"></i>
    </div>
    <div>
      <h2 class="text-2xl font-bold text-gray-800">まず覚える3つ</h2>
      <p class="text-gray-500 text-sm">これだけ押さえれば大丈夫</p>
    </div>
  </div>

  <div class="space-y-4">
    <!-- 1つ目 -->
    <div class="flex items-start gap-4 p-4 bg-blue-50 rounded-xl border-l-4 border-blue-500">
      <div class="w-9 h-9 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">1</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。1〜2文。専門用語は使わない。】</p>
      </div>
    </div>

    <!-- 2つ目 -->
    <div class="flex items-start gap-4 p-4 bg-teal-50 rounded-xl border-l-4 border-teal-500">
      <div class="w-9 h-9 bg-teal-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">2</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。】</p>
      </div>
    </div>

    <!-- 3つ目 -->
    <div class="flex items-start gap-4 p-4 bg-indigo-50 rounded-xl border-l-4 border-indigo-500">
      <div class="w-9 h-9 bg-indigo-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">3</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。】</p>
      </div>
    </div>
  </div>
</div>
```

### キャラクター吹き出し（導入・重要ポイント・まとめで使用）

詳細 → [persona-guide.md](persona-guide.md)

```html
<!-- さも→うさ：疑問→説明パターン（導入・各セクション冒頭） -->
<div class="flex items-start gap-4 mb-4">
  <img src="./images/さも-ニコニコ.png" alt="さも" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bubble-left flex-1">
    <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
    <p class="text-gray-700">【読者が抱きそうな疑問・「え、これってどういうこと？」】</p>
  </div>
</div>
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/うさ-説明中.png" alt="うさ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bubble-right flex-1">
    <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
    <p class="text-gray-700">【説明。たとえ話を使って平易に。「〇〇みたいなイメージです」】</p>
  </div>
</div>

<!-- ラグ：セキュリティ警告（重要ポイント近く） -->
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/ラグ-注意.png" alt="ラグ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bubble-lag flex-1">
    <p class="text-sm font-bold text-slate-600 mb-1">ラグ</p>
    <p class="text-gray-700">【短く端的に。「それ、〇〇のリスクがある。△△に変えるだけで防げる」】</p>
  </div>
</div>

<!-- うさ→さも：励まし→わかった（まとめ前） -->
<div class="flex items-start gap-4 mb-4 flex-row-reverse">
  <img src="./images/うさ-励まし.png" alt="うさ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bubble-right flex-1">
    <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
    <p class="text-gray-700">【「全部覚えなくていい。この3つだけ持ち帰って！」系の締め】</p>
  </div>
</div>
<div class="flex items-start gap-4 mb-5">
  <img src="./images/さも-わかった.png" alt="さも" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bubble-left flex-1">
    <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
    <p class="text-gray-700">【「なるほど！それなら覚えられそうです！」系の前向きな反応】</p>
  </div>
</div>
```

### 用語解説ボックス

```html
<div class="term-explain">
  <div class="flex items-start gap-3">
    <i data-lucide="lightbulb" class="w-6 h-6 text-purple-600 flex-shrink-0 mt-0.5"></i>
    <div>
      <div class="font-bold text-purple-800 text-lg">「【用語】」ってなに？</div>
      <p class="text-gray-700 mt-1">
        【やさしい言葉での説明。たとえ話を含める。「この図解では〜と呼びます」まで書いてOK。】
      </p>
    </div>
  </div>
</div>
```

### セキュリティ警告（注意）

```html
<div class="security-caution">
  <div class="flex items-start gap-3">
    <i data-lucide="triangle-alert" class="w-5 h-5 text-amber-600 flex-shrink-0 mt-0.5"></i>
    <div>
      <div class="font-bold text-amber-800 mb-1">⚠ 気をつけて</div>
      <p class="text-gray-700">【注意事項。怖がらせるのではなく、具体的に何をするか/しないかを伝える。】</p>
    </div>
  </div>
</div>
```

### セキュリティ警告（危険）

```html
<div class="security-danger">
  <div class="flex items-start gap-3">
    <i data-lucide="shield-x" class="w-5 h-5 text-red-600 flex-shrink-0 mt-0.5"></i>
    <div>
      <div class="font-bold text-red-800 mb-1">絶対にやってはいけないこと</div>
      <p class="text-gray-700">【具体的なNG行動と、なぜいけないかの理由。】</p>
    </div>
  </div>
</div>
```

### NG/OK 比較グリッド

```html
<div class="ng-ok-grid">
  <div class="ng-card">
    <div class="flex items-center gap-2 mb-3">
      <i data-lucide="x-circle" class="w-5 h-5 text-red-500"></i>
      <span class="font-bold text-red-700">やりがちなNG</span>
    </div>
    <ul class="space-y-2 text-gray-700">
      <li class="flex items-start gap-2">
        <span class="text-red-500 font-bold flex-shrink-0">✗</span>
        <span>【NG例】</span>
      </li>
    </ul>
  </div>
  <div class="ok-card">
    <div class="flex items-center gap-2 mb-3">
      <i data-lucide="check-circle" class="w-5 h-5 text-green-600"></i>
      <span class="font-bold text-green-700">こうしよう</span>
    </div>
    <ul class="space-y-2 text-gray-700">
      <li class="flex items-start gap-2">
        <span class="text-green-600 font-bold flex-shrink-0">✓</span>
        <span>【OK例】</span>
      </li>
    </ul>
  </div>
</div>
```

### たとえ話ボックス

```html
<div class="bg-amber-50 border border-amber-200 p-5 rounded-xl my-5">
  <div class="flex items-center gap-2 mb-3">
    <i data-lucide="coffee" class="w-5 h-5 text-amber-600"></i>
    <span class="font-bold text-amber-800">たとえるなら——</span>
  </div>
  <p class="text-gray-700">【身近なたとえ。職場・日常生活のシーンに結びつける。】</p>
</div>
```

### 30秒まとめ（必須・最後に配置）

```html
<div class="thirty-summary">
  <div class="flex items-center gap-3 mb-5">
    <div class="w-12 h-12 bg-green-600 rounded-xl flex items-center justify-center flex-shrink-0">
      <i data-lucide="clock" class="w-6 h-6 text-white"></i>
    </div>
    <div>
      <h2 class="text-2xl font-bold text-gray-800">30秒まとめ</h2>
      <p class="text-green-700 text-sm font-medium">「今日学んだこと、3つだけ言えますか？」</p>
    </div>
  </div>

  <div class="space-y-3">
    <div class="flex items-start gap-3 bg-white rounded-lg p-4 shadow-sm">
      <span class="w-7 h-7 bg-green-500 text-white rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0">1</span>
      <p class="text-gray-700 font-medium">【ポイント1。短く・動詞で締める。例：「AIへの入力に個人情報を含めない」】</p>
    </div>
    <div class="flex items-start gap-3 bg-white rounded-lg p-4 shadow-sm">
      <span class="w-7 h-7 bg-green-500 text-white rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0">2</span>
      <p class="text-gray-700 font-medium">【ポイント2。】</p>
    </div>
    <div class="flex items-start gap-3 bg-white rounded-lg p-4 shadow-sm">
      <span class="w-7 h-7 bg-green-500 text-white rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0">3</span>
      <p class="text-gray-700 font-medium">【ポイント3。】</p>
    </div>
  </div>
</div>
```

---

## Lucide Icon よく使うアイコン

| 用途 | アイコン名 | コード |
|-----|----------|--------|
| セキュリティOK | `shield-check` | `<i data-lucide="shield-check" class="w-6 h-6 text-green-600"></i>` |
| セキュリティNG | `shield-x` | `<i data-lucide="shield-x" class="w-6 h-6 text-red-500"></i>` |
| 鍵・パスワード | `lock` | `<i data-lucide="lock" class="w-6 h-6 text-gray-600"></i>` |
| 警告 | `triangle-alert` | `<i data-lucide="triangle-alert" class="w-6 h-6 text-amber-600"></i>` |
| チェックOK | `check-circle` | `<i data-lucide="check-circle" class="w-6 h-6 text-green-600"></i>` |
| バツ | `x-circle` | `<i data-lucide="x-circle" class="w-6 h-6 text-red-500"></i>` |
| ヒント | `lightbulb` | `<i data-lucide="lightbulb" class="w-6 h-6 text-yellow-500"></i>` |
| 時計 | `clock` | `<i data-lucide="clock" class="w-6 h-6 text-green-600"></i>` |
| メモ | `message-square` | `<i data-lucide="message-square" class="w-5 h-5 text-blue-600"></i>` |
| コード | `code` | `<i data-lucide="code" class="w-6 h-6 text-purple-500"></i>` |
| ファイル | `file-text` | `<i data-lucide="file-text" class="w-6 h-6 text-blue-500"></i>` |
| リスト | `list-checks` | `<i data-lucide="list-checks" class="w-6 h-6 text-blue-600"></i>` |
| 人 | `user` | `<i data-lucide="user" class="w-6 h-6 text-gray-600"></i>` |
| 矢印 | `arrow-right` | `<i data-lucide="arrow-right" class="w-5 h-5 text-gray-400"></i>` |
| フロー | `git-branch` | `<i data-lucide="git-branch" class="w-6 h-6 text-indigo-500"></i>` |
| クラウド | `cloud` | `<i data-lucide="cloud" class="w-6 h-6 text-blue-400"></i>` |
| メール | `mail` | `<i data-lucide="mail" class="w-6 h-6 text-gray-600"></i>` |
| PCスマホ | `monitor` | `<i data-lucide="monitor" class="w-6 h-6 text-gray-700"></i>` |
| コーヒー | `coffee` | `<i data-lucide="coffee" class="w-5 h-5 text-amber-600"></i>` |

---

## フロー図（ステップ）

```html
<div class="flex flex-col md:flex-row items-stretch gap-3 my-6">
  <!-- ステップ1 -->
  <div class="flex-1 bg-blue-50 border border-blue-200 rounded-xl p-4 text-center">
    <div class="w-10 h-10 bg-blue-500 rounded-full text-white font-bold flex items-center justify-center mx-auto mb-2">1</div>
    <i data-lucide="【アイコン】" class="w-7 h-7 text-blue-600 mx-auto mb-2"></i>
    <div class="font-bold text-gray-800">【ステップ名】</div>
    <p class="text-sm text-gray-500 mt-1">【説明】</p>
  </div>

  <div class="flex items-center justify-center">
    <i data-lucide="arrow-right" class="w-6 h-6 text-gray-400 hidden md:block"></i>
    <i data-lucide="arrow-down" class="w-6 h-6 text-gray-400 md:hidden"></i>
  </div>

  <!-- ステップ2（色をteal等に変える） -->
  <div class="flex-1 bg-teal-50 border border-teal-200 rounded-xl p-4 text-center">
    ...
  </div>
</div>
```

---

## セクションヘッダー（共通パターン）

```html
<div class="flex items-center gap-3 mb-6">
  <div class="w-12 h-12 bg-【色】-100 rounded-xl flex items-center justify-center flex-shrink-0">
    <i data-lucide="【アイコン名】" class="w-6 h-6 text-【色】-600"></i>
  </div>
  <div>
    <h2 class="text-2xl font-bold text-gray-800">【セクションタイトル】</h2>
    <p class="text-gray-500 text-sm">【サブタイトル】</p>
  </div>
</div>
```
