# Figma 作業手順（時間優先版）

提出期限が近いため、評価される要素を最短で組み立てる順番にしています。
**全部で 1.5〜2 時間** を想定。

---

## STEP 0 — 準備（5分）

1. 提供 Figma を Duplicate
2. ページを以下に整理
   ```
   00_Cover
   01_Research
   02_Design System
   03_Components
   04_Screens
   05_UX Proposal
   06_Notes
   ```

---

## STEP 1 — Variables / Styles を先に作る（20分）★最重要

評価で一番効くのは「**トークンが整理されているか**」です。画面より先に作ります。

### Color Variables（Collection: `core`）
`DESIGN_SYSTEM.md` の Color Tokens を全部登録。
- base/black, base/dark-gray, surface/card, surface/glass, surface/scrim
- text/primary, text/secondary, text/tertiary, text/disabled
- accent/water-blue, accent/deep-blue, accent/soft-cyan
- status/attention, status/success, status/error

### Text Styles
display/large, title/large, title/medium, body/large, body/medium, caption, label
（font は Inter + Noto Sans JP）

### Number Variables
space/xs(4), space/s(8), space/m(16), space/l(24), space/xl(32), space/xxl(48)
radius/sm(8), radius/md(16), radius/lg(24), radius/full(999)

---

## STEP 2 — Components を作る（30分）

最低この5つだけは必ず作る。残りは時間があれば。

### 必須5
1. **Button / Primary**（44h, radius/full, fill accent/water-blue）
   - Variant: default / pressed / disabled
2. **Card / Artwork / Featured**
   - 構造: image + title + subtitle + meta row
   - Auto Layout 縦, gap 12, padding 16, radius/lg
3. **Navigation / Bottom**
   - 5アイコン + ラベル, height 72, blur background
   - Variant: each active state
4. **Topbar / Glass**
   - backdrop-blur, transparent background
5. **MapPin**
   - Variant: default / visited / recommended / current(glow)

### 余裕があれば
- Tag, BottomSheet, Modal, Alert, QR/Ticket

---

## STEP 3 — Screens（40分）

下記の順で。1画面 5分目安。

### 優先順位
1. **Home** ← まず1枚作る。デザインシステムの説得力が最大化する画面。
2. **Artwork Detail** ← 提供デザインの再現性をアピールする画面。
3. **Map**
4. **Quiet Mode** ← UX提案の証拠画面。
5. **Exhibition List**
6. **Nearby Artwork Guide**
7. **Splash**
8. **Ticket / Entry**
9. **Settings**

### 共通設定
- Frame: iPhone 15 / 393×852
- Status Bar: 44pt
- Bottom Safe Area: 34pt
- Bottom Nav: 72pt
- 左右マージン: 24pt
- すべて Auto Layout

---

## STEP 4 — Cover / Research / UX Proposal（15分）

### Cover
- Title: "teamLab Guide App"
- Subtitle: "Quiet Guide for Immersive Space"
- 制作者名
- 課題名
- 中央寄せ、余白多め、装飾なし

### Research（1スライド分でOK）
- 利用環境：暗所 / 回遊 / 没入
- 想定ユーザー：来場者（初訪問者・リピーター）
- ユーザー課題：眩しい・歩きながら使う・没入を切らしたくない

### UX Proposal
- Quiet Guide Mode の課題・提案・フロー・期待効果
- `補足資料.md` の内容をそのまま図解化

---

## STEP 5 — 仕上げ（10分）

- すべての Layer 名を英語snake_caseに統一
- Frame 名のプレフィックスを整える（`Screens / Home / Default`）
- 未使用の Component / Style を削除
- Cover ページに戻して、共有リンクを「閲覧可能」で発行

---

## 提出時チェックリスト

- [ ] Color が全て Variable 経由
- [ ] Text が全て Text Style 経由
- [ ] すべての Frame に Auto Layout
- [ ] Tap領域 ≥ 44pt
- [ ] 本文 ≥ 14pt
- [ ] Component に Variant 設定済み
- [ ] Layer 名が英語snake_case
- [ ] 共有リンクが「Anyone with link / Can view」
- [ ] PDF 補足資料を添付
- [ ] 提出メールに Figma URL を貼った

---

時間が足りなくなったら、優先順位は
**Design System > Components > Home画面 > Artwork Detail > 残り**
で削ってください。
