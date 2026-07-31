# vibe-unpack

**把普通人脑子里的模糊感觉，变成清晰、可执行、可验证的需求。**

vibe-unpack 是一个专为非技术用户设计的「需求解包器」。它通过结构化的追问，把「我想做一个像小红书但更简单的」这种模糊表达，一步步展开成带有硬约束、决策权衡、成功定义的完整需求图谱。

**核心理念**：在写一行代码、推荐一个技术栈、匹配一个技能之前，先把需求真正搞清楚。

---

## 快速开始

```bash
# 查看完整示例（推荐）
cat vibe-unpack/examples/c1-child-daily/demand-spec.md

# 查看可视化知识图
cat vibe-unpack/examples/c1-child-daily/demand-graph.mmd
# （用支持 Mermaid 的编辑器打开，或粘贴到 https://mermaid.live）
```

---

## 它解决了什么？

普通人说需求时通常只有：
- 一种感觉（"我想记录孩子日常，但不要太复杂"）
- 一个场景（"给我的手作店做一个网站"）
- 一种情绪（"现在的工具都太烦人了"）

而真正的需求是：
- 硬约束（"我完全不会编程，3个月后可能就不管了"）
- 隐性假设（"我以为要像小红书一样，其实我只需要自己能快速翻到旧记录"）
- 权衡决策（"多人协作 vs 极简维护，我选极简"）
- 成功定义（"3个月后我还能自己维护，奶奶能自己看到内容"）

**vibe-unpack 就是把前者变成后者。**

---

## 核心铁律（永远不越界）

- ✅ 永远不推荐任何技术栈、框架、数据库
- ✅ 永远不匹配、推荐、筛选任何 skill
- ✅ 永远把「当前 workaround」作为唯一支点
- ✅ 痛点必须具体到「上周三晚上 10 点翻了 20 分钟」
- ✅ 输出必须同时服务**人类**（可视化图）和**AI**（结构化 JSON + Markdown）

---

## 真实案例（6 个完整场景）

| 场景 | 用户最初说的话 | 关键发现 | 推荐路径 |
|------|----------------|----------|----------|
| [C1 孩子日常](vibe-unpack/examples/c1-child-daily) | 像小红书但更简单，记录孩子日常 | 完全不会编程 + 奶奶只会微信 + 可能 3 个月不管 | 先手动整理 + 极简本地方案 |
| [C2 记账](vibe-unpack/examples/c2-accounting) | 做一个简单的记账 App，不要像现有软件那么复杂 | Excel 已经有了，真正痛点是分类太细 + 月底对账 | 先把 Excel 砍成 4-5 个粗分类，验证 1 个月 |
| [C3 手作店](vibe-unpack/examples/c3-handmade-shop) | 给小手作店做一个清爽网站 | 每天被 5-10 个重复私信打扰才是最大痛 | 先做自动回复验证客服减负，再考虑 no-code |
| [C4 健身](vibe-unpack/examples/c4-fitness) | 记录健身 + 进度曲线激励自己 | 技术能力强但执行力低，复杂工具会更早放弃 | 先用备忘录验证 2 周，再做极简一行输入工具 |
| [C5 家庭相册](vibe-unpack/examples/c5-family-album) | 家庭相册共享，不想用微信 | 奶奶只会微信，技术能力完全不对称 | 混合方案：奶奶看精选推送 + 自己本地完整存档 |
| [C6 小说游戏](vibe-unpack/examples/c6-novel-game) | 把故事做成像原神一样的游戏 | 零编程 + 零美术 + 零预算 + 对复杂度严重低估 | 强制从纯文字 Twine 开始，永远不要从 Unity 开始 |

每个案例都包含完整的可读输出：
- `demand-spec.md` —— 人类可读的需求规格书
- `demand-graph.json` —— AI 可消费的结构化知识图
- `demand-graph.mmd` —— Mermaid 可视化分支与剪枝图
- `README.md` —— 案例解读

---

## 输出示例（C1 节选）

普通妈妈最初只说了一句话：

> 我想做一个像小红书但更简单的 App，专门记录我和孩子的日常。

经过引导后：

**致命约束**：
- 完全不会编程，身边也没有会技术的人 → 任何需要自己维护的方案都死
- 可能 3-6 个月后就不管了 → 必须能自己跑至少半年
- 奶奶只会用微信，技术能力极低 → 再酷的 App 对她也是零价值

**关键决策**：
- 多人协作 vs 极简个人 → 选极简（被「不会编程 + 奶奶不会用」直接剪掉）
- 云端 vs 本地 → 倾向本地（至少前 3 个月先验证）

**下一步行动**（具体可执行）：
1. 本周内把过去 3 个月的内容用固定格式整理一次
2. 找奶奶和老公直接看整理后的内容，观察他们能不能自主操作
3. 两周后自问：如果 3 个月我不管，这个东西还能不能自己用？

完整的可视化见 [examples/c1-child-daily/demand-graph.mmd](vibe-unpack/examples/c1-child-daily/demand-graph.mmd)。

---

## 安装与使用

### 作为 Claude Code Skill（推荐）

```bash
cp -r vibe-unpack ~/.claude/skills/vibe-unpack
```

之后在对话中遇到模糊需求时，Claude 会自动加载。

### 手动使用

直接把 `SKILL.md` 的内容作为 system prompt 喂给任何模型即可。

---

## 项目结构

```
vibe-unpack/                    # 开发主体（核心规则、示例、模板）
docs/                           # 项目层面文档
references/                     # 外部参考项目（完整克隆）
archive/                        # 废弃内容
```

---

## 设计原则

完整原则见 [design-A-core-principles.md](vibe-unpack/design/design-A-core-principles.md)。

核心只有一条：

> **在冲动地说「我要做一个 App」之前，先把「为什么要做」「能不能做」「做了之后会死在哪」这三件事彻底搞清楚。**

---

## 状态

- ✅ 设计完成（核心规则、图谱 schema、6 个压力场景）
- ✅ MVP 实现完成（SKILL.md 可直接使用）
- ✅ 6 个场景全部产出真实可读输出
- ✅ 本地已部署到 `~/.claude/skills/vibe-unpack`

---

## License

MIT（或按你的喜好）

---

**现在打开 [vibe-unpack/examples/c1-child-daily/demand-spec.md](vibe-unpack/examples/c1-child-daily/demand-spec.md) 开始体验。**
