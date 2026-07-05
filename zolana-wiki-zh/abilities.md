# 能力（Abilities）· 14 个被动

# 生物能力

每只生物出生时都自带一组固定的**被动能力**——1 到 5 个，列在它的检视卡上。能力是**物种与生俱来的**：你无法替换、学习或移除它们，因此一只生物的能力阵容是其价值的一部分。它们始终生效，且运行不需要任何成本。

能力做两件事：

- **经济光环（Economy auras）**——提高你放置阵容在挂机时赚取的 Gold 金币，是 2026 年金币充裕经济中的主力。
- **实用被动（Utility passives）**——影响喂养、蛋孵化以及你的 PvP 定位。

共有 **14 个具名能力**。其中 8 个已接入当前游戏机制；另外 6 个是生物档案上的风味标签，为未来系统预留（它们仍显示在卡上，但目前不提供加成）。本页明确说明哪个是哪个，并给出每个已接入效果的精确数值。

**光环作用于你的整个阵容**

经济光环读取的是**你放置的每一只生物**，而不仅仅是拥有该能力的那只。单个 **CoinAura** 携带者能一次性提升你所有放置生物的收益，因此构筑良好的阵容会复利叠加。这就是为什么"放置"——而不仅仅是力量——很重要。

## 效果速查表 · 精确数值

以下所有加成均取自游戏实时代码（`idle.ts`、喂养路由和孵化路由）。"作用范围（Scope）"告诉你光环会向哪些生物发放收益。

| 能力 | 效果 | 作用范围 | 状态 |
|---|---|---|---|
| CoinAura | **+10%** 挂机金币 | 所有放置生物（全局） | 生效 |
| Inspiration | **+5%** 挂机金币 | 所有放置生物（全局） | 生效 |
| Radiance | **+5%** 挂机金币 | 所有放置生物（全局） | 生效 |
| PackLeader | **+15%** 挂机金币 | 仅同物种生物 | 生效 |
| ElementalHarmony | **+10%** 挂机金币 | 仅同元素生物 | 生效 |
| EfficientFeeder | 喂食获得的幸福度 **+50%**（30 对比 20） | 自身，每次喂食 | 生效 |
| QuickHatch | 每个放置的携带者使蛋孵化时间 **−10%** | 你所有正在孵化的蛋 | 生效 |
| HappinessKeeper | 将该生物标记为 **Support（辅助）** PvP 原型 | 自身（战斗定位） | 生效 |
| XPBoost | 风味标签——尚未接入加成 | — | 预留 |
| OfflineBoost | 风味标签——尚未接入加成 | — | 预留 |
| ShadowCloak | 风味标签——尚未接入加成 | — | 预留 |
| GemFinder | 风味标签——尚未接入加成 | — | 预留 |
| DoubleDrop | 风味标签——尚未接入加成 | — | 预留 |
| LuckyCharm | 风味标签——尚未接入加成 | — | 预留 |

## 经济光环 · 挂机金币

### 挂机金币如何构成

你放置的阵容每秒都在你离线时产出金币，累积窗口上限为 **8 小时**。每只生物在其中分到的份额为：

> **perCreature = base(rarity, stage) × variantMult × happinessMult × auraMult × relicMult × levelMult**

能力存在于 **auraMult** 中。该乘数从 **1.0** 起步，每个作用于某生物的光环都在其上**相加**其百分比：

> **auraMult = 1 + 全局光环 + PackLeader(同物种) + ElementalHarmony(同元素) + elementBonus**

全局光环（**CoinAura**、**Inspiration**、**Radiance**）在你整个放置阵容中被汇总一次，并应用于**每一只**生物。两个定向光环只向与携带者共享物种或元素的生物发放收益。此外，**Terra** 生物自带内置的 **+10%** 元素加成（`ELEMENT_COIN_BONUS`），叠加在同一插槽中。

| 全局光环 | 值 |
|---|---|
| CoinAura | +10% |
| Inspiration | +5% |
| Radiance | +5% |
| 作用于 | 所有放置生物 |

| 定向光环 | 值 |
|---|---|
| PackLeader | +15%（范围：同物种） |
| ElementalHarmony | +10%（范围：同元素） |

| 元素加成 | 值 |
|---|---|
| Terra | +10% |
| 其他 | +0% |
| 来源 | 与生俱来 |

**叠加是相加，而非相乘**

所有光环都叠加进**同一个**乘数。一只 Terra 生物，若身旁有一个 CoinAura 携带者、一个匹配的 PackLeader 和一个 ElementalHarmony 携带者，可获得 **1 + 0.10 + 0.15 + 0.10 + 0.10 = 1.45×**——即固定 +45%，这还是在幸福度、变体、遗物和等级乘数之前（后者各自再相乘）。

### CoinAura
**为每只放置生物 +10% 挂机金币。** 最强的单个经济被动，也是 Terra 物种成为多数金币农场核心的原因。一个携带者就足以提升整个阵容；额外携带者各自叠加其 +10%。

### Inspiration / Radiance
**各为每只放置生物 +5% 挂机金币。** 又两个全局光环。它们在 Lux 及辅助风味生物上很常见，且两者**也**会把其拥有者在 PvP 中标记为 Support 原型（见下文）。运行多个以层叠它们各自 +5% 的贡献。

### PackLeader
**为同物种生物 +15% 挂机金币。** 最大的单槽加成，但只向匹配物种发放收益——因此 PackLeader 奖励养**复数副本**。一群同种生物中只要有一个 PackLeader，它们全体都获得该加成。

### ElementalHarmony
**为同元素生物 +10% 挂机金币。** 比 PackLeader 更广——任何与携带者共享元素的放置生物都受益。它奖励单元素阵容（全 Aqua 或全 Terra 的场地）。

## 实用被动 · 喂养 · 孵化 · PvP

### EfficientFeeder
喂养一只生物给予 **+20 幸福度**和 **+20 经验**，冷却 10 分钟。EfficientFeeder 把幸福度增益提升 **50%**——携带者每次喂食获得 **+30 幸福度**而非 +20（经验不变）。幸福度以 **每小时 3 点**衰减，并直接放大挂机收益，所以这额外的幸福度随时间累积就是实打实的金币。

### QuickHatch
每个放置的 QuickHatch 携带者使**你所有蛋的孵化时间缩短 10%**。它按携带者叠加，并被钳制以确保孵化时间永不低于**基础值的 10%**（即 9 个携带者 = 下限）。因为它读取的是你的放置阵容——而非蛋——所以停放几只 QuickHatch 生物会加速你运行的每一次孵化。

| QuickHatch 携带者数 | 孵化时间乘数 |
|---|---|
| 0 | 100% |
| 1 | 90% |
| 2 | 80% |
| 3 | 70% |
| 5 | 50% |
| 9+ | 10%（下限） |

### HappinessKeeper
在 PvP 中，生物的战斗**原型**（Nuker / Tank / Support…）通常由其属性读取，但 HappinessKeeper、Radiance 和 Inspiration 会覆盖该读取，把携带者标记为 **Support（辅助）**。辅助生物在 3v3 长老天梯中填补赋能位。在经济方面，HappinessKeeper 是一个"维持士气"的主题被动；它当前的实时挂钩就是 Support 标记。

## 预留被动 · 风味标签

这六个能力印在生物卡上、用于给物种赋予主题，但在当前发布版本中它们**尚未接入加成**。它们目前无成本、无作用——把它们当作为未来系统预留的插槽。此处列出是为求完整，使你在游戏中看到的卡与 wiki 匹配。

| 能力 | 预期风味 | 当前效果 |
|---|---|---|
| XPBoost | 更快的生物升级 | 暂无 |
| OfflineBoost | 更大的离线 / 挂机收益窗口 | 暂无 |
| ShadowCloak | 虚空闪避 / 潜行风味 | 暂无 |
| GemFinder | 从内容中提升 Gem 宝石几率 | 暂无 |
| DoubleDrop | 额外的地下城 / 突袭战利品滚动 | 暂无 |
| LuckyCharm | 全局幸运 / 稀有结果推动 | 暂无 |

**不要为了预留标签而选一只生物**

因为 GemFinder、DoubleDrop 等目前不提供任何加成，它们不应影响你的购买或繁殖决策。以生物的 **CoinAura / PackLeader / ElementalHarmony** 经济光环及其属性来评估它。

## 谁携带什么 · 按能力列出物种

能力阵容因物种而固定（来自 `creatures.ts`）。层级繁殖天梯和混种不携带任何能力——只有**基础蛋物种**、第 30 天的 Wishling，以及活动/神秘/突袭扩展生物才携带。以下是每个能力及携带它的物种。越稀有的生物通常同时携带越多能力（Mythical 神级堆叠 3–5 个）。

### CoinAura（+10% 全局金币）
Cobble、Fuzzrock、Craggle、Crystara、Megalith · Gaiamir、Solivanna、Fortaran、Chronovex · Boulderon、Quarzon、Aurelia、Lucentia · Terraquill、Tidalord、Stratoguard、Geargrove。

### Inspiration（+5% 全局金币）
Skydrift、Aquarine · Leviath、Zephyron、Solivanna、Chronovex、Umbraluxis · Bloomara、Marlance、Cindermane、Zephyrion、Aurelia、Coralisk、Verdania、Emberle、Gustaria、Lucentia。

### Radiance（+5% 全局金币）
Lumen、Glimra · Wishling · Zephyron、Solivanna、Chronovex、Umbraluxis · Zephyrion、Aurelia、Gustaria、Lucentia · Prismark。

### PackLeader（+15% 同物种金币）
Brambark、Smoldra、Florix、Sylvorn · Verdantia、Pyrexis、Nihilarch、Umbraluxis · Bloomara、Coralisk、Verdania · Terraquill、Thornmaw、Magmarok、Umbraxis。

### ElementalHarmony（+10% 同元素金币）
Craggle、Tiddles、Aquarine · Gaiamir、Verdantia、Leviath、Fortaran、Chronovex · Boulderon、Noctilume、Quarzon、Umbrance · Tidalord、Stratoguard、Geargrove。

### EfficientFeeder（+50% 喂食幸福度）
Seedlup。（按携带者数量计最稀有的能力——Common 的 Flora 初始生物是它唯一的持有者。）

### QuickHatch（每携带者 −10% 孵化时间）
Splisho、Gloopy、Tiddles、Aquarine · Leviath · Marlance、Coralisk · Tidalord。

### HappinessKeeper（Support 原型）
Clovy、Brambark、Florix、Sylvorn · Verdantia、Solivanna、Fortaran · Bloomara、Verdania。

### 预留标签携带者

| 能力 | 携带它的物种 |
|---|---|
| XPBoost | Cindle、Flicky、Smoldra · Pyrexis · Marlance、Cindermane、Emberle · Thornmaw、Magmarok |
| OfflineBoost | Gusty、Nimbu、Skydrift · Zephyron · Zephyrion、Gustaria · Stratoguard |
| ShadowCloak | Dimble、Duskee · Nihilarch、Umbraluxis · Noctilume、Umbrance · Umbraxis |
| GemFinder | Crystara、Megalith · Gaiamir、Nihilarch、Chronovex · Boulderon、Noctilume、Quarzon、Umbrance · Umbraxis、Prismark、Geargrove |
| DoubleDrop | Crystara、Megalith · Pyrexis · Terraquill、Thornmaw、Magmarok、Prismark、Geargrove |
| LuckyCharm | Florix、Sylvorn · Verdantia · Bloomara、Cindermane、Aurelia、Emberle |

**查看每只生物的完整档案**

每只生物精确的能力列表、元素、稀有度和属性位于 [生物图鉴（Creatures）](creatures.md) 页。关于这些光环如何供养 2026 年金币充裕的经济，见 [经济与市场（Economy & Market）](economy.md)；关于 PvP 原型系统，见 [战斗与 PvP（Combat & PvP）](combat.md)。
