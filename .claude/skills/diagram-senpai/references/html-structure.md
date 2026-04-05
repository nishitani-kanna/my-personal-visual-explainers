# HTML構造ガイド

## デザインコンセプト

**ノート風・クリーンカードスタイル**の学習テキスト。
- ベースカラー：ベージュ（`#f5f0e8`）
- テキスト：ダークブラウン（`#2d1f0e`）
- カード：クリーム白（`#fffef8`）
- アクセント：チャコール（`#3d3530`）
- ボーダー：薄茶（`#c8b89a`）

---

## 基本CSS（`<style>` タグにそのまま貼る）

Tailwind CDN と組み合わせて使う。このCSSをそのまま流用し、色だけこのガイドのパレットに変換する。

```css
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
```

---

## HTMLスケルトン

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
    /* ↑ 上記CSSをここに貼る */
  </style>
</head>
<body>

  <header class="header-gradient text-white py-10">
    <div class="max-w-3xl mx-auto px-6">
      <div class="text-sm font-medium opacity-75 mb-2 tracking-wide uppercase">【カテゴリ（例：セキュリティ / 開発ツール / IT基礎）】</div>
      <h1 class="text-3xl md:text-4xl font-black leading-tight">【図解タイトル】</h1>
      <p class="mt-3 text-base md:text-lg opacity-90">【一言サマリー：このトピックの核心を1文で】</p>
    </div>
  </header>

  <main class="max-w-3xl mx-auto px-6 py-8">
    <!-- ★ まず覚える3つ（必須セクション） -->
    <!-- ★ キャラクター対話（導入）: さも→うさ で「なぜ大事か」を引き出す -->
    <!-- ★ 各論セクション × 2〜4 -->
    <!-- ★ キャラクター対話（重要ポイント）: さも→ラグ or うさ→さも で落とし穴を指摘 -->
    <!-- ★ キャラクター対話（まとめ前）: うさ→さも で「これだけ持って帰って」 -->
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
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。1〜2文。専門用語は使わない。】</p>
      </div>
    </div>

    <div class="flex items-start gap-4 p-4 bg-teal-50 rounded-xl border-l-4 border-teal-500">
      <div class="w-9 h-9 rounded-full flex items-center justify-center font-bold flex-shrink-0 text-white" style="background:#2d1f0e;">2</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。】</p>
      </div>
    </div>

    <div class="flex items-start gap-4 p-4 rounded-xl border-l-4" style="background:#fdf6e8; border-color:#9c7340;">
      <div class="w-9 h-9 rounded-full flex items-center justify-center font-bold flex-shrink-0 text-white" style="background:#2d1f0e;">3</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">【ポイントタイトル】</div>
        <p class="text-gray-600">【説明。】</p>
      </div>
    </div>
  </div>
</div>
```

### キャラクター吹き出し（対話パターン）

テキスト解説の代わりに、キャラクター対話でポイントを伝える。
各論セクションの中や、セクション間のつなぎとして使う。

詳細パターン → [persona-guide.md](persona-guide.md)

```html
<!-- さも→うさ：疑問→説明パターン -->
<div class="flex items-start gap-4 mb-4">
  <img src="./images/さも-ニコニコ.png" alt="さも" class="char-img">
  <div class="flex-1 rounded-2xl rounded-tl-none px-5 py-4" style="background:#fdf6e8; border:1.5px solid #d4b88a;">
    <p class="text-sm font-bold mb-1" style="color:#9c7340;">さも</p>
    <p class="text-gray-700">【読者が抱きそうな疑問・「え、これってどういうこと？」】</p>
  </div>
</div>
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/うさ-説明中.png" alt="うさ" class="char-img">
  <div class="flex-1 rounded-2xl rounded-tr-none px-5 py-4" style="background:#eef2fb; border:1.5px solid #94afd4;">
    <p class="text-sm font-bold mb-1" style="color:#3b5fa0;">うさ</p>
    <p class="text-gray-700">【説明。たとえ話を使って平易に。「〇〇みたいなイメージだよ！」「要は〜ってこと」】</p>
  </div>
</div>
```

### セクションヘッダー（共通）

```html
<div class="flex items-center gap-3 mb-6">
  <div class="w-12 h-12 rounded-xl flex items-center justify-center flex-shrink-0" style="background:【背景色】;">
    <i data-lucide="【アイコン名】" class="w-6 h-6" style="color:【アイコン色】;"></i>
  </div>
  <div>
    <h2 class="text-2xl font-bold text-gray-800">【セクションタイトル】</h2>
    <p class="text-gray-500 text-sm">【サブタイトル】</p>
  </div>
</div>
```

アイコンコンテナのカラーバリエーション：
- NG・セキュリティ警告系：`background:#f5ede8;` + アイコン `color:#963030;`
- OK・確認ステップ系：`background:#e8f5ee;` + アイコン `color:#3d7a5a;`
- 情報・知識系：`background:#eef2fb;` + アイコン `color:#3b5fa0;`
- 汎用・ダーク：`background:#2d1f0e;` + アイコン `color:#f5f0e8;`（`text-white`）

### 用語解説ボックス

```html
<div class="term-explain">
  <div class="flex items-start gap-3">
    <i data-lucide="lightbulb" class="w-6 h-6 flex-shrink-0 mt-0.5" style="color:#9c7340;"></i>
    <div>
      <div class="font-bold text-lg" style="color:#7a5010;">「【用語】」ってなに？</div>
      <p class="text-gray-700 mt-1">【やさしい言葉での説明。たとえ話を含める。】</p>
    </div>
  </div>
</div>
```

### たとえ話ボックス

```html
<div class="p-5 rounded-xl my-5" style="background:#fdf6e8; border:1.5px solid #d4b88a;">
  <div class="flex items-center gap-2 mb-3">
    <i data-lucide="coffee" class="w-5 h-5" style="color:#9c7340;"></i>
    <span class="font-bold" style="color:#7a5010;">たとえるなら——</span>
  </div>
  <p class="text-gray-700">【身近なたとえ。職場・日常生活のシーンに結びつける。】</p>
</div>
```

### NG/OK 比較グリッド（基本）

```html
<div class="ng-ok-grid">
  <div class="ng-card">
    <div class="flex items-center gap-2 mb-3">
      <i data-lucide="x-circle" class="w-5 h-5" style="color:#963030;"></i>
      <span class="font-bold" style="color:#6b1e1e;">やりがちなNG</span>
    </div>
    <ul class="space-y-2 text-gray-700 text-sm">
      <li class="flex items-start gap-2">
        <span class="font-bold flex-shrink-0" style="color:#963030;">✗</span>
        <span>【NG例】</span>
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
        <span>【OK例】</span>
      </li>
    </ul>
  </div>
</div>
```

### NG/OK 比較グリッド（チャットUIモック付き）

AIへの入力のNG/OKなど、具体的な入力例を見せたいときに使う。

```html
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
          【NGな入力例（固有名詞・機密情報が入っている）】
        </div>
      </div>
    </div>
    <p class="text-xs font-medium" style="color:#963030;">【何がNGかの一言】</p>
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
          【OKな入力例（固有名詞をダミーに置き換えた）】
        </div>
      </div>
    </div>
    <p class="text-xs font-medium" style="color:#3d7a5a;">【何がOKかの一言】</p>
  </div>
</div>
```

### 情報グリッド（カテゴリ別リスト）

複数カテゴリの情報を並べるとき（例：「入力してはいけない情報の種類」）。

```html
<div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-6">
  <div class="rounded-xl p-4" style="background:#fdf0f0; border:1px solid #e0a0a0;">
    <div class="flex items-center gap-2 mb-2">
      <i data-lucide="【アイコン】" class="w-5 h-5" style="color:#963030;"></i>
      <span class="font-bold" style="color:#6b1e1e;">【カテゴリ名】</span>
    </div>
    <ul class="text-sm text-gray-600 space-y-1">
      <li>【項目1】</li>
      <li>【項目2】</li>
    </ul>
  </div>
  <!-- 他のカテゴリ... -->
</div>
```

カテゴリカードの色バリエーション：
- 危険・禁止系：`background:#fdf0f0; border:1px solid #e0a0a0;` + アイコン `color:#963030;`
- 注意・機密系：`background:#fdf6e8; border:1px solid #d4b88a;` + アイコン `color:#9c7340;`
- 認証・キー系：`background:#f7f0ff; border:1px solid #c4b0e0;` + アイコン `color:#7c5cbf;`

### フロー図（確認ステップ）

```html
<div class="flex flex-col md:flex-row items-stretch gap-3 mb-6">
  <div class="flex-1 rounded-xl p-4 text-center" style="background:#eef5ee; border:1.5px solid #90c4a0;">
    <div class="w-10 h-10 rounded-full font-bold flex items-center justify-center mx-auto mb-2 text-white" style="background:#3d7a5a;">1</div>
    <i data-lucide="【アイコン】" class="w-6 h-6 mx-auto mb-2" style="color:#3d7a5a;"></i>
    <div class="font-bold text-gray-800 text-sm">【ステップ名】</div>
    <p class="text-xs text-gray-500 mt-1">【説明】</p>
  </div>

  <div class="flex items-center justify-center py-2 md:py-0">
    <i data-lucide="arrow-right" class="w-6 h-6 hidden md:block" style="color:#a09080;"></i>
    <i data-lucide="arrow-down" class="w-6 h-6 md:hidden" style="color:#a09080;"></i>
  </div>

  <div class="flex-1 rounded-xl p-4 text-center" style="background:#eef2fb; border:1.5px solid #94afd4;">
    <div class="w-10 h-10 rounded-full font-bold flex items-center justify-center mx-auto mb-2 text-white" style="background:#3b5fa0;">2</div>
    <i data-lucide="【アイコン】" class="w-6 h-6 mx-auto mb-2" style="color:#3b5fa0;"></i>
    <div class="font-bold text-gray-800 text-sm">【ステップ名】</div>
    <p class="text-xs text-gray-500 mt-1">【説明】</p>
  </div>

  <!-- 矢印 + ステップ3以降... -->
</div>
```

### 確認カード（3列グリッド）

内容を3つの視点で整理するとき（例：「AIの出力確認の3観点」）。

```html
<div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-6">
  <div class="rounded-xl p-4 text-center" style="background:#f5f0e8; border:1px solid #c8b89a;">
    <i data-lucide="【アイコン】" class="w-7 h-7 mx-auto mb-2" style="color:#6b5744;"></i>
    <div class="font-bold text-gray-800 text-sm mb-1">【タイトル】</div>
    <p class="text-xs text-gray-500">【説明】</p>
  </div>
  <!-- 他のカード... -->
</div>
```

### 30秒まとめ（必須・最後に配置）

```html
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
      <p class="font-medium text-gray-700">【ポイント1。短く・動詞で締める。】</p>
    </div>
    <div class="flex items-start gap-3 rounded-lg p-4" style="background:#fffef8; border:1px solid #c8b89a;">
      <span class="w-7 h-7 rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0" style="background:#3d7a5a; color:#f5f0e8;">2</span>
      <p class="font-medium text-gray-700">【ポイント2。】</p>
    </div>
    <div class="flex items-start gap-3 rounded-lg p-4" style="background:#fffef8; border:1px solid #c8b89a;">
      <span class="w-7 h-7 rounded-full flex items-center justify-center font-bold text-sm flex-shrink-0" style="background:#3d7a5a; color:#f5f0e8;">3</span>
      <p class="font-medium text-gray-700">【ポイント3。】</p>
    </div>
  </div>
</div>
```

---

## Lucide Icon よく使うアイコン

| 用途 | アイコン名 |
|-----|----------|
| セキュリティOK | `shield-check` |
| セキュリティNG | `shield-x` |
| 鍵・パスワード | `key` / `lock` |
| 警告 | `triangle-alert` |
| チェックOK | `check-circle` |
| バツ | `x-circle` |
| ヒント | `lightbulb` |
| 時計 | `clock` |
| メモ | `message-square` |
| コード | `code` |
| ファイル | `file-text` |
| リスト | `list-checks` |
| 人 | `user` |
| 矢印右 | `arrow-right` |
| 矢印下 | `arrow-down` |
| フロー | `git-branch` |
| 検索 | `search` |
| スケール | `scale` |
| モニター | `monitor` |
| コーヒー | `coffee` |
| クラウド | `cloud` |
| メール | `mail` |
