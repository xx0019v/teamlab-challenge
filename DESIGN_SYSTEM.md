# teamLab Guide App — Design System Spec
**Concept:** Quiet Guide for Immersive Space
**Target Device:** iPhone 15 / 393 × 852pt
**Designer:** アヴェンダニョ シンタロウ

---

## 0. 設計原則（Design Principles）

1. **Don't compete with the artwork** — UIは作品体験の背景に徹する。
2. **Read in the dark** — 暗所での視認性を、装飾より優先する。
3. **One-hand, walking** — 歩きながら片手で使える操作領域とリズム。
4. **Quiet hierarchy** — 階層・余白・コントラストで構造を表現し、装飾は減らす。
5. **Reusable from day one** — Auto Layout / Component / Variable を前提に作る。

---

## 1. Color Tokens

### Base / Surface
| Token | Value | Usage |
|---|---|---|
| `color/base/black` | `#050609` | App background |
| `color/base/dark-gray` | `#111318` | Section background |
| `color/surface/card` | `#181B22` | Card / Sheet |
| `color/surface/glass` | `rgba(255,255,255,0.08)` | Overlay / Topbar blur |
| `color/surface/scrim` | `rgba(0,0,0,0.6)` | Modal scrim |

### Text
| Token | Value | Contrast on `#050609` |
|---|---|---|
| `color/text/primary` | `#FFFFFF` | 19.6 : 1 ✓ AAA |
| `color/text/secondary` | `rgba(255,255,255,0.72)` | ~14 : 1 ✓ AAA |
| `color/text/tertiary` | `rgba(255,255,255,0.48)` | 7.0 : 1 ✓ AA Large |
| `color/text/disabled` | `rgba(255,255,255,0.32)` | informational only |

### Accent
| Token | Value | Usage |
|---|---|---|
| `color/accent/water-blue` | `#69D9FF` | Primary CTA / 現在地 / Selected |
| `color/accent/deep-blue` | `#2B6CFF` | Press state of water-blue |
| `color/accent/soft-cyan` | `#A8F1FF` | 装飾 / グロー |

### Status
| Token | Value | Usage |
|---|---|---|
| `color/status/attention` | `#FFCC66` | 混雑表示 |
| `color/status/success` | `#7CE2A4` | Visited / 完了 |
| `color/status/error` | `#FF5A5F` | エラー |

---

## 2. Typography

**Font:** Inter (Latin) + Noto Sans JP (CJK) — どちらも400/500/600/700。
**Reason:** 暗所での字形可読性と、英日混在の高さ揃え。

| Style | Size / Weight | Line-height | Letter-spacing | Use |
|---|---|---|---|---|
| `display/large` | 32 / 700 | 1.2 | -0.01em | Hero numbers ("28m") |
| `title/large` | 24 / 700 | 1.3 | -0.005em | 作品タイトル |
| `title/medium` | 20 / 600 | 1.3 | 0 | Section heading |
| `body/large` | 16 / 400 | 1.6 | 0 | 説明文 |
| `body/medium` | 14 / 400 | 1.55 | 0 | 補足説明 |
| `caption` | 12 / 400 | 1.4 | 0 | メタ情報 |
| `label` | 11 / 500 | 1.3 | 0.04em | Tag / Nav label |

> 本文は14pt未満を使わない。暗所での疲労を増やすため。

---

## 3. Spacing — 8pt Grid

| Token | Value |
|---|---|
| `space/xs` | 4 |
| `space/s` | 8 |
| `space/m` | 16 |
| `space/l` | 24 |
| `space/xl` | 32 |
| `space/xxl` | 48 |

- 画面左右マージン: **24pt**
- カード内パディング: **16–20pt**
- セクション間: **32pt以上**
- Tap領域: **最低 44×44pt**（暗所での誤タップ防止に通常より広く）

---

## 4. Radius

| Token | Value | Use |
|---|---|---|
| `radius/sm` | 8 | Tag, Input |
| `radius/md` | 16 | Button, Small Card |
| `radius/lg` | 24 | Artwork Card, Modal |
| `radius/full` | 999 | Pill, Avatar, FAB |
| `radius/sheet-top` | 24 (top only) | Bottom Sheet |

---

## 5. Shadow / Blur

| Token | Value |
|---|---|
| `shadow/card` | `0 8 24 rgba(0,0,0,0.5)` |
| `shadow/floating` | `0 12 40 rgba(0,0,0,0.6)` |
| `blur/glass-topbar` | `backdrop-blur: 24px` |
| `blur/bottom-sheet` | `backdrop-blur: 32px` |
| `glow/accent` | `0 0 24 rgba(105,217,255,0.45)` |

---

## 6. Icon Rules

- **Library:** Lucide (24px / stroke 1.5)
- 必ず**vector**。emoji絶対NG。
- アクティブ状態のみ filled、通常は outline。
- Iconサイズ: `16 / 20 / 24 / 32`（混在禁止）
- Iconには必ず `accessibilityLabel`。

---

## 7. Component Inventory（11個＋Variant）

| Component | Variants |
|---|---|
| `Button/Primary` | default / pressed / disabled / loading |
| `Button/Secondary` | default / pressed / disabled |
| `Button/Ghost` | default / pressed |
| `Card/Artwork` | featured / compact / list / visited / nearby |
| `Tag` | default / selected / status-attention |
| `Navigation/Bottom` | home / map / guide / ticket / settings (5 active states) |
| `Topbar/Glass` | default / with-back |
| `BottomSheet/Artwork` | peek (120) / expanded (480) |
| `Modal/Info` | default |
| `MapPin` | default / visited / recommended / current |
| `Alert/Inline` | info / attention / error |
| `LanguageSwitch` | JA / EN |
| `QR/TicketEntry` | scan / display |
| `Toast` | info / success / error |

---

## 8. Figma 命名ルール

```
Pages:
  00_Cover
  01_Research
  02_Design System
  03_Components
  04_Screens
  05_UX Proposal
  06_Notes

Frames:
  Screens / Home / Default
  Screens / Artwork Detail / Default
  Screens / Quiet Mode / Active
  ...

Components:
  Button / Primary
  Card / Artwork / Featured
  Navigation / Bottom
  ...

Layers:
  // 英語snake_case
  artwork_image
  artwork_title
  meta_row
```

- すべてのFrameに **Auto Layout** を適用。
- すべての色は **Variable** 化（Light/Darkは将来拡張可能な形に）。
- すべての文字は **Text Style** 経由。
- Hard-coded hex / px は禁止。
