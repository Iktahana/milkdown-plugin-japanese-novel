## 🌸 milkdown-plugin-novel-japanese

このプラグインは、日本語小説家のために設計された Milkdown 拡張機能です。Web エディタにおける日本語特有のレイアウト（縦書き）や、ルビの入力、原稿用紙換算などの課題を解決することを目的としています。

✨ 主な機能
縦書き (Vertical Writing) モード: CSS writing-mode: vertical-rl を活用し、日本の伝統的な小説形式をサポート。

ルビ (振仮名) サポート: {漢字|かんじ} というシンプルな記法で HTML5 の <ruby> タグをレンダリング。

縦中横 (Tate-chu-yoko): 縦書き中の半角数字や記号（!!, ??）を自動的に水平表示。

原稿用紙カウント: 文字数だけでなく、400字詰め原稿用紙（20x20）に換算した枚数をリアルタイムで表示。

禁則処理: 行頭・行末禁則（句読点や開き括弧の制御）を適切に処理。

📦 インストール

```bash
npm install milkdown-plugin-novel-japanese
```

🚀 使用方法
Next.js プロジェクトでの使用例：

```tsx
import { Editor, rootCtx } from '@milkdown/core'; import { nord } from '@milkdown/theme-nord';
import { commonmark } from '@milkdown/preset-commonmark';
import { japaneseNovel } from 'milkdown-plugin-novel-japanese';

// 縦書き・ルビスタイルをインポート import 'milkdown-plugin-novel-japanese/style.css';

const createEditor = (root) => { return Editor.make() .config((ctx) => { ctx.set(rootCtx, root); }) .config(nord) .use(commonmark) .use(japaneseNovel({ isVertical: true, // 縦書きモードを有効化 showManuscriptLine: true // 原稿用紙風のグリッド線を表示 })); };
```

📝 構文例

1. ルビ (振仮名)
   入力：それは{運命|さだめ}だった。 出力：漢字「運命」の上に「さだめ」が表示されます。

2. 縦中横 (Tate-chu-yoko)
   縦書きモード時に自動処理されます。 例：10 や !! が読みやすく水平に配置されます。

🛠 構成要素
novel-syntax: Remark 拡張による日本語特有記法の解析。

novel-component: Ruby などのリアルタイムプレビューと編集。

novel-theme: vertical-rl に最適化されたスクロールとレイアウト管理。

🗺 ロードマップ (Roadmap)
[x] 基本的なルビのレンダリング

[x] 縦書き・横書き切り替え CSS エンジン

[ ] 傍点（圏点）のサポート

[ ] 外部校正 API (Enno.jp 等) との連携

[ ] 文庫本形式の PDF エクスポート

🤝 コントリビュート
日本語のタイポグラフィやレイアウトに関するフィードバックは大歓迎です！
