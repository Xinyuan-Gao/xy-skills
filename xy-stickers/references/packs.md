# 默认九格和站点文件名

## 默认九格

用户没点名动作时用这一套，先报出来确认再画。全部正对镜头、全身、站着或坐着仍能看清鞋子。

| 格 | slug | 动作 |
|---|---|---|
| 01 | wave | 右手举起挥手打招呼 |
| 02 | hi | 双手或单手在胸前打招呼，比挥手更收 |
| 03 | ok | 胸前 OK 手势 |
| 04 | aha | 刚想明白，小张嘴，手微抬，右上角可以有小星星或感叹号 |
| 05 | think | 托腮或手抵下巴思考 |
| 06 | cheer | 小握拳加油 |
| 07 | explain | 一只手摊开讲解 |
| 08 | notes | 拿本子或笔在记 |
| 09 | read | 捧书看，这时额发可以略往前掉 |

不要把走路侧身挥手当成默认 01。站点页脚那张 `wave` 可以是侧身走路，但新包默认正脸。

## 站点已有贴纸

博客成品在 `src/assets/img/stickers/xy/`。每个 slug 一对 png/gif。

正脸包：`front-wave` `front-hi` `front-ok` `front-aha` `front-cheer` `front-explain` `front-notes` `front-read` `front-show` `front-study` `front-think`

侧身 / 场景：`wave` `ok` `laptop` `thinking` `sleepy` `coffee`

新贴纸不要覆盖旧文件，除非用户明确说替换。新主题用新 slug，或 `front-{动作}`。

## 工程目录

九宫格过程文件放：

```
src/assets/img/stickers/da-job-xy-{主题}/
```

已有 `da-job-xy-front`、`da-job-xy-office`、`da-job-xy-warm`、`da-job-xy-bw`。新主题另开目录，不要往旧 job 里叠。
