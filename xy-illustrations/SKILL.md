---
name: xy-illustrations
description: XY 的个人形象与站点配图。角色锁定为暖色线稿女孩：杏色短袖、可可棕阔腿裤、米色运动鞋；黑发高马尾，额头中间露出，太阳穴短碎刘海，脸和胳膊同色杏色。用户要求个人形象图、拍立得、头像、mascot、配图、插画、术语图或 xy-illustrations 时使用。
---

# xy-illustrations

XY 的固定角色。个人形象图、拍立得、头像、文章配图、术语图都画同一个人，不要重设计。

2026-09-16 用户确认的定稿是 `refs/mascot.jpg`（桌面镜头拍立得）。新图必须对得上这张，以及挥手贴纸 `refs/wave.png`。

## 何时用

- 个人形象图、拍立得、头像、mascot、站点角色
- 文章配图、术语图、Skill 演示图、xy-illustrations

表情包、九宫格贴纸、站点 `xy-sticker` 的 png/gif 走 `xy-stickers`，不要用本 Skill 出模切贴纸。

不要用旧的深蓝 T 恤、黑色短裤、水彩梅花小人。

## 出图前必做

1. 打开本目录 `refs/`，至少看 `mascot.jpg`、`wave-head.jpg`、`wave.png`、`character-sheet.png`。
2. 生图必须带参考图，禁止只靠文字重画一张新脸。
3. 优先 `baoyu-image-gen`：`--provider dashscope --model wan2.7-image-pro --ar` 按用途 `--quality 2k`，`--ref` 附上参考图。
4. 出图后对照下面「验收」逐项看。不合格就改 prompt 重出，不要将就。

参考图路径（相对本 Skill 目录）：

| 文件 | 用来锁什么 |
|---|---|
| `refs/mascot.jpg` | 已定稿的个人形象：构图、脸、头发、衣服、场景 |
| `refs/wave-head.jpg` | 脸、肤色、发型近景 |
| `refs/wave.png` / `refs/wave-full.jpg` | 全身比例、衣服、走路姿态 |
| `refs/ok.png` | 正脸、碎刘海、肤色 |
| `refs/laptop.png` | 低头看电脑时的刘海（额发会往前掉，仅这个姿势） |
| `refs/character-sheet.png` | 原版六姿态线和发型 |

个人形象图默认 ref：`mascot.jpg` + `wave-head.jpg` + `wave.png`。
配图默认 ref：`wave.png` + `wave-head.jpg` + `character-sheet.png`。

## 角色锁定

名字：XY。年轻女孩，身体比例正常，不是大头 Q 版。

### 脸（最容易画错）

- 整张脸涂满：额头、脸颊、鼻子、下巴、耳朵，和脖子、胳膊同一杏色 / 桃色。
- 两颊浅粉腮红。
- 五官是简单墨线：小点或短弧眼睛、小小微笑，鼻子几乎不画。
- **禁止**：白脸、纸色脸、没涂的脸、脸比胳膊浅、精致动漫五官、大眼、高光鼻唇。

### 头发（最容易画错）

对 `refs/wave-head.jpg` 和 `refs/ok.png`：

- 黑发，高马尾，从头顶束起。
- **额头正中露出**，发际线清楚。
- **太阳穴两侧短碎刘海**，贴在眼睛旁边，可以有几缕细发丝。
- **禁止齐刘海**：不要一条直线挡住整额。
- **禁止梳太开**：不要把头发全部往后拢，露出光额头或秃太阳穴。
- 只有「低头看电脑 / 看书」时，刘海可以往额前掉一点，见 `refs/laptop.png`。正对镜头时用挥手那款碎刘海。

### 衣服

- 上衣：杏色 / 奶油杏短袖 T 恤。
- 裤子：暖可可棕阔腿裤。
- 鞋：米色 / 奶油色运动鞋。
- 衣服上不要写 X、Y 或任何字母。

### 画风

- 干净墨线贴纸插画，平涂暖色，线宽稳定。
- 浅米白或奶油色底，明亮，不要发灰发暗。
- **禁止**：写实照片、厚涂水彩、精美动漫、大头 Q 版、绿幕、水印、相框、衣服上的字母。
- 画进场景时（拍立得、办公桌），人是画面的一部分，**不要**贴纸白边 / 模切描边 / 像贴上去的表情包。表情包走 `xy-stickers`，那里才允许模切白边。

## 两种用途

### A. 个人形象图 / 拍立得 / 头像

默认构图（用户确认的 D）：

- 镜头放在桌面上，桌子占画面下半，像摄像头搁在桌沿。
- 人坐在桌子后面，**正对或略侧对镜头，看向镜头**，微笑。不要低头看屏幕。
- 桌上：银色笔记本、左侧绿植、小熊杯子、台灯、书；后面可以有垂藤小书架。
- 比例 1:1。站点拍立得和导航头像用这张。
- 导航圆形头像会裁画面上方约 22%，脸必须够近、够清楚。

用户如果只要半身、全身站姿或别的场景，仍锁脸 / 头发 / 衣服 / 画风，只改姿势和场景。

### B. 文章配图 / 术语图

- 横图默认 16:9；单动作贴纸可用 1:1。
- 浅米白底，留白多，不要复杂办公室底板（除非用户要场景）。
- 一张图一件事、一个动作、一个对象。
- 需要标注时用红色手写中文加箭头，字少。
- 不要额外人物。

## 出图

优先 2K。DashScope `wan2.7-image-pro` 支持多图 `--ref`，个人形象必须走参考图融合，不要纯文生图。

把 [references/prompts.md](references/prompts.md) 里对应模板填进 prompt，并写明各张 ref 的用途，例如：

```
Image 1 = mascot.jpg：只保留构图和场景。
Image 2 = wave-head.jpg：脸、肤色、发型。
Image 3 = wave.png：衣服和全身。
```

英文身份句（可直接拼进 prompt）：

```
Same character as the references: XY, young girl, black high ponytail, center of forehead open with visible hairline, short side-swept bangs only at the temples beside the eyes. Entire face filled with the same peach skin as neck and arms, light pink blush, simple ink-line eyes and small smile. Apricot-cream short-sleeve shirt, cocoa-brown wide pants, cream sneakers. Clean ink-line sticker illustration, flat warm fill. Not 齐刘海, not slicked-back bald forehead, not white/paper face, not polished anime, not watercolor, not chibi, not photoreal, no letters on clothes.
```

## 验收

交图前必须同时成立：

- [ ] 脸是杏色，和胳膊同色，有浅腮红；不是白脸。
- [ ] 高马尾；额心露出；太阳穴有短碎刘海。
- [ ] 不是齐刘海，不是头发全梳上去。
- [ ] 杏色短袖、可可棕阔腿裤、米色运动鞋。
- [ ] 墨线平涂，不是精美动漫 / 水彩 / 写实。
- [ ] 场景图没有贴纸白边。
- [ ] 个人形象图在看镜头，不是低头看电脑（除非用户要求低头）。
- [ ] 和 `refs/mascot.jpg`、`refs/wave.png` 是同一个人。

任一失败就重出。
