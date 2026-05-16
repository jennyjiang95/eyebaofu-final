# E 夜暴富 · 求符记 — 期末展示 Slides

## 任务

为 CVS 领航十一期 Team E 期末展示 (2026.05.17, JJ Lake) 制作一套 **HTML 单文件** 演示 slides。
风格: 中国道家求符堂会 + 红金喜庆 + 猫元素。5 分钟 HARD LIMIT 演出节奏。

**最终交付物**: `index.html` (单文件,内嵌 CSS / JS / SVG, 用相对路径引用 `assets/` 下的图片), 在浏览器中按方向键 / 空格切换 slides, 适配 16:9 投影 (1920×1080)。

## 现有素材

```
eyebaofu-final/
├─ CLAUDE.md                      ← 本文档
├─ assets/
│   ├─ team/01.png ... 11.png    ← 11 位组员头像 (从期中PDF p2 抽取, 顺序未必对应名单, 你需要肉眼判断哪张配哪个名字, 或全部统一展示)
│   ├─ mentors/m1.png ... m4.png ← 4 位导师头像 (PDF p3 抽取, 同上)
│   ├─ activities/a1.png ... a7.png ← 12场活动里能用的照片
│   └─ qr/vote.png               ← 投票二维码 (zhswatson.github.io)
└─ reference/
    ├─ old_slides.html            ← 之前一版求符记 slides, 视觉风格基线 (红金宣纸/符牌/猫SVG), 可以直接复用 CSS 风格和 SVG 猫绘制代码
    └─ backup_slides.html         ← 备用版,可参考
```

**强烈建议**: 直接 fork `reference/old_slides.html` 的视觉系统 (宣纸底纹、四角云纹、talisman 符牌组件、猫 SVG)，在它基础上改造,而不是从零开始。

## 团队信息 (从期中 PDF 提取)

### 11 位组员 (顺序按 PDF p2)
| 角色 | 英文名 | 中文名 |
|---|---|---|
| 助教 | Luna Chen | 陈清源 |
| 助教 | Abby Sun | 孙炜禛 |
| 小组长 | Jenny Jiang | 姜尚君 |
| 组员 | Annie Zhou | 周叶 |
| 组员 | Hugang Ren | 任虎刚 |
| 组员 | Fanshu Jiang | 蒋凡述 |
| 组员 | Victor Yang | 杨康怡 |
| 组员 | Haibin Qi | 齐海彬 |
| 组员 | Luning Yang | 杨璐宁 |
| 组员 | Hansen Zhang | 张涵森 |
| 组员 | Boxin Jiang | 姜博馨 |

### 4 位导师 (E代名师 / 仙师 / 道长)
| 英文名 | 中文道号 | 头衔 |
|---|---|---|
| Chun Xia | 夏淳道长 | Founder & Managing Partner, Voyager Capital |
| Peiji Chen | 培基道长 | Director of Applied Science, Amazon |
| Yvonne Luo | Yvonne 道长 | Cofounder of 3 Tech Corps & TSVC |
| Shenghua Bao | 胜华道长 | VP of Engineering, Faire |

## 二维码

座位上 / 屏幕上的扫码用 `assets/qr/vote.png`, 链接 zhswatson.github.io (用于"扫码抽本命开富符 / 投票")。

---

## Slide 结构 (按演讲词)

总共 **9 张 slide** (开场 + 4 张前置 + 4 道符 + 终极符), 完全对齐 5 分钟脚本。

### Slide 1 — 开场 "开 / 坛"
- 全屏黑底, 中央两个超大金字 "开" / "坛" 依次从左右滑入, 各自 0.4s
- 下方副标题: "求 · 符 · 大 · 典"
- 底部小字: "领航十一期 · Team E · 2026.05.17 · JJ Lake"
- **没有其它文字**, 让现场喊出 "求·符·大典"
- 复用 old_slides.html 的 `#s-open` 样式

### Slide 2 — 立组 (E夜暴富)
- 大字标题: **E 夜 暴 富** (红色狂草感, 复用 .p0-title 样式)
- 副标题: **· 求 符 记 ·**
- 中央一行话: "我们不是因为爱财, 而是想搞清楚 —— 什么才是 · 真正的 · 暴富"
- "真正的" 三个字用金色高亮
- 底部 banner: ⚜ 领航十一期 · E 夜暴富 · 2026.05.17 ⚜

### Slide 3 — 11 只猫 (组员介绍)
- 标题: **十 一 喵 · E 往 无 前**
- 副标题: "5 位管理喵 · 5 位 IC 喵 · 2 位领队喵"
- **核心视觉**: 11 张组员头像, 每张包在一个 **猫脸边框** 里 (圆形头像 + 上方两只三角猫耳 SVG + 底部胡须装饰)
- 头像下方写: 中文名 + 英文名 + 角色标签 (助教/小组长/组员)
- 11 张照片用 4 列 / 3 行的网格布局 (最后一行 3 张居中), 用 CSS Grid
- 头像之间穿插小金色符号点缀
- **猫边框 SVG 实现思路**: 在 `<div class="cat-frame">` 中放一个圆形 `<img>`, 用 ::before / ::after 或额外 SVG 画两只猫耳 (左上、右上各一个三角形, 内里粉色三角), 底部画 6 根胡须线条
- 颜色: 头像边框配色按角色——助教 (金色) / 小组长 (红色) / 组员 (深棕)

参考 Google slide 第二页的布局: https://docs.google.com/presentation/d/1PEeGh965ZAMLPgOG-ki6DmRMuhflJwp4023KKydmcbs/edit?slide=id.g3bd5e522b03_1_1409

### Slide 4 — 四位道长 (导师)
- 标题: **四 位 仙 师 · 道 法 加 持**
- 4 张大头像横排, 每张做成 **道长画像** 风格:
  - 圆形头像外圈一圈金色道符 / 八卦纹 SVG 装饰环 (旋转动画, 慢速 30s/转)
  - 头像顶部加一顶 **道士帽** SVG (黑色方帽, 顶有金色发髻)
  - 头像下方挂一条红色绸带, 写道号 (夏淳道长 / 培基道长 / Yvonne 道长 / 胜华道长)
  - 道号下方小字写头衔
- 排列顺序按演讲: 培基 → 夏淳 → 胜华 → Yvonne (按授符顺序), 但道长 SVG 装饰风格统一
- 整体背景加几片飘动的祥云 (复用 cloud-bg)

### Slide 5 — 12 场修行 (活动照片墙)
- 标题: **十 二 场 · 求 道 修 行**
- 副标题: "9 个月 · 12 次聚 · 思想碰撞"
- 中央: **照片砖墙布局** (mosaic / masonry), 把 7 张活动照片以错落大小排列, 每张照片有 4-5° 的随机旋转, 像贴在墙上的 polaroid
- 每张照片配一行毛笔体小标题 (从 PDF p4 看, 内容为 "深度分享"、"思想碰撞"、"线下交流" 等), 你可以编 12 个修行主题:
  1. 拓同路 · 利他合作
  2. 广结善缘 · 聚贵人
  3. 把握大势 · 预先机
  4. 禅修心境 · 事从容
  5. 大展宏图 · 心想事成
  6. 深度分享 · 真知灼见
  7. 线下夜话 · 兄弟情深
  8. AI 浪潮 · 求护城河
  9. 职场破局 · 求晋升路
  10. 投资认知 · 求复利
  11. 组织视角 · 求高维
  12. 信任协作 · 求 Support
- 视觉细节: 红色 washi tape (胶带) 贴在每张照片角上

### Slide 6 — 两猫入山
**保留 old_slides.html 的 P1 设计, 但加强动画**:
- 标题: **两 猫 入 山 · 我 们 来 求 什 么**
- 左侧: **白色 Token 猫 SVG**, 旁边动态海浪 SVG 不断拍打 (CSS keyframes 上下波动, 蓝色渐变), 猫身上有 "Token" 燃烧图标
  - 文字: "我是 Token 猫 · AI 浪潮猫 / AI 浪潮拍来, 我只看到 Token 在烧, 护城河在塌 / 我是在驾驭浪潮, 还是在被淹没?"
- 右侧: **黑色 Title 猫 SVG**, 旁边一把锄头 / 一座山, 猫做出"开天辟地"的奋斗动作 (CSS animation: 身体小幅前倾 + 锄头上下挥动), 配几滴汗珠
  - 文字: "我是 Title 猫 · 职场破局猫 / 拼尽全力, 项目原地打转 / 我是开荒破局的人, 还是被局势清场?"
- 底部大字: **来 时 求 机 会 · 后 来 求 判 断**

### Slide 7 — 第一道符 · 财富复利符 (培基道长授)
**对联形式呈现四句心法** (重点改造):
- 标题: **第 一 道 符 · 财 富 复 利**
- 副标题: 🔔 培基道长 授符
- 左侧: 焦虑的 Token 猫 (cat-shake 动画), 配独白
- 右侧: **真正的对联布局**:
  - 中央一张大符牌, 红底金字, 两侧各挂一条**竖向对联** (rotation: writing-mode: vertical-rl)
  - **上联** (右): "看不懂不下注 · 真看懂小仓试"
  - **下联** (左): "没时间买大盘 · 活得久等复利"
  - **横批** (顶): "财 富 复 利"
  - 底部一行小字: "不懂装懂, 才是破财的开始"
- 对联文字用毛笔楷体, 每个字稍微错位增加手写感
- 授符瞬间金光闪烁动画 (复用 .gold-glow)

### Slide 8 — 第二道符 · 智能黑领符 (夏淳道长授)
- 标题: **第 二 道 符 · 智 能 黑 领**
- 副标题: 🔔 夏淳道长 授符
- 同样对联布局:
  - 上联: "识 压 缩 · 设 红 线"
  - 下联: "定 权 限 · 人 拍 板"
  - 横批: "智 能 黑 领"
  - 底部小字: "AI 是工具, 不是余生 / 别做提效白领, 要做设限黑领"
- 左侧 Token 猫 + 一个抽象 AI 机器人剪影对峙

### Slide 9 — 第三道符 · 信任协作符 (胜华道长授)
- 标题: **第 三 道 符 · 信 任 协 作**
- 副标题: 🔔 胜华道长 授符
- 对联:
  - 上联: "私 下 存 信 任 · 风 险 提 前 报"
  - 下联: "目 标 要 翻 译 · 缺 位 我 补 齐"
  - 横批: "信 任 协 作"
  - 底部小字: "信任存够了, 路才推得开"
- 左侧 Title 猫 (孤军奋战的姿态)

### Slide 10 — 第四道符 · 高维判断符 (Yvonne 道长授)
- 标题: **第 四 道 符 · 高 维 判 断**
- 副标题: 🔔 Yvonne 道长 授符
- 对联:
  - 上联: "先 定 北 极 星 · 问 我 要 什 么"
  - 下联: "再 看 组 织 盘 · 用 结 果 换 地 盘"
  - 横批: "高 维 判 断"
  - 底部小字: "不靠喊累, 靠 Deliver / 不是更努力, 是看更远"
- 左侧 Title 猫顿悟造型 (头顶灯泡)

### Slide 11 — 终极开富符 + 二维码 + 投票
**全场高潮 slide**, 必须震撼:
- 中央: 一个**山头道场 SVG 背景** (远山剪影 + 金色霞光), 两只猫 (白 Token + 黑 Title) 站在山头上对拜
- 标题: **终 极 · 开 · 富 · 符** (金光闪烁 + level up 动画)
- 中间: 4 道符的图标围成一圈, 中央汇聚成一道**金色总符** (CSS 旋转聚合动画)
- 两列总结:
  - 左 (蓝): **经济财富** = 职业选择权 + 投资认知
  - 右 (红): **精神财富** = 组织视角 + AI 黑领
- 战绩条: **符见效了 · 1 跳槽 · 2 转岗 · 1 扩 scope · 2 面试中**
- 大字 finale: **真 正 的 一 夜 暴 富 · 是 长 出 判 断 力**
- 右上角: 二维码 (`assets/qr/vote.png`), 旁配文字:
  - **⬆ 扫码抽本命开富符 / 给 E 夜暴富投一票**
  - 二维码加抖动提示 (CSS shake 动画, 每 3s 一次)
- 底部: **此符不保 E 夜暴富 —— 但保长期财富!**
- Confetti 喷彩花动画 (canvas 或 CSS 实现)

---

## 视觉规范

- **配色**: 主红 `#a01818` / 金 `#f7d97e` / 暗金 `#c8941a` / 宣纸黄 `#f4e4bc` / 黑底 `#1a0505`
- **字体**: `"STKaiti", "KaiTi", "Kaiti SC", "楷体", "STSong", "宋体", serif`
- **猫 SVG**: 直接从 reference/old_slides.html 复制白猫 / 黑猫的 JS 绘制函数 (drawCat 等)
- **符牌组件**: 复用 `.talisman` / `.talisman-head` / `.talisman-line` CSS
- **音效**: 不需要嵌入 (现场用蓝牙音箱), 但可以保留 console hint 或 keyboard shortcut

## 交互

- 方向键 ← → / Space 切 slide
- 数字键 1-9 直接跳转
- 底部小导航 (复用 old_slides.html 的 `#nav`)
- ESC 切回封面

## 输出

写入 `/Users/a965598/eyebaofu-final/index.html` 单文件。完成后用 `open index.html` 在 Safari 打开测试。

## 不要做的事

- 不要拆成多个 HTML 文件 — 必须单文件方便投影机拷贝
- 不要引入外部 JS 库 (no React / Vue / D3 / Three.js)
- 不要改演讲词的措辞 — 严格按上面对联和文案
- 不要超过 11 张 slide
- 不要在猫边框 / 道长画像里用真人照片以外的 emoji 替代 (要用真照片 from assets/)

---

# 🔊 追加规格 v2: 音效 + 高级动画

## 音效系统 (Web Audio API 合成,不下载外部文件)

在 HTML 顶部加一个 `SoundEngine` 模块,用 `AudioContext` + `OscillatorNode` + `GainNode` 实时合成。
**无外部音频文件**,所有音效在浏览器里生成。

### 必备音效 (函数清单)

| 函数 | 用途 | 实现要点 |
|---|---|---|
| `sfx.gong()` | 开场锣 (Slide 1 "开/坛") | 低频 sine 80Hz + 高频 metallic sine 1200Hz, 衰减 2s, reverb 模拟 |
| `sfx.bell()` | 道长入场 / 授符 (Slide 4, 7-10) | "叮~" 短促铃声: sine 1800Hz + 三角波 900Hz, 衰减 0.4s |
| `sfx.drum()` | 鼓点 (slide 切换) | 低频 sine 120Hz → 60Hz pitch sweep, 衰减 0.15s, 配 noise burst |
| `sfx.woodfish()` | 木鱼 (对联落下) | 短促 square 600Hz, 衰减 0.05s, 像 "笃" |
| `sfx.levelup()` | 终极开富符合体 (Slide 11) | 上行 arpeggio: C5→E5→G5→C6, 每音 0.1s, 类似 RPG升级音 |
| `sfx.confetti()` | 撒花结尾 | 多个 sine 波 + 白噪声爆破, 模拟 pop pop pop |
| `sfx.wave()` | Token猫的浪潮 (Slide 6) | 持续低频 brown noise, 0.3s 衰减循环 |
| `sfx.swoosh()` | 道长走入 / slide 切换 | filtered noise sweep, 200Hz→3000Hz, 0.4s |
| `sfx.scroll()` | 对联展开 | filtered noise (paper rustle), 0.6s |

### Web Audio 实现模板

```js
class SoundEngine {
  constructor() {
    this.ctx = null;  // lazy init on first user gesture
    this.muted = false;
  }
  init() {
    if (this.ctx) return;
    this.ctx = new (window.AudioContext || window.webkitAudioContext)();
    // master gain + simple convolver reverb
    this.master = this.ctx.createGain();
    this.master.gain.value = 0.6;
    this.master.connect(this.ctx.destination);
  }
  gong() {
    this.init(); if (this.muted) return;
    const t = this.ctx.currentTime;
    [80, 240, 480, 1200, 1800].forEach((f, i) => {
      const o = this.ctx.createOscillator(); const g = this.ctx.createGain();
      o.type = i < 2 ? 'sine' : 'triangle'; o.frequency.value = f;
      g.gain.setValueAtTime(0.4 / (i+1), t);
      g.gain.exponentialRampToValueAtTime(0.001, t + 2.5);
      o.connect(g).connect(this.master); o.start(t); o.stop(t + 2.5);
    });
  }
  bell() {
    this.init(); if (this.muted) return;
    const t = this.ctx.currentTime;
    [1800, 900, 2700].forEach((f, i) => {
      const o = this.ctx.createOscillator(); const g = this.ctx.createGain();
      o.type = 'sine'; o.frequency.value = f;
      g.gain.setValueAtTime(0.3 / (i+1), t);
      g.gain.exponentialRampToValueAtTime(0.001, t + 0.5);
      o.connect(g).connect(this.master); o.start(t); o.stop(t + 0.5);
    });
  }
  // ... 其余按上述参数实现
}
const sfx = new SoundEngine();
// 第一次按键时 init: document.addEventListener('keydown', () => sfx.init(), {once:true});
```

### 音效与 slide 绑定

```js
const slideHooks = {
  0: () => sfx.gong(),                      // Slide 1 开场
  1: () => sfx.drum(),                      // Slide 2 立组
  2: () => sfx.swoosh(),                    // Slide 3 11猫
  3: () => { sfx.bell(); sfx.bell(); },     // Slide 4 道长入场 (两声铃)
  4: () => sfx.drum(),                      // Slide 5 12场
  5: () => sfx.wave(),                      // Slide 6 两猫入山 (浪潮)
  6: () => { sfx.bell(); setTimeout(()=>sfx.scroll(), 300); }, // Slide 7 第一道符
  7: () => { sfx.bell(); setTimeout(()=>sfx.scroll(), 300); },
  8: () => { sfx.bell(); setTimeout(()=>sfx.scroll(), 300); },
  9: () => { sfx.bell(); setTimeout(()=>sfx.scroll(), 300); },
 10: () => { sfx.levelup(); setTimeout(()=>sfx.confetti(), 800); }, // Slide 11 高潮
};
// 在 showSlide(i) 里调用 slideHooks[i]?.();
```

### UI 控制

- 屏幕右下角加一个 🔊 / 🔇 按钮 (`#sfx-toggle`), 点击切换 `sfx.muted`
- 默认 **打开**, 但因为浏览器策略, 第一次必须用户按键才会响 (在 keydown 里 `sfx.init()`)

---

## 高级动画 (在原有基础上增加)

### 全局: slide 切换转场

每张 slide 进入时用 **舞台幕布** 效果:
- 一道金色光带从左→右扫过, 0.5s
- 同时 slide 内容 `transform: translateY(20px)` → `0` + `opacity: 0 → 1`
- CSS keyframe `@keyframes stage-enter`

### Slide 1 (开场): 已有"开/坛"字滑入,加强:
- 黑底先有一束 spotlight 圆从中心扩散 (radial gradient mask 动画 0.6s)
- "开" 从左侧推入时带轻微 rotate(-10deg → 0), 同步播 `gong()`
- "坛" 从右侧推入,同样 rotate(10deg → 0)
- 副标题 "求·符·大典" 一字一字弹出 (0.1s 间隔, 每字 transform: scale(0)→scale(1) bounce)

### Slide 3 (11只猫): 头像入场
- 11 张猫脸框 **错位掉落** 进场: 每张 `translateY(-100vh) → 0` + 弹簧缓动, stagger 80ms
- 每张落地时配 `sfx.woodfish()` (笃笃笃 11 声)
- 落地后微微 wiggle ±3°

### Slide 4 (四位道长): 道长走入感 ⭐
**重点动画**:
- 4 位道长从屏幕底部一个个 **走入**: `translateY(100vh) → 0`, 每位间隔 250ms
- 每位入场时:
  - `sfx.bell()` 一声
  - 头部上方道士帽先于身体出现 0.2s
  - 道符旋转环 (八卦圈) 从旋转 0° 加速到 30s/转的稳速
- 4 位全部站定后,4 圈金色光环同时收缩亮一下 (flash)
- 背景祥云持续飘动 (`@keyframes drift` 30s linear infinite)

### Slide 5 (12场修行): polaroid 砖墙
- 7 张活动照片 **逐张抛入** (像甩到墙上),每张 stagger 150ms
- 入场: `translateX(-50vw) rotate(-720deg) scale(0.3) → 0 / final rotate / 1`, 弹簧缓动
- 落定后红色 washi tape 从左上角 "贴" 上 (高度 0→16px, 0.2s)
- 鼠标 hover 单张照片放大 1.1x + 立起 (z-index 提升 + box-shadow 加深)

### Slide 6 (两猫入山): 浪潮 + 锄头动画 ⭐
- **左侧 Token 猫**:
  - 背景 SVG 海浪有 3 层叠加, 每层不同速度 horizontal translate (8s/12s/16s linear infinite)
  - 浪头每 4 秒拍打猫一次, 猫 `translateX(-10px) rotate(-5deg)` 短暂躲闪 (0.3s spring)
  - 同步 `sfx.wave()` (低音量循环)
  - 猫身上 "Token" 火焰图标做 flicker 动画
- **右侧 Title 猫**:
  - 锄头 SVG 上下挥动 (1.2s, ease-in-out infinite)
  - 每次锄头落下: 地面冒一小撮土星 (3 个粒子 div 短生命周期), 配 `sfx.drum()` (低音量)
  - 猫身体跟随锄头节奏前后摆动 ±5°
  - 头顶冒汗珠 (绝对定位 div, opacity loop + translateY)

### Slide 7-10 (四道符): 对联降下 + 符牌展开 ⭐⭐⭐
**核心改造,全部按这个模板**:

1. slide 进入时, 中央先出现一卷**符纸** (高度 0, transform-origin top)
2. `sfx.bell()` 响, 符纸从顶部展开 `height: 0 → 100%` (0.6s, ease-out), 同步 `sfx.scroll()`
3. 符纸展开后, **横批**先飞入 (从顶部 -30px 滑入 + fade in, 0.3s)
4. 然后 **上联** 从右侧像卷轴般降下 (writing-mode: vertical-rl, transform-origin: top, scaleY: 0 → 1, 0.5s)
   - 同步 `sfx.woodfish()`
5. 200ms 后 **下联** 从左侧降下 (镜像)
   - 再一声 `sfx.woodfish()`
6. 对联文字一字一字 **fade in** (stagger 50ms), 像逐字写出
7. 最后底部小字 (心法总结) 从下方 fade up

**对联 CSS 关键代码**:
```css
.couplet {
  writing-mode: vertical-rl;
  text-orientation: upright;
  font-size: 2.2rem; font-weight: 900;
  color: #4a1d10;
  background: linear-gradient(180deg, #f4d97e 0%, #e8c884 100%);
  border: 3px solid #a01818;
  padding: 30px 18px;
  border-radius: 6px;
  box-shadow: 0 4px 20px rgba(160,24,24,0.3);
  letter-spacing: 0.3em;
  transform-origin: top center;
  animation: couplet-drop 0.5s ease-out both;
}
@keyframes couplet-drop {
  0%   { transform: scaleY(0); opacity: 0; }
  100% { transform: scaleY(1); opacity: 1; }
}
.couplet-char {
  display: block;
  opacity: 0;
  animation: char-ink 0.4s ease-out forwards;
}
.couplet-char:nth-child(1) { animation-delay: 0.5s; }
.couplet-char:nth-child(2) { animation-delay: 0.55s; }
/* ... 用 JS 动态生成 stagger 也行 */
@keyframes char-ink {
  from { opacity: 0; filter: blur(4px); transform: translateY(-6px); }
  to   { opacity: 1; filter: blur(0); transform: translateY(0); }
}
```

8. 道长画像 (圆形头像 + 道帽) 在符牌右上角弹出 (从 scale(0) bounce 到 1, delay 0.8s),配 `sfx.bell()`
9. 左侧的猫 (Token / Title) **接符动作**: 跳起来 1 次 (translateY(-20px) → 0, 0.4s spring)

### Slide 11 (终极开富符): 高潮 ⭐⭐⭐⭐
- 进入时屏幕**全白闪一下** (flash overlay opacity 0→1→0, 0.3s)
- 同步 `sfx.levelup()` (上行音阶)
- 4 道符 SVG 从屏幕四角向中心**飞汇聚**, 边飞边旋转, 最后在中心**爆发金光** (radial gradient 扩散动画)
- 中心出现 "终极开富符" 大字, 字体本身做金色 shimmer (linear-gradient 滚动)
- 两猫从左右两侧走到山头中央, 对拜 (transform: rotate ±10° 来回)
- 4 秒后 confetti 撒花 (canvas 撒粒子) + `sfx.confetti()`
- QR 码持续 wiggle (每 3 秒 shake 0.5s)
- 底部 "此符不保E夜暴富 / 但保长期财富" 字打印机效果 (字符逐个出现)

### Confetti 实现 (canvas)

```js
function confetti(canvas) {
  const ctx = canvas.getContext('2d');
  const particles = [];
  const colors = ['#a01818', '#f7d97e', '#c8941a', '#fff', '#ff6b6b'];
  for (let i = 0; i < 150; i++) {
    particles.push({
      x: canvas.width / 2,
      y: canvas.height / 2,
      vx: (Math.random() - 0.5) * 20,
      vy: (Math.random() - 1) * 15,
      gravity: 0.4,
      color: colors[i % colors.length],
      size: Math.random() * 8 + 4,
      life: 1,
      rot: Math.random() * 360,
      vrot: (Math.random() - 0.5) * 20,
    });
  }
  function tick() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles.forEach(p => {
      p.x += p.vx; p.y += p.vy; p.vy += p.gravity;
      p.rot += p.vrot; p.life -= 0.005;
      ctx.save();
      ctx.translate(p.x, p.y); ctx.rotate(p.rot * Math.PI / 180);
      ctx.globalAlpha = Math.max(0, p.life);
      ctx.fillStyle = p.color;
      ctx.fillRect(-p.size/2, -p.size/2, p.size, p.size * 0.4);
      ctx.restore();
    });
    if (particles.some(p => p.life > 0)) requestAnimationFrame(tick);
  }
  tick();
}
```

---

## 关键提醒

- **AudioContext 必须在用户手势后初始化** (浏览器策略), 在第一次 keydown 里 lazy init
- 音量默认 60%, 不要太大 (现场有蓝牙音箱)
- 所有音效 / 动画都要带 `prefers-reduced-motion` 兜底 (检测到 reduce 就关动画但保留音效)
- 添加 **🔊 mute 切换按钮** 给主持人现场应急

---

## Current task (handed off from CVS Code)

Build a chooser landing page for the GitHub Pages site.

1. Rename the existing `index.html` to `index-v1.html` using `git mv` so history is preserved.
2. Create a new `index.html` that acts as a simple chooser landing page with two buttons/cards:
   - **v1** → links to `index-v1.html`
   - **v2** → links to `index-v2.html`
3. Style it to match the existing 道家求符堂会 aesthetic — red/gold palette, cat illustrations from `assets/` if appropriate, the same fonts/feel as `index-v1.html` and `index-v2.html`.
4. Keep it single-file HTML with inline CSS/JS, no external dependencies (consistent with the rest of the project).
5. Add brief labels under each button so visitors understand the difference. Confirm wording by skimming the two files. Suggested:
   - v1 = original horizontal slide deck
   - v2 = full-screen vertical scroll couplet layout
6. Suggest the user preview locally by opening `index.html`, then commit with a clear message and push to `origin/main` so GitHub Pages updates.

---

## Follow-up task (handed off from CVS Code)

Add a third option to the chooser landing page (`index.html`):

1. Add a **v3** button/card linking to `index-v3.html`, matching the style of the existing v1 and v2 cards.
2. Skim `index-v3.html` to write an accurate short label describing what v3 is.
3. Make sure the layout still looks balanced with three cards instead of two (adjust grid/spacing as needed, keep it responsive).
4. Commit with a clear message and push to `origin/main`.
