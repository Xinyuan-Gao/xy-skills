---
name: xy-stickers
description: 用 XY 固定角色生成个人表情包。适用于挥手/OK/思考等单张贴纸、九宫格动态表情包、站点 xy-sticker、png+gif 成对交付。不要用于拍立得、头像、文章配图或术语图。
---

# xy-stickers

XY 的表情包。人必须是 `xy-illustrations` 里那一套，不要重设计。本 Skill 只管贴纸：模切白边、透明底、九宫格动态包。拍立得和文章配图走 `xy-illustrations`。

## 何时用

- 个人表情包、贴纸、九宫格、动态 GIF、微信表情
- 站点 `xy-sticker`（页脚挥手、栏目 aha 等）
- 「做一套 XY 的表情」「再出一张 OK 贴纸」

不要用：个人形象图、拍立得、头像、文章配图、术语图。那些走 `xy-illustrations`。

不要单独跑 `da-motion-sticker-skill` 而不带本 Skill 的角色锁。九宫格的切格、去绿幕、打包脚本可以复用那个 Skill，角色和画风以这里为准。

## 出图前必做

1. 打开 `xy-illustrations/refs/`，至少看 `wave.png`、`wave-head.jpg`、`ok.png`、`character-sheet.png`。低头看电脑才加 `laptop.png`。
2. 生图必须带参考图，禁止只靠文字重画一张新脸。
3. 先读 [references/packs.md](references/packs.md) 里的默认九格和站点文件名，再读 [references/prompts.md](references/prompts.md)。
4. 优先 `baoyu-image-gen`：`--provider dashscope --model wan2.7-image-pro --ar 1:1 --quality 2k`，`--ref` 附上参考图。
5. 对照下面「验收」。不合格就改 prompt 重出。

参考图路径（相对 `xy-illustrations` 目录，本 Skill 不复制一份）：

| 文件 | 贴纸里锁什么 |
|---|---|
| `refs/wave.png` | 全身、衣服、站姿、模切白边 |
| `refs/wave-head.jpg` | 脸、肤色、发型 |
| `refs/ok.png` | 正脸、碎刘海 |
| `refs/character-sheet.png` | 六姿态线 |
| `refs/laptop.png` | 仅低头看电脑时的额发 |

贴纸默认 ref：`wave.png` + `wave-head.jpg` + `ok.png`。

## 角色锁定

和 `xy-illustrations` 同一人。名字 XY。年轻女孩，身体比例正常，不是大头 Q 版。

- 脸：整张涂满杏色 / 桃色，和脖子、胳膊同色；浅粉腮红；墨线小点眼睛、小小微笑。禁止白脸、纸色脸、精致动漫五官。
- 头发：黑发高马尾，额心露出，太阳穴短碎刘海。禁止齐刘海，禁止头发全梳上去。只有低头看电脑 / 看书时额发可以往前掉，见 `laptop.png`。
- 衣服：杏色短袖、可可棕阔腿裤、米色运动鞋。衣服上不要字母。
- 画风：干净墨线贴纸，平涂暖色。禁止写实、水彩、精美动漫、Q 版、绿幕（单张米色底时）、水印。

和形象图的差别：表情包**允许**模切白边。人要居中、全身或大半身，正对镜头。不要办公桌场景。

## 两种用途

### A. 单张站点贴纸

站点现用格式：同名 `png` + `gif`，gif 可自动播。

1. 用户给动作，或从 [references/packs.md](references/packs.md) 里选一个 slug。
2. 用 prompts.md 的单张模板出 1:1 静帧。底是浅暖米色，可以有淡十字纹；人带白模切边。
3. 需要动态时，用同一张静帧做参考，再出短循环动作（挥手、点头、眨眼），或走下面 B 的单格。
4. 接到博客时拷到：

```
src/assets/img/stickers/xy/{slug}.png
src/assets/img/stickers/xy/{slug}.gif
```

页面用法：`src` 用 png，`data-gif` 用 gif，需要一进来就动就加 `data-gif-auto`。不要改 `sticker.js` 的约定。

### B. 九宫格动态包

用户说「一套表情包 / 九宫格 / 动态贴纸」时走这条。

1. 九个反应：用户指定就用用户的。没指定就用 packs.md 的默认九格，先报给用户确认。
2. 工程目录放在博客仓库外或 `src/assets/img/stickers/da-job-xy-{主题}/`，不要写进 Skill 目录。
3. 九宫格**源图**必须用不透明纯绿底 `#00FF00`，这是 `da-motion-sticker-skill` 切格去背的要求。这和单张米色底不同，不要混。
4. 按 `da-motion-sticker-skill` 的流程：`compile_prompts.py` → 带 XY ref 生 3×3 绿底大图 → `prepare_sheet.py` → 用户选关键帧路线或视频路线 → 打包九张透明 GIF。
5. 风格不要问 36 套预设。锁定本 Skill 的墨线暖色贴纸。角色图也不要再问，用上面的 refs。
6. 切完后逐格对照验收。脸或衣服漂了就重出那一格，不要整包将就。

## 出图

身份句和模板在 [references/prompts.md](references/prompts.md)。ref 用途写进 prompt，例如：

```
Image 1 = wave.png：全身、衣服、模切边。
Image 2 = wave-head.jpg：脸、肤色、发型。
Image 3 = ok.png：正脸碎刘海。
```

低头看电脑时把 Image 3 换成 `laptop.png`。

## 验收

交图前必须同时成立：

- [ ] 和 `wave.png`、`wave-head.jpg` 是同一个人。
- [ ] 脸是杏色，和胳膊同色，有浅腮红；不是白脸。
- [ ] 高马尾；额心露出；太阳穴有短碎刘海。不是齐刘海，不是头发全梳上去。
- [ ] 杏色短袖、可可棕阔腿裤、米色运动鞋。
- [ ] 正对镜头（用户明确要求侧身或走路除外）。
- [ ] 墨线平涂贴纸。单张允许白模切边；九宫格源图才用纯绿底。
- [ ] 没有办公桌场景、没有第二个人、衣服上没有字母。
- [ ] 接到站点时 png 和 gif 文件名一致，gif 能循环。

任一失败就重出。
