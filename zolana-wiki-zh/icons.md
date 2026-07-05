# 图标与符号（Icons & Glyphs）· 零表情系统

# 图标系统

Zenko 在游戏内使用**零象形表情符号**。每个符号都是来自整合的 `assets/ui` 集的手工像素 PNG。本页以大尺寸呈现完整图库，附其名称和含义——并使用它所记录的正是这些图标来呈现。

> 说明：下方"资源名"为游戏使用的图标资源标识符（原站保留）。

## 货币 · 8 个符号

| 名称 | 含义 | 资源名 |
|---|---|---|
| Gold | 主要软货币 | icon_gold |
| Gem | 高级第二货币 | icon_gem |
| $ZOLANA | 链上代币币 | icon_zenko |
| SOL | Solana 货币 | icon_sol |
| Coin | 大型 HUD/加载币 | coin |
| Heads | 抛硬币正面 | icon_coin_heads |
| Tails | 抛硬币反面 | icon_coin_tails |
| Shard | 通用蓝色碎片 | icon_shard |

## 材料 · 制作层级 T1–T4 + 遗物碎片

HUD 图标（icon_*）与全尺寸道具美术（material/*）配对。

| 名称 | 含义 | 资源名 |
|---|---|---|
| Glimmer Dust | T1 材料 | icon_glimmer |
| Mana Shard | T2 材料 | icon_mat_mana_shard |
| Astral Core | T3 材料 | icon_astral |
| Gem Catalyst | T4 材料（稀有） | icon_catalyst |
| Relic Shard | 遗物制作材料 | icon_relic_shard |
| Glimmer（全） | T1 道具美术 | material/glimmer_dust |
| Mana（全） | T2 道具美术 | material/mana_shard |
| Astral（全） | T3 道具美术 | material/astral_core |
| Catalyst（全） | T4 道具美术 | material/gem_catalyst |
| Relic Shard（全） | 遗物道具美术 | material/relic_shard |

## 元素徽章 · 仅 CSS 颜色——不存在元素 PNG

元素被呈现为彩色文本徽章（.el-badge）和 10px 圆点（.el-dot），而非图标文件。

| 元素 | Hex · 主题 |
|---|---|
| TERRA | #8b5a2b · 大地 |
| FLORA | #00c864 · 植物 |
| AQUA | #0096ff · 水 |
| AERO | #c8e6ff · 风 |
| IGNIS | #ff5000 · 火 |
| VOID | #9b5de5 · 暗 |
| LUX | #f6c945 · 光 |

## 稀有度颜色与边框 · 6 种方块边框

稀有度是一个方块边框颜色（.tile / .index-cell），而非印章。

| 稀有度 | Hex |
|---|---|
| Common | #969696 |
| Uncommon | #00c800 |
| Rare | #0064ff |
| Epic | #9600ff |
| Legendary | #ff9600 |
| Mythical | #ff00ff |

## 变体标记 · 闪光 / 进化 / 概率徽章

| 名称 | 含义 | 资源名 |
|---|---|---|
| Sparkle | 闪光 / 稀有光泽 | icon_sparkle |
| Star | 评级 / 精选 | icon_star_front |
| Evolve | 阶段进程 | icon_evolve_arrow |
| <5%（Rate · Rare） | 金色掉落徽章 | .rate-badge.rare |
| 5–20%（Rate · Uncommon） | 银色掉落徽章 | .rate-badge.uncommon |
| >20%（Rate · Common） | 灰色掉落徽章 | .rate-badge.common |

## 遗物属性与槽位徽章 · 10 属性 · 5 槽位

| 名称 | 含义 | 资源名 |
|---|---|---|
| Attack | 固定伤害 | relic/stat/attack |
| Ferocity | 暴击伤害 | relic/stat/ferocity |
| Fortune | 金币 / 幸运 | relic/stat/fortune |
| Guard | 防御 | relic/stat/guard |
| Might | 力量 | relic/stat/might |
| Precision | 暴击几率 | relic/stat/precision |
| Siphon | 吸血 | relic/stat/siphon |
| Swiftness | 速度 | relic/stat/swiftness |
| Vitality | HP | relic/stat/vitality |
| Ward | 抵抗 | relic/stat/ward |
| Amulet | 遗物槽位 | relic/slot/amulet |
| Ring | 遗物槽位 | relic/slot/ring |
| Idol | 遗物槽位 | relic/slot/idol |
| Charm | 遗物槽位 | relic/slot/charm |
| Sigil | 遗物槽位 | relic/slot/sigil |

## HUD / 导航符号 · 导航与状态集

| 名称 | 含义 | 资源名 |
|---|---|---|
| XP | 经验 | icon_xp |
| Power | 队伍力量要求 | icon_power |
| Stamina | 探索成本 | icon_stamina |
| Heart | 幸福度 | icon_heart |
| Timer | 时长 / 冷却 | icon_timer |
| Stats | 属性面板 | icon_stats |
| Bell | 通知 | icon_bell |
| Receipt | 出售通知 | icon_receipt |
| Search | 放大镜 | icon_search |
| Eye | 查看 / 旁观 | icon_eye |
| Lock | 锁定 / 已挂单 | icon_lock |
| Warn | 警告 | icon_warn |
| Settings | 齿轮 | icon_settings |
| Dungeon | 地下城标签 | icon_dungeon |
| Creatures | 图鉴标签 | icon_creatures |
| Bag | 库存标签 | icon_bag |
| Shop | 商店标签 | icon_shop |
| Market | 市场标签 | icon_market |
| Forge | 强化标签 | icon_forge |
| Breed | 繁殖标签 | icon_breed |
| Nest | 孵化标签 | icon_nest |
| Plot | 家园基地标签 | icon_plot |
| Style | 衣柜标签 | icon_style |
| Relics | 遗物标签 | icon_relics |
| Daily | 每日奖励 | icon_daily |
| Quest | 任务 | icon_quest |
| Decor | 装饰模式 | icon_decor |
| Decor Placed | 已放置状态 | icon_decor_placed |
| Home Island | 城镇导航 | icon_home_island |
| Town Gate | 进入城镇 | icon_town_gate |
| Signpost | 方向 | icon_signpost |
| Chat | 城镇聊天 | icon_chat |
| Friends | 好友列表 | icon_friends |
| Online | 在线玩家 | icon_players_online |
| Online Pip | 绿色状态点 | icon_online_pip |
| Leaderboard | 排名 | icon_leaderboard |
| Paw | 伙伴 | icon_paw |
| Chest | 宝藏 / 奖励 | icon_chest |
| Egg | 通用蛋 | icon_egg |
| Mystery Egg | 不剧透繁殖蛋 | mystery_egg |
| Breed Emblem | 心形蛋徽记 | breed_emblem |
| Swords | 战斗 / 派遣 | icon_swords |
| Shield | 防御 | icon_shield |
| PvP Ticket | 竞技场入场 | icon_pvp_ticket |
| Raid Boss | 合作突袭 | icon_raid_boss |
| Pickaxe | 地下城刷取 | icon_pickaxe |
| Handshake | 交易 / 挥手 | icon_handshake |
| Flame | Ignis / 连续 | icon_flame |
| Moon | 夜晚 / 虚空 | icon_moon |
| Zzz | 挂机 / 空闲 | icon_zzz |
| Mug | 赌场休息室 | icon_mug |
| Casino | 赌场入口 | icon_casino |
| Dice | 赌场游戏 | icon_dice |
| Jackpot | 老虎机胜利 | icon_jackpot |
| Rock | 石头剪刀布·石头 | icon_rps_rock |
| Paper | 石头剪刀布·布 | icon_rps_paper |
| Scissors | 石头剪刀布·剪刀 | icon_rps_scissors |
| Epoch Crystal | 社区基金 | icon_epoch_crystal |
| Gavel | 拍卖行 | icon_gavel |
| Raffle Ticket | Zothebyz 抽奖 | icon_raffle_ticket |
| Forge OK | 锻造成功 | icon_forge_success |
| Forge Fail | 锻造失败 | icon_forge_fail |
| Slot · Hat | 衣柜槽位 | icon_slot_hat |
| Slot · Hair | 衣柜槽位 | icon_slot_hair |
| Slot · Outfit | 衣柜槽位 | icon_slot_outfit |
| Slot · Mount | 衣柜槽位 | icon_slot_mount |
| Slot · Accessory | 衣柜槽位 | icon_slot_accessory |
| Bag · All | 筛选：全部 | bag_all |
| Bag · Mats | 筛选：材料 | bag_mat |
| Bag · Eggs | 筛选：蛋 | bag_egg |
| Bag · Decor | 筛选：装饰 | bag_decor |

## 奖项 · 奖牌 · 层级 · 排名符号

| 名称 | 含义 | 资源名 |
|---|---|---|
| Gold Medal | 第 1 名 | icon_medal_gold |
| Silver Medal | 第 2 名 | icon_medal_silver |
| Bronze Medal | 第 3 名 | icon_medal_bronze |
| Trophy | 冠军 | icon_trophy |
| Platinum | PvP 层级 | icon_tier_platinum |
| Champion | PvP 层级 | icon_tier_champion |
| First Raid | 成就 | icon_ach_firstraid |
| Hatch 50 | 成就 | icon_ach_hatch50 |
| Rare Tamer | 成就 | icon_ach_raretamer |
| Boss Slayer | 成就 | icon_ach_bossslayer |
| Mythic | 成就 | icon_ach_mythic |
