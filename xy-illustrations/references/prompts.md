# Prompt 模板

先读 `../SKILL.md`。这里只放可粘贴的 prompt。出图必须带 `../refs/` 里的参考图。

## 身份句（每次都带）

```
Same character as the references: XY, young girl, black high ponytail, center of forehead open with visible hairline, short side-swept bangs only at the temples beside the eyes. Entire face filled with the same peach skin as neck and arms, light pink blush, simple ink-line eyes and small smile. Apricot-cream short-sleeve shirt, cocoa-brown wide pants, cream sneakers. Clean ink-line sticker illustration, flat warm fill. Not 齐刘海, not slicked-back bald forehead, not white/paper face, not polished anime, not watercolor, not chibi, not photoreal, no letters on clothes.
```

## 个人形象图 / 拍立得（1:1）

Ref：`mascot.jpg`、`wave-head.jpg`、`wave.png`。

```
Multi-image fusion.

Image 1 = keep ONLY the scene: webcam sitting on a wooden desk, desk filling the lower foreground, girl behind the desk facing the camera, silver laptop, left plant, bear mug, lamp, books, hanging-plant shelf, cream wall. Bright and clean.

Image 2 = the face, skin, and hair. Image 3 = the full body and clothes.

Copy XY from Image 2/3. She faces the camera, looks at us, small smile, hands on the laptop. Do not look down at the screen.

Face: fill the entire face with the same peach as neck and arms. Pink blush. Never white, paper, or unfilled.

Hair: high black ponytail, center forehead open, short temple bangs beside the eyes. Not 齐刘海. Not slicked fully back.

She is drawn into the room, not a cut-out sticker. No white die-cut outline.

Square 1:1, ink-line, flat warm color.
```

## 文章配图（16:9）

Ref：`wave.png`、`wave-head.jpg`、`character-sheet.png`。

把 `{动作}` 换成这一张要发生的事。标注可选。

```
Single illustration, 16:9. Cream-white background, generous whitespace.

XY from the references does: {动作}

One action, one object. Optional short red handwritten Chinese labels with arrows, few words.

No extra people, no green screen, no watermark, no frame, no letters on clothes.
```

## 表情贴纸

不要用本文件出表情包。改走 `xy-stickers`：`../xy-stickers/SKILL.md` 和 `../xy-stickers/references/prompts.md`。

## 命令

```bash
BUN="${BUN:-$HOME/.bun/bin/bun}"
MAIN="$HOME/.agents/skills/baoyu-image-gen/scripts/main.ts"
REF="$HOME/.agents/skills/xy-illustrations/refs"

"$BUN" "$MAIN" \
  --provider dashscope --model wan2.7-image-pro \
  --ar 1:1 --quality 2k \
  --promptfiles /tmp/xy-prompt.txt \
  --ref "$REF/mascot.jpg" "$REF/wave-head.jpg" "$REF/wave.png" \
  --image /tmp/xy-out.png
```

配图把 `--ar` 改成 `16:9`，ref 改成 `wave.png` `wave-head.jpg` `character-sheet.png`。
