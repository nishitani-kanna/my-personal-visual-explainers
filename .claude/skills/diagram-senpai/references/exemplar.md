# 模範解答パターン

## 成功する図解の構造

```
1. ヘッダー
   └─ カテゴリバッジ + タイトル + 一言サマリー

2. まず覚える3つ（必須）
   └─ 色分けされた番号カード × 3
   └─ 各カードに：タイトル + 1〜2文の説明

3. 先輩メモ（導入）
   └─ なぜ今これを知る必要があるかの現場感

4. 各論セクション × 2〜4
   └─ セクションヘッダー（アイコン + タイトル）
   └─ 用語解説ボックス（初出の専門用語に必ず）
   └─ たとえ話ボックス
   └─ NG/OK比較グリッド（行動の対比がある場合）
   └─ 先輩メモ（重要ポイント or 落とし穴）
   └─ フロー図 or ステップ（手順がある場合）

5. 先輩メモ（まとめへの橋渡し）
   └─ 「この3つだけ持って帰って」の一言

6. 30秒まとめ（必須・最後）
   └─ 番号カード × 3（動詞で締める短い文）
```

---

## 「まず覚える3つ」の書き方

### 良い例（AIセキュリティの場合）

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
    <div class="flex items-start gap-4 p-4 bg-blue-50 rounded-xl border-l-4 border-blue-500">
      <div class="w-9 h-9 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">1</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">個人情報・機密情報は入力しない</div>
        <p class="text-gray-600">氏名・会社名・取引先情報・設計書など、「社外に出していい？」と迷うものはAIに渡さない。</p>
      </div>
    </div>

    <div class="flex items-start gap-4 p-4 bg-teal-50 rounded-xl border-l-4 border-teal-500">
      <div class="w-9 h-9 bg-teal-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">2</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">入力前に「これ、外に出していい？」と一呼吸</div>
        <p class="text-gray-600">ルールを全部覚えなくていい。この一問を習慣にするだけで大半のリスクは避けられる。</p>
      </div>
    </div>

    <div class="flex items-start gap-4 p-4 bg-indigo-50 rounded-xl border-l-4 border-indigo-500">
      <div class="w-9 h-9 bg-indigo-500 text-white rounded-full flex items-center justify-center font-bold text-base flex-shrink-0">3</div>
      <div>
        <div class="font-bold text-gray-800 text-lg mb-1">会社のガイドラインを確認する</div>
        <p class="text-gray-600">ツールごとに使ってよいサービスが決まっている場合がある。まず社内ルールを確認してから使おう。</p>
      </div>
    </div>
  </div>
</div>
```

---

## 先輩メモの良い例

### 導入（現場感を伝える）

```
「AIツールを使いたい気持ちはすごくわかります。便利だし、業務効率も上がる。
でも『どこまで入力していいか』をちゃんと理解していないまま使うと、
後でひやっとする場面が出てくることがあるんです。
この図解で、安心して使えるようになりましょう。」
```

### 重要ポイント（落とし穴）

```
「よく見かけるのが、メールの返信文をそのままコピーして貼り付けるケース。
取引先の会社名や担当者名がそのまま入っていることが多くて、
意図せず情報を外部サービスに渡していることになります。
固有名詞は『〇〇社』『△△様』のように置き換えてから使うと安心ですよ。」
```

### まとめ（持ち帰り）

```
「難しいルールを全部覚えなくていい。
入力する前に1秒だけ『これ、社外に出していい情報？』と考える習慣ができれば、それだけで十分です。
今日から少しずつ始めてみましょう。」
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

## たとえ話の良い例

### 社会人・職場に結びつけるたとえ

```html
<div class="bg-amber-50 border border-amber-200 p-5 rounded-xl my-5">
  <div class="flex items-center gap-2 mb-3">
    <i data-lucide="coffee" class="w-5 h-5 text-amber-600"></i>
    <span class="font-bold text-amber-800">たとえるなら——</span>
  </div>
  <p class="text-gray-700">
    会社のコピー機に書類を置き忘れる感覚に似ています。<br>
    うっかり社外の人が拾えてしまうような場所（＝AIの入力欄）に、
    大事な書類（＝機密情報）を置かないようにしよう、ということです。
  </p>
</div>
```

---

## 品質チェックリスト

作成後、以下を全て確認する:

### 構成・内容
- [ ] 「まず覚える3つ」セクションがある（3項目ちょうど）
- [ ] 末尾に「30秒まとめ」がある（3項目ちょうど）
- [ ] 先輩メモが3箇所ある（導入・重要ポイント・まとめ前）
- [ ] 専門用語が最初に出てきたとき、用語解説ボックスがある
- [ ] たとえ話が3つ以上ある（職場・日常・デジタルなど複数種類）

### デザイン
- [ ] Lucide iconのみ使用（絵文字を使っていない）
- [ ] 外部画像ファイルを参照していない
- [ ] スマホでも読みやすい（`md:` breakpointで対応）
- [ ] `<script>` タグはLucide初期化のみ

### トーン
- [ ] 30秒まとめの各項目が動詞で終わる短文になっている
- [ ] 先輩メモが命令口調になっていない
- [ ] 読者をレベルでラベリングする表現がない（「初心者向け」等）
- [ ] セキュリティ系の表現が怖がらせるよりも「こうすれば大丈夫」になっている
