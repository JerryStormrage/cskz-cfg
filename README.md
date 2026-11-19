# cskz-cfg

[中文](#中文) | [English](#english)

## 更新记录 / Changelog

- **2026-11-17**：CS2 增加启动自动加载 Green、分批加载 HUD、P 单独切换自动松 W、0 切换 KZ/MG，以及三段模式切换提示音。
- **2026-11-17**: Added CS2 Green autoload, two-part HUD loading, P switching for automatic W release, KZ/MG switching on 0, and three transition sounds.
- **2026-11-12**：恢复 CS:GO Green 右键蹲伏及 Bind 右键蹲跳并自动松 W；撤回 CS:GO 的 I、F8 快捷键及鼠标切换文件。
- **2026-11-12**: Restored CS:GO Mouse2 duck in Green and crouch-jump with automatic W release in Bind; reverted the CS:GO I/F8 shortcuts and mouse switch configs.
- **2026-11-07**：更新 CS2 个人 HUD 偏好；增加 CS2 KZ 自由观察和鼠标攻击／蹲跳切换。
- **2026-11-07**: Updated personal CS2 HUD preferences and added KZ spectate and mouse attack/duck-jump switching.

---

## 中文

本项目分别维护 **CS2** 和 **CS:GO Legacy** 的个人 KZ 配置。两款游戏是独立安装的，配置文件和安装目录不能混用。Green 指原生移动，并不代表所有键位均为游戏默认；配置包含个人灵敏度和键位，请按习惯调整。

### CS2

#### 文件和用途

| 文件 | 用途 |
| --- | --- |
| [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) | KZ 基础设置、原生移动和常用按键，灵敏度 2.0 |
| [cs2kzbind.cfg](cs2/cs2kzbind.cfg) | 启用滚轮起跳时自动松 W |
| [cs2kzbind_off.cfg](cs2/cs2kzbind_off.cfg) | 关闭自动松 W，恢复普通 W 和滚轮跳跃 |
| [cs2kzhud.cfg](cs2/cs2kzhud.cfg)、[cs2kzhud2.cfg](cs2/cs2kzhud2.cfg) | 分两批加载 HUD 和插件偏好 |
| [cs2mg.cfg](cs2/cs2mg.cfg) | MG／竞技按键和 ZE 快捷购买 |
| [cs2kzmouse_move.cfg](cs2/cs2kzmouse_move.cfg)、[cs2kzmouse_attack.cfg](cs2/cs2kzmouse_attack.cfg) | 切换鼠标蹲跳和攻击 |
| [autoexec.cfg](cs2/autoexec.cfg) | 启动时加载 Green |
| [sounds/cs_cfg](cs2/sounds/cs_cfg/) | 三个模式切换提示音，需单独复制到声音目录 |

#### 模式切换

主键盘 **0** 在 KZ 与 MG 之间切换；从 MG 返回时加载 KZ Green。

#### KZ 按键

| 按键 | 功能 |
| --- | --- |
| W / A / S / D | 前进／左移／后退／右移；Bind 中 W 还用于准备自动松 W |
| 空格 / Ctrl / Shift | 跳跃／按住蹲伏／按住静步 |
| E | 使用／交互；不打开购买菜单 |
| Mouse1 / Mouse2 / Mouse3 | 默认主攻击／副攻击／玩家标记；F8 可切换左右键用途 |
| P | 在 Green 和 Bind 之间切换自动松 W |
| O | AD 节拍音开关 |
| `[` / `]` | 分别加载 HUD 第 1 / 2 部分，**仅在主菜单使用** |
| F8 | 切换鼠标左右键的攻击／蹲跳 |
| 1–7 | 直接调用 CS2KZ 高级菜单功能：存点、传送、上一个检查点、下一个检查点、撤销、暂停、重新开始 |
| 滚轮向上 | 保存检查点 |
| N | KZ 飞行／穿墙 |
| I | 自由观察 |
| G | 夜视 |
| X / C | 自动喷涂开关／清理贴花 |
| H / J | 隐藏玩家／持续跳跃统计 |
| Z | 按住使用 Zed meme 语音键位；松开恢复数字键 |
| L | 循环切换 Gamma 1.0 / 1.8 / 2.2 / 2.6 |
| 滚轮向下 | 跳跃；Bind 中配合 W 自动松 W |

数字键 1–7 直接绑定 CS2KZ 的常用高级菜单命令，不需要先打开 radio1 菜单。检查点、飞行、观察、夜视等命令需要服务器插件支持。Z 的 meme 语音仅为个人可选设置；不需要时，可删除 Green 文件中 `+kz_radio`、`-kz_radio` 和 `bind z +kz_radio`；如果已加载，还需在控制台执行 `unbind z` 或重新绑定 Z。

按住 Z 时，1–6 临时对应“收到、否定、欢呼、守住、跟随、感谢”，7 临时解绑；松开 Z 后恢复 KZ 数字键。F8 切换到蹲跳后，鼠标左键为蹲伏、右键为跳跃；再次按 F8 恢复左右键攻击，切换前请松开鼠标左右键。

P 从 Green 进入 Bind 时，按 W 会为下一次向下滚轮起跳准备自动松 W；再次按 P 只恢复普通 W 和滚轮跳跃，不重载完整 Green，因此保留当前灵敏度、AD 节拍音和鼠标状态。**切换前先松开移动、跳跃和蹲伏键。**完整加载 Green 时，节拍音默认关闭、鼠标恢复攻击。

#### MG／竞技模式

在 KZ 中按 **0** 进入 MG；MG 中按 **0** 返回 KZ Green。P 在 MG 中解绑，只负责 KZ 内的 Green／Bind 切换。切换前请松开移动、跳跃、蹲伏和 Z。

MG 默认灵敏度 **1.0**，并使用以下配置中的按键：

| 按键 | MG／竞技模式功能 |
| --- | --- |
| 8（主键盘） | 在灵敏度 1.0 / 0.45 之间切换 |
| F5 | 发送 `!negev`，用于服务器的 ZE Negev 快捷购买 |
| F6 | 发送 `!xz`，用于服务器的 ZE 血针快捷购买 |
| F7 | 发送 `!he`，用于服务器的 ZE 手雷快捷购买 |
| 1–7 | 切换武器／装备槽位 |
| G | 丢弃武器 |
| Z / C | 打开对应无线电菜单 |
| X | 选择 `slot12`，通常用于医疗针 |
| H | 隐藏玩家，需服务器插件支持 |
| W / A / S / D、空格、Ctrl、Shift | 普通移动、跳跃、蹲伏和静步 |
| 滚轮向上 / 向下 | 普通跳跃 |
| E | 使用／交互；不打开购买菜单 |
| Mouse1 / Mouse2 / Mouse3 | 主攻击／副攻击／玩家标记 |
| L | 循环切换 Gamma 1.0 / 1.8 / 2.2 / 2.6 |

F5/F6/F7 的聊天命令需要服务器支持。MG 中 P、N、I、J、O、F8 和 HUD 的 `[` / `]` 解绑。返回 Green 后灵敏度恢复为 **2.0**，8 和 F5/F6/F7 解绑。

切换配置不会主动关闭服务器端已经开启的飞行、夜视、自动喷涂等状态。例如，进入 MG 后 N 已解绑，但先前开启的 KZ 飞行可能仍然开启；需要时可先返回 KZ，再按 N 关闭。

#### HUD 与插件偏好

HUD 由 zer0k 编写，本项目保存的是个人导出设置。按原顺序将 **222 条偏好**分为两部分，各 111 条：

- **第 1 部分 `[`**：基础偏好、计时器、速度、按键和检查点显示，以及跳跃统计的位置。
- **第 2 部分 `]`**：跳跃统计其余外观、路线、比赛、Perf/CJ/Jumpbug 提示、菜单、喷涂及统计报告。

完整恢复时，在主菜单分别按两个键，再连接服务器。共享配置不包含个人 `kzp__stamp`；迁移自己的偏好时，可按插件导出说明自行保留个人标记。

**不要在服务器内加载这两份 HUD 配置。**此前一次性加载大量 `setinfo` 曾导致 `NETWORK_DISCONNECT_OVERFLOW`；分批测试未触发该断线，但分批不减少累计变量数，仍可能触发引擎的 255 个变量限制。已有的服务器偏好是否保留取决于服务器和插件。

#### 模式提示音

| 操作 | 提示音 |
| --- | --- |
| KZ → MG，按 0 | wow |
| MG → KZ Green，按 0 | poi |
| Green → Bind，按 P | very_simple |
| Bind → Green，按 P | 无提示音 |

三个 `.vsnd_c` 文件由已有的 CS:GO 自定义声音使用 CS2 资源编译器转换。没有安装声音文件时，模式切换仍会执行，但不会播放相应声音。

#### 安装与启动

1. 在 Steam 库中右键 **Counter-Strike 2** →“管理”→“浏览本地文件”，打开游戏目录。
2. 将 [cs2](cs2/) 目录下所需的 `.cfg` 文件复制到游戏的 `game/csgo/cfg/`。需要 P、F8 和 0 切换功能时，相关辅助文件也要一起复制。已有同名文件请先备份。
3. 将 [cs2/sounds/cs_cfg](cs2/sounds/cs_cfg/) 中的三个声音文件复制到游戏 `game/csgo/sounds/cs_cfg/`；目录不存在时自行创建。声音文件和 `cfg` 是两个不同目录。
4. 如需启动自动加载 Green，将 [CS2 autoexec.cfg](cs2/autoexec.cfg) 中的命令加入游戏目录已有的 `autoexec.cfg`；没有该文件时可创建。请保留自己已有的内容，并注意键位冲突。
5. 在 Steam 的 CS2“属性”→“通用”→“启动选项”中追加 `-disable_workshop_command_filtering`，保留已有启动项，用空格分隔，然后重启游戏。该参数用于关闭创意工坊地图的命令过滤，参见 [CS2KZ 使用指南](https://cs2kz.org/servers)。
6. 启动后若未自动加载，可在主菜单控制台执行 `exec cs2kzgreen`。在主菜单分别按 `[` 和 `]` 加载 HUD，再进入服务器。

如果用记事本手动创建 cfg，请将“保存类型”设为“所有文件”、编码设为 UTF-8，并确认文件名不是 `.cfg.txt`。检查服务器规则：部分服务器可能禁止辅助绑定；Valve 更新也可能使部分功能失效。

### CS:GO Legacy

以下内容仅适用于 **CS:GO Legacy**，不要复制到 CS2 的配置目录。

#### 文件和按键

| 文件 | 用途 |
| --- | --- |
| [csgokzgreen.cfg](csgo/csgokzgreen.cfg) | Green：原生移动 |
| [csgokzbind.cfg](csgo/csgokzbind.cfg) | Bind：WAD/SAD Null 与可选 2tick 大跳 |
| [autoexec.cfg](csgo/autoexec.cfg) | 启动时加载 Green |

两种模式的灵敏度均为 **2.0**，使用 **P** 切换；每次切换显示最终模式的控制台说明。

| 按键 | Green | Bind |
| --- | --- | --- |
| P | 切换到 Bind | 切换到 Green |
| O | AD 节拍音开关，默认关闭 | AD 节拍音开关，默认关闭 |
| Mouse2 | 按住蹲伏 | 蹲跳并自动松 W |
| K | 无绑定 | 2tick 大跳开关，默认关闭 |
| E | 使用 | 使用；每次 2tick 大跳前重置蹲伏状态 |
| 滚轮向上 | 存点 | 2tick 关闭时存点；开启时触发大跳 |
| 滚轮向下 | 普通跳跃 | 普通跳跃 |

两种模式均保留 G 夜视、N 穿墙、C 清贴花、X 喷涂、H HUD 切换和 J 持续跳跃统计；相关命令需要服务器插件。

**2tick 大跳：**按 K 开启，每次先按 E 重置蹲伏状态，再向上滚动滚轮触发；再次按 K 关闭，滚轮向上恢复存点。感谢 [ss god](https://steamcommunity.com/id/ausbb) 分享，原文件见其 [Bilibili 专栏](https://www.bilibili.com/opus/629511818986799065)。

**WAD/SAD Null：**进入 Bind 后启用，适配 WAD 和 SAD 组合。感谢 [gus god](https://steamcommunity.com/id/lbgdre) 分享 `null.cfg`、`newnull.cfg` 和 `unnull.cfg`；本项目将其合并并补充 SAD 适配。

#### 安装与启动

1. 在 Steam 库中右键 **Counter-Strike: Global Offensive** →“管理”→“浏览本地文件”，进入 Legacy 安装目录的 `csgo/cfg/`。
2. 将 [csgo](csgo/) 中的 Green 和 Bind 文件复制到该目录。已有同名文件请先备份。
3. 如需自动加载 Green，将 [CS:GO autoexec.cfg](csgo/autoexec.cfg) 中的命令追加到游戏目录中的 `autoexec.cfg`；没有该文件时可以创建。保留原有内容并检查冲突。也可在游戏控制台手动执行 `exec csgokzgreen`。

辅助功能是否可用取决于游戏版本和服务器规则，请使用前查阅服务器规定。

---

## English

This project maintains separate personal KZ configs for **CS2** and **CS:GO Legacy**. They are separate installations: their cfg files and installation paths are not interchangeable. Green means native movement, not a fully default key layout. Adjust the personal binds and sensitivity to your preferences.

### CS2

#### Files

| File | Purpose |
| --- | --- |
| [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) | KZ basics, native movement and common binds; sensitivity 2.0 |
| [cs2kzbind.cfg](cs2/cs2kzbind.cfg) | Enable automatic W release for wheel jumps |
| [cs2kzbind_off.cfg](cs2/cs2kzbind_off.cfg) | Restore normal W and wheel jumps |
| [cs2kzhud.cfg](cs2/cs2kzhud.cfg), [cs2kzhud2.cfg](cs2/cs2kzhud2.cfg) | Load HUD and plugin preferences in two parts |
| [cs2mg.cfg](cs2/cs2mg.cfg) | MG/competitive binds and ZE purchases |
| [cs2kzmouse_move.cfg](cs2/cs2kzmouse_move.cfg), [cs2kzmouse_attack.cfg](cs2/cs2kzmouse_attack.cfg) | Switch mouse duck/jump and attack |
| [autoexec.cfg](cs2/autoexec.cfg) | Load Green at startup |
| [sounds/cs_cfg](cs2/sounds/cs_cfg/) | Three transition sounds; install separately in the sound directory |

#### Mode switching

Main keyboard **0** switches between KZ and MG; returning from MG loads KZ Green.

#### KZ keys

| Key | Action |
| --- | --- |
| W / A / S / D | Forward / left / back / right; W also arms automatic release in Bind |
| Space / Ctrl / Shift | Jump / hold duck / hold walk |
| E | Use / interact; does not open the buy menu |
| Mouse1 / Mouse2 / Mouse3 | Default primary attack / secondary attack / player ping; F8 switches mouse buttons |
| P | Toggle automatic W release between Green and Bind |
| O | Toggle A/D keypress sounds |
| `[` / `]` | Load HUD parts 1 / 2 separately, **in the main menu only** |
| F8 | Toggle mouse attack / duck-jump |
| 1–7 | Direct CS2KZ advanced menu actions: checkpoint, teleport, previous checkpoint, next checkpoint, undo, pause and restart |
| Wheel up | Save checkpoint |
| N | KZ noclip |
| I | Free-camera spectate |
| G | Night vision |
| X / C | Toggle auto paint / clear decals |
| H / J | Hide players / toggle always-on jumpstats |
| Z | Hold for Zed meme voice keys; release to restore number keys |
| L | Cycle gamma 1.0 / 1.8 / 2.2 / 2.6 |
| Wheel down | Jump; in Bind, automatic W release when armed |

Keys 1–7 directly bind common CS2KZ advanced menu commands without first opening the radio1 menu. Checkpoint, noclip, spectate and night vision require server support. The Zed meme voice is optional: remove `+kz_radio`, `-kz_radio` and `bind z +kz_radio` from Green if unwanted; after loading it, also run `unbind z` or rebind Z.

While Z is held, 1–6 temporarily become roger, negative, cheer, hold position, follow me and thanks; 7 is temporarily unbound. Releasing Z restores the KZ number keys. F8 switches the mouse to left-button duck and right-button jump; press F8 again to restore attack. Release both mouse buttons before switching.

In Bind, pressing W arms the next downward wheel jump to release W. Pressing P again restores normal W and wheel jump without reloading the full Green cfg, preserving sensitivity, A/D sounds and mouse state. **Release movement, jump and duck before switching.** Loading the full Green cfg resets A/D sounds to off and restores mouse attack.

#### MG / competitive

Press **0** in KZ to enter MG, and **0** in MG to return to Green. P is unbound in MG and only switches Green/Bind in KZ. Release movement, jump, duck and Z before switching.

MG starts at sensitivity **1.0** and uses these configured keys:

| Key | MG / competitive action |
| --- | --- |
| 8 (main keyboard) | Toggle sensitivity 1.0 / 0.45 |
| F5 | Send `!negev` for the server's ZE Negev shortcut |
| F6 | Send `!xz` for the server's ZE healthshot purchase |
| F7 | Send `!he` for the server's ZE grenade shortcut |
| 1–7 | Select weapon / equipment slots |
| G | Drop weapon |
| Z / C | Open the corresponding radio menus |
| X | Select `slot12`, usually the healthshot |
| H | Hide players; requires a server plugin |
| W / A / S / D, Space, Ctrl, Shift | Normal movement, jump, duck and walk |
| Wheel up / down | Normal jump |
| E | Use / interact; does not open the buy menu |
| Mouse1 / Mouse2 / Mouse3 | Primary attack / secondary attack / player ping |
| L | Cycle gamma 1.0 / 1.8 / 2.2 / 2.6 |

F5/F6/F7 send chat commands that require server support. P, N, I, J, O, F8 and HUD `[` / `]` are unbound in MG. Returning to Green restores sensitivity **2.0** and unbinds 8 and F5/F6/F7.

Switching configs does not actively reset plugin states such as noclip, night vision or auto paint. For example, N is unbound in MG while previously enabled KZ noclip may remain active; return to KZ and press N to turn it off if needed.

#### HUD and plugin preferences

The HUD was developed by zer0k; these files contain a personal export. The **222 preferences** are split in original order into two files of 111 settings:

- **Part 1 `[`**: basic preferences, timer, speed, keys and checkpoint displays, plus jumpstats position.
- **Part 2 `]`**: remaining jumpstats appearance, course, race, Perf/CJ/Jumpbug, menu, paint and statistics.

Load both separately in the main menu before connecting. The shared configs omit the personal `kzp__stamp`; follow the plugin's export instructions when migrating your own preferences.

**Do not load either HUD file while connected to a server.** Loading many `setinfo` commands at once previously caused `NETWORK_DISCONNECT_OVERFLOW`; separate loading was tested without that disconnect, but the total variable count remains unchanged and may still hit the engine's 255-variable limit. Retention of server preferences depends on the server and plugin.

#### Transition sounds

| Action | Sound |
| --- | --- |
| KZ → MG, press 0 | wow |
| MG → KZ Green, press 0 | poi |
| Green → Bind, press P | very_simple |
| Bind → Green, press P | None |

The three `.vsnd_c` files were converted from existing custom CS:GO audio using the CS2 resource compiler. Switching still works without the sound files, but the corresponding sounds will not play.

#### Installation and startup

1. In Steam, right-click **Counter-Strike 2** → **Manage → Browse local files**.
2. Copy the required `.cfg` files from [cs2](cs2/) into the game's `game/csgo/cfg/`. Include the helper files for any P, F8 and 0 switching you use. Back up existing files with the same names first.
3. Copy the three files from [cs2/sounds/cs_cfg](cs2/sounds/cs_cfg/) into the game's `game/csgo/sounds/cs_cfg/`, creating the directory if needed. This is separate from `cfg`.
4. To load Green at startup, add the command from [CS2 autoexec.cfg](cs2/autoexec.cfg) to your existing game `autoexec.cfg`, or create it if absent. Preserve existing contents and check for binding conflicts.
5. In CS2 Steam **Properties → General → Launch Options**, append `-disable_workshop_command_filtering`, separated from existing options by a space, and restart. It disables Workshop map command filtering; see the [CS2KZ guide](https://cs2kz.org/servers).
6. If Green did not load automatically, run `exec cs2kzgreen` in the main-menu console. Press `[` and `]` separately in the main menu for HUD, then join a server.

When creating a cfg in Notepad, use “All files” and UTF-8, and ensure the name does not end in `.cfg.txt`. Check server rules: some servers prohibit assists, and Valve updates can affect functionality.

### CS:GO Legacy

This section applies only to **CS:GO Legacy**. Do not copy these files into the CS2 cfg directory.

#### Files and keys

| File | Purpose |
| --- | --- |
| [csgokzgreen.cfg](csgo/csgokzgreen.cfg) | Green: native movement |
| [csgokzbind.cfg](csgo/csgokzbind.cfg) | Bind: WAD/SAD null and optional 2-tick crouch-jumps |
| [autoexec.cfg](csgo/autoexec.cfg) | Load Green at startup |

Both modes use sensitivity **2.0** and switch with **P**. Each switch prints the final mode's console guide.

| Key | Green | Bind |
| --- | --- | --- |
| P | Switch to Bind | Switch to Green |
| O | Toggle A/D sound, initially off | Toggle A/D sound, initially off |
| Mouse2 | Hold duck | Crouch-jump with automatic W release |
| K | Unbound | Toggle 2-tick crouch-jump, initially off |
| E | Use | Use; reset duck before each 2-tick crouch-jump |
| Wheel up | Checkpoint | Checkpoint when off; trigger crouch-jump when on |
| Wheel down | Normal jump | Normal jump |

Both modes retain G night vision, N noclip, C clear decals, X paint, H HUD toggle and J always-on jumpstats; server commands need plugin support.

**2-tick crouch-jump:** Press K to enable; before each jump press E to reset duck, then scroll up. Press K again to disable and restore scroll-up checkpoint. Thanks to [ss god](https://steamcommunity.com/id/ausbb); see the original [Bilibili article](https://www.bilibili.com/opus/629511818986799065).

**WAD/SAD null:** Enabled in Bind and supports WAD and SAD combinations. Thanks to [gus god](https://steamcommunity.com/id/lbgdre) for `null.cfg`, `newnull.cfg` and `unnull.cfg`; this project combines them and adds SAD support.

#### Installation and startup

1. In Steam, right-click **Counter-Strike: Global Offensive** → **Manage → Browse local files**, then open the Legacy installation's `csgo/cfg/`.
2. Copy the Green and Bind files from [csgo](csgo/) into that directory. Back up existing names first.
3. To load Green at startup, append the command from [CS:GO autoexec.cfg](csgo/autoexec.cfg) to the game's `autoexec.cfg`, or create it if absent. Preserve existing contents and check for conflicts. Alternatively, run `exec csgokzgreen` manually in the game console.

Assist availability depends on the game version and server rules; check the server's rules before use.
