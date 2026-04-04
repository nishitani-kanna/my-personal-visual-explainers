# キャラクターガイド

## キャラクター紹介

| キャラ | 名前 | 役割 | 性格 |
|--------|------|------|------|
| ベージュうさぎ | **うさ** | IT知識を教えてくれる先輩 | 物知りで温かく責任感が強い中堅エンジニア。自分もAI・ITを日々勉強中。「一緒に頑張ろう」タイプ |
| 白サモエド | **さも** | 新人の代弁者 | ニコニコ穏やか。知識はまだ浅くうっかりしがち。でも素直に学んでいく愛すべきポンコツ |
| グレー白ラグドール | **ラグ** | セキュリティ担当 | 口数は少ないが端的に大切なことを伝える。クールに見えるが実はよく周りを見ていて、みんなに信頼されている |
| カラフルオウム | **わらび** | ベテランエンジニア | 出番は少ないが、過去の経験・歴史的な背景が必要な場面で登場。落ち着いた知恵袋 |

---

## 表情一覧と使用シーン

### うさ（先輩・IT知識担当）

| 表情 | ファイル名 | 使用シーン |
|------|-----------|----------|
| 標準 | `うさ-標準.png` | 通常の説明・導入 |
| 説明中 | `うさ-説明中.png` | 重要ポイントを教える・「ここがポイントです」 |
| 心配 | `うさ-心配.png` | 落とし穴の指摘・「これ気をつけてほしいんですが…」 |
| 嬉しい | `うさ-嬉しい.png` | まとめ・励まし・「一緒に頑張ろう！」 |

### さも（新人代弁者）

| 表情 | ファイル名 | 使用シーン |
|------|-----------|----------|
| ニコニコ | `さも-ニコニコ.png` | 疑問を投げかける・通常の反応 |
| 焦り | `さも-焦り.png` | 「急いでやったら…」「間に合わない！」 |
| やらかした | `さも-やらかした.png` | NG行動の描写・「こういうことやっちゃいがちです」 |
| わかった | `さも-わかった.png` | 理解した瞬間・「なるほど！」 |

### ラグ（セキュリティ担当）

| 表情 | ファイル名 | 使用シーン |
|------|-----------|----------|
| 無表情 | `ラグ-無表情.png` | セキュリティに関する落ち着いたコメント |
| 注意 | `ラグ-注意.png` | 重要なセキュリティ警告・「これは必ず確認して」 |

### わらび（ベテラン）

| 表情 | ファイル名 | 使用シーン |
|------|-----------|----------|
| 標準 | `わらび-標準.png` | 歴史的背景・過去の経験談・「昔はこうだったんだけど…」 |

---

## 画像パス

HTML内での参照パス（デプロイ時のパスに合わせること）:

```html
<img src="./images/うさ-標準.png" alt="うさ" class="w-20 h-20 object-contain flex-shrink-0">
```

スキル内での保存場所:
```
.claude/skills/diagram-senpai/character-images/
```

デプロイ時にコピーが必要。SKILL.md の Phase 8 参照。

---

## 対話パターン

### パターン1：さも→うさ（疑問→説明）

```html
<!-- さも：疑問を投げかける -->
<div class="flex items-start gap-4 mb-5">
  <img src="./images/さも-標準.png" alt="さも" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
    <p class="text-gray-700">【疑問・読者が思いそうな「え、それってどういうこと？」】</p>
  </div>
</div>

<!-- うさ：説明する -->
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/うさ-アドバイス.png" alt="うさ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-blue-50 border border-blue-200 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
    <p class="text-gray-700">【説明。たとえ話を使って平易に。「〇〇みたいなイメージです」】</p>
  </div>
</div>
```

### パターン2：さも→ラグ（セキュリティ警告場面）

```html
<!-- さも：うっかりNG行動 -->
<div class="flex items-start gap-4 mb-5">
  <img src="./images/さも-やらかした.png" alt="さも" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
    <p class="text-gray-700">【「こういうことやっちゃいそう…」なNG行動の描写。自虐的に】</p>
  </div>
</div>

<!-- ラグ：セキュリティ的に注意 -->
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/ラグ-警告.png" alt="ラグ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-slate-50 border border-slate-300 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-slate-600 mb-1">ラグ</p>
    <p class="text-gray-700">【短く、端的に。「それ、〇〇のリスクがある。△△に変えるだけで防げる」】</p>
  </div>
</div>
```

### パターン3：うさ→さも（まとめ・励まし）

```html
<!-- うさ：「これだけ覚えて」 -->
<div class="flex items-start gap-4 mb-5 flex-row-reverse">
  <img src="./images/うさ-励まし.png" alt="うさ" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-blue-50 border border-blue-200 rounded-2xl rounded-tr-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-blue-700 mb-1">うさ</p>
    <p class="text-gray-700">【「難しいルールは全部覚えなくていい。この3つだけ持ち帰って！」系の締め】</p>
  </div>
</div>

<!-- さも：理解した！ -->
<div class="flex items-start gap-4 mb-5">
  <img src="./images/さも-わかった.png" alt="さも" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-amber-50 border border-amber-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-amber-700 mb-1">さも</p>
    <p class="text-gray-700">【「なるほど！それなら覚えられそうです！」系の前向きな反応】</p>
  </div>
</div>
```

### パターン4：わらびの登場（ベテランの一言）

```html
<!-- わらび：歴史・経験談 -->
<div class="flex items-start gap-4 mb-5">
  <img src="./images/わらび-標準.png" alt="わらび" class="w-20 h-20 object-contain flex-shrink-0">
  <div class="bg-green-50 border border-green-200 rounded-2xl rounded-tl-none px-5 py-4 flex-1">
    <p class="text-sm font-bold text-green-700 mb-1">わらび</p>
    <p class="text-gray-700">【「昔はこういう事故があってね…」「現場では実際こんなことが起きた」的な経験談】</p>
  </div>
</div>
```

---

## セリフの書き方

### うさ
- 一人称なし（使わなくていい）
- 丁寧語ベース。でも硬すぎない
- 「〜みたいなイメージです」「〜から始めましょう」「一緒に確認しましょう」
- 自分も勉強中であることが滲み出る表現を使う：「私もよく確認するんですが…」「最近これ改めて気をつけてて…」

### さも
- 一人称：「ぼく」または使わない
- 素直で明るい。「えっ」「なるほど！」「それって…」
- NG場面では反省しつつもニコニコ感が残る：「やっちゃった…でも次から気をつけます！」

### ラグ
- 短く。1〜2文で完結
- 「〜だから、〜するといい」構造
- 感嘆符は使わない。冷静に事実を伝える

### わらび
- 「〜だったんだよね」「経験的に言うと…」「昔ねえ…」
- 少し老練な語り口。でも怖くない
- 出番は1図解に1〜2回まで

---

## 配置ルール

1. **さも は左、うさ・ラグ・わらび は右** に配置（`flex-row-reverse` を使う）
2. **吹き出しは角丸**。左側キャラは `rounded-tl-none`、右側は `rounded-tr-none`
3. **画像サイズ**: `w-20 h-20`（80px）を基本とする
4. **対話は連続2〜3往復まで**。それ以上は図解のほうが伝わる
5. **わらびはセクション横断で最大2回まで**
