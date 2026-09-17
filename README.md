# xy-skills

自己用的 Agent Skills。个人形象、表情包和成稿口吻拆成三个目录，拷进技能加载目录就能用。

| Skill | 做什么 |
|---|---|
| [xy-illustrations](./xy-illustrations) | 个人形象、拍立得、文章配图。人锁在 `refs/` 里，出图必须带参考图。 |
| [xy-stickers](./xy-stickers) | 同一套角色的表情包和站点贴纸。单张米色模切，九宫格才走绿底切格。 |
| [xy-blog-writing](./xy-blog-writing) | 成稿口吻和事实边界。 |

`xy-stickers` 不另存一份人设图，直接用 `xy-illustrations/refs/`。

## 安装

```bash
git clone https://github.com/Xinyuan-Gao/xy-skills.git
cd xy-skills
mkdir -p ~/.agents/skills
ln -sf "$PWD/xy-illustrations" ~/.agents/skills/xy-illustrations
ln -sf "$PWD/xy-stickers" ~/.agents/skills/xy-stickers
ln -sf "$PWD/xy-blog-writing" ~/.agents/skills/xy-blog-writing
```

Claude / Codex 若从 `~/.claude/skills/` 或项目 `.agents/skills/` 读 Skill，把链接建到对应目录即可。

已经在本机用着这三份的话，这个仓库用来备份和同步。
