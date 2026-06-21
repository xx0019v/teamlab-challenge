# Figma 01_Components — 構築指示書（未実施・枠回復後に実行）

> 正直な状態：Figma無料プランの編集回数制限により、現時点で `01_Components`
> ページへのコンポーネント配置は**実行できていません**。以下は、枠が回復したとき
> そのまま実行できる指示です。AIが「やった」と偽らないために、ここに残します。

対象ファイル：https://www.figma.com/design/HAfwLTPJoD6Uh1ZUomAylE
対象ページ：`01_Components`（現在は空。スタイルは右パネルに定義済み）

---

## 配置するコンポーネント（既存6画面から抽出）

| # | Component | Variants / States | 仕様 |
|---|---|---|---|
| 1 | `Button / Primary` | Default / Pressed | radius 999・padding 11×24・fill Text/Primary・文字 #0c1a20 |
| 2 | `Button / Secondary` | Default | radius 999・0.5px hairline・透明背景 |
| 3 | `Navigation / App Bar` | back / title / menu | height 44・space-between・padding 14 |
| 4 | `Card / Artwork` | Default / Visited | aspect 1:1・radius 7・image fill（Visitedは scrim+✓） |
| 5 | `Card / Area (Guide)` | Default / Current | full-bleed・下グラデ・title overlay |
| 6 | `Map / Pin` | Current / Artwork | Current=白+glow・Artwork=色ドット |
| 7 | `Status / Queue` | Available | YOUR NUMBER + V-128 + waiting note |
| 8 | `Status / Badge` | Live / Visited / Busy | radius 999・色16%背景・色文字・tracking 0.08em |
| 9 | `Information Row` | — | label↔value・下に0.5px hairline |
| 10 | `Divider` | — | 0.5px・Line/Divider |

各コンポーネントに併記：Component name / Variants / States / Padding / Gap /
Radius / Color token / Text style / Usage note。

## 命名規則
```
Navigation / Bottom / Item
Button / Primary / Default
Button / Primary / Pressed
Card / Artwork / Default
Card / Artwork / Visited
Status / Queue / Available
Map / Pin / Current
```

## 重要
- **6画面（02_Screens）の見た目は変更しない。** ここは「再現済みの部品を可視化する」だけ。
- すべて Auto Layout・既存 Color/Text Style を適用。
- 配置後、各コンポーネントを右クリック →「コンポーネントの作成」で ⬡ 化し、
  Variant をまとめる。

## 実行用コード（Figma MCP / プラグインAPI）
枠回復後、`use_figma` に渡せば自動配置される完全なJSは
リポジトリのコミット履歴（このファイル追加時点）の作業ログにある通り。
手動で組む場合は上表の仕様に従えば同一結果になる。

---

## 手動で組む場合の最短手順（10分）
1. `01_Components` を開く
2. 左上に Text で「Component Library」(36px Bold) と説明1行
3. 上表の各部品を、暗い角丸ステージ（Base/Black・radius14・padding20）の上に置く
4. 各ステージの上に Caption で部品名（Accent色）、下に仕様テキスト（Text/Tertiary 10px）
5. 部品を選択 → Cmd+Option+K で Component 化
6. 状態違い（Default/Pressed/Visited 等）は Variant にまとめる
