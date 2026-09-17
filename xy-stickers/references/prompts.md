# Prompt 模板

先读 `../SKILL.md`。出图必须带 `xy-illustrations/refs/`。

`REF` 默认：

```
$HOME/.agents/skills/xy-illustrations/refs
```

## 身份句（每次都带）

```
Same character as the references: XY, young girl, black high ponytail, center of forehead open with visible hairline, short side-swept bangs only at the temples beside the eyes. Entire face filled with the same peach skin as neck and arms, light pink blush, simple ink-line eyes and small smile. Apricot-cream short-sleeve shirt, cocoa-brown wide pants, cream sneakers. Clean ink-line sticker illustration, flat warm fill. Not 齐刘海, not slicked-back bald forehead, not white/paper face, not polished anime, not watercolor, not chibi, not photoreal, no letters on clothes.
```

## 单张站点贴纸（1:1，米色底，允许模切白边）

Ref：`wave.png`、`wave-head.jpg`、`ok.png`。

```
Same XY as the references. Full body, centered on a 1:1 square. Light warm beige paper background with a faint plus-sign pattern. White die-cut sticker outline around the character is OK.

She FACES THE CAMERA and looks at us. Not a side view, not walking to the side, not 3/4 away from camera.

Pose: {动作}

No green screen, no extra people, no desk scene, no letters on clothes.
```

低头看电脑时 Pose 写明额发往前掉，ref 把 `ok.png` 换成 `laptop.png`。

## 九宫格源图（3×3，纯绿底）

Ref 同上。九个动作按行优先 01–09 写进 prompt。

```
Opaque 3x3 sticker sheet, square. Exact uniform pure-green background #00FF00, edge-connected, no gradient, no scene, no shadow, no checkerboard.

Nine isolated full-body XY stickers, one per cell, wide gutters, no subject crossing cell borders.

Each cell is the same XY as the references, facing the camera, ink-line, flat warm fill. White die-cut outline per cell is OK. No extra people.

Row-major:
01 {动作}
02 {动作}
...
09 {动作}
```

绿底只用于这一张源图。不要把绿底用到站点单张 png。

## 命令

```bash
BUN="${BUN:-$HOME/.bun/bin/bun}"
MAIN="$HOME/.agents/skills/baoyu-image-gen/scripts/main.ts"
REF="$HOME/.agents/skills/xy-illustrations/refs"

"$BUN" "$MAIN" \
  --provider dashscope --model wan2.7-image-pro \
  --ar 1:1 --quality 2k \
  --promptfiles /tmp/xy-sticker-prompt.txt \
  --ref "$REF/wave.png" "$REF/wave-head.jpg" "$REF/ok.png" \
  --image /tmp/xy-sticker.png
```

九宫格源图同样 `--ar 1:1`，prompt 换成绿底 3×3 模板。
