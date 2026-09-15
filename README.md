# cskz-cfg

[中文](#中文) | [English](#english)

## 中文

个人 CS:GO / CS2 KZ 配置，按 Green（原生移动）和 Bind（辅助绑定）区分。

CS:GO 与 CS2 均使用 **P 切换 Green / Bind**。

CS:GO 通过 `autoexec.cfg` 自动加载，请将本项目的 `autoexec.cfg` 中的内容复制进您的 `autoexec.cfg` 中使用（**注意可能会和您原有的 cfg 冲突**）。

CS2 首次使用先在控制台手动执行 `exec cs2kzgreen`，无需 `autoexec.cfg`。

### 使用说明

- **Green 指原生移动绑定，不代表全部键位均为游戏默认。KZ 相关按键配置会影响游玩 CS2 的其他模式，例如官方竞技、ZE、MG 等，请按需要自行修改。本文档未列出全部按键功能，请查阅 cfg 中的具体配置；大部分配置都有注释，没有编程基础也可以对照阅读。**

- **配置包含个人灵敏度、键位及 HUD 设置，使用前请按自己的习惯调整。**

  HUD 的作者是 zer0k，具体配置由各位玩家自行定义。本项目保存的是我个人的 HUD 偏好设置，您可以按自己的习惯调整并导出。设置默认通过 API 保存，但有时可能未正确加载，因此我将其导出并保存在 cfg 中，方便恢复自己的设置，无需每次手动调整。

- 检查点、传送等命令依赖服务器插件；辅助绑定是否可用取决于游戏版本与服务器规则。

### CS:GO Legacy

| 模式 | 文件 | 用途 |
| --- | --- | --- |
| Green | [csgokzgreen.cfg](csgo/csgokzgreen.cfg) | 原生移动 |
| Bind | [csgokzbind.cfg](csgo/csgokzbind.cfg) | WAD/SAD 适配 Null、右键自动松 W 蹲跳与可选 2tick 大跳 |
|  | [autoexec.cfg](csgo/autoexec.cfg) | 启动默认加载 Green |

两种模式的灵敏度均为 **2.7**，各自独立加载所需设置，每次切换只显示最终模式的控制台说明。

| 按键 | Green | Bind |
| --- | --- | --- |
| P | 切换到 Bind | 切换到 Green |
| O | AD 节拍音开关，默认关闭 | AD 节拍音开关，默认关闭 |
| Mouse2 | 按住蹲伏 | 蹲跳并自动松 W |
| K | 无绑定 | 2tick 大跳开关，默认关闭 |
| E | 使用 | 使用；每次触发 2tick 大跳前按下，重置蹲伏状态 |
| 滚轮向上 | 存点 | 2tick 关闭时存点；开启后，每次先按 E 再向上滚动触发大跳 |
| 滚轮向下 | 普通跳跃 | 普通跳跃 |
| Mouse4 / Mouse5 | 无绑定 | 无绑定 |

- **P 只切换模式**，不单独开关自动松 W。进入 Bind 即启用右键辅助；返回 Green 后右键恢复普通蹲伏。

- 两种模式均保留 G 夜视、N 穿墙、C 清贴花、X 喷涂、H HUD 切换，以及 J 持续跳跃统计开关；相关服务器命令需要插件支持。

- **2tick 大跳：**按 K 开启，先按 E 重置蹲伏状态，再正常向上滚动滚轮即可触发。**每次触发前都需要先按 E 重置。**再次按 K 关闭后，滚轮向上恢复存点。

  感谢 [ss god](https://steamcommunity.com/id/ausbb) 的开源分享，原文件详细信息参见他的 [Bilibili 专栏](https://www.bilibili.com/opus/629511818986799065)。

- **WAD/SAD 适配 Null：**进入 Bind 模式即可启用，适配 WAD 和 SAD 按键组合，解决原先普通 Null 仅适用于 WA 或 WD 组合的使用限制。

  感谢 [gus god](https://steamcommunity.com/id/lbgdre) 拿下 2023 年第二届生肖杯冠军后在生肖杯群内的开源分享：`null.cfg`、`newnull.cfg` 和 `unnull.cfg`。本项目仅将这三份配置合并整理，并补充了 SAD 适配。

### CS2

| 模式 | 文件 | 用途 |
| --- | --- | --- |
| Green | [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) | 原生移动 |
| Bind | [cs2kzbind.cfg](cs2/cs2kzbind.cfg) | 目前仅支持滚轮向下起跳并自动松 W，其他 Bind 功能待日后研究整理 |

首次使用先执行 `exec cs2kzgreen`。松开移动、跳跃和蹲伏键后按 P 进入 Bind，再按 P 重新加载 Green 并关闭辅助。

| 按键 | 功能 |
| --- | --- |
| P | Green / Bind 模式切换 |
| O | AD 节拍音开关 |
| G | `sw_nv` 夜视开关，依赖服务器插件 |
| L | Gamma 1.0 / 1.8 / 2.2 / 2.6 循环切换 |
| Mouse2 | 按住蹲伏 |
| Z | 按住使用 Zed meme 语音键位，松开恢复 KZ 数字键 |

两种模式均保留 G 夜视、N 穿墙、C 清贴花、X 喷涂、H HUD/玩家隐藏切换，以及 J 持续跳跃统计开关（`kz_jsalways`，直接执行控制台命令）；相关服务器命令需要插件支持。

加载 Green 时 O 默认关闭；进入 Bind 时保持当前节拍音状态。Bind 中按 W 会为下一次向下滚轮起跳准备自动松 W。

### 安装与加载

1. 下载仓库：点击 **Code → Download ZIP**，解压。

2. 打开 Steam 库，找到对应游戏，通过“管理 → 浏览本地文件”进入安装目录，再复制配置文件。下方路径中的 `…` 表示您自己的安装路径，具体盘符和 Steam 库位置可能不同。

   **CS:GO：**右键点击您的 **Counter-Strike: Global Offensive**，选择“管理 → 浏览本地文件”。打开的目录应为 `…\steam\steamapps\common\csgo legacy`。依次进入 `csgo` → `cfg`，将解压后 `csgo/` 文件夹中的 `csgokzgreen.cfg` 和 `csgokzbind.cfg` 放入 `…\steam\steamapps\common\csgo legacy\csgo\cfg`。

   **CS2：**同样在 Steam 库中右键点击 **Counter-Strike 2**，选择“管理 → 浏览本地文件”，再依次进入 `game` → `csgo` → `cfg`。将解压后 `cs2/` 文件夹中的 `cs2kzgreen.cfg` 和 `cs2kzbind.cfg` 放入 `…\steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg`。

3. 打开游戏控制台，执行下方命令；两款游戏均使用 P 切换。

| 游戏 | 加载 Green | 加载 Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2kzgreen` | 先加载 Green，再按 P |

CS:GO 若需启动默认 Green，将 `csgo/autoexec.cfg` 放入同一目录；如果已有 autoexec，只在原文件末尾添加 `exec csgokzgreen`，保留原有设置。游戏已运行时，手动执行一次 `exec csgokzgreen` 即可加载新版。

CS2 的两份文件需一起安装；Bind 不会自动调用 Green，首次加载请使用 Green 入口。

---

## English

Personal CS:GO / CS2 KZ configs, organized into Green (native movement) and Bind (assisted binds).

Both games use **P to switch Green / Bind**.

CS:GO loads automatically through `autoexec.cfg`. Copy the contents of this project's `autoexec.cfg` into your own `autoexec.cfg` (**these settings may conflict with your existing configs**).

For CS2, manually run `exec cs2kzgreen` in the console before first use. No `autoexec.cfg` is required.

### Usage notes

- **Green refers to native movement binds, not a completely default keyboard layout. KZ keybinds also affect other CS2 modes, such as official Competitive, ZE, and MG, so adjust them as needed. This document does not list every key function; check the cfg files for the full configuration. Most settings include comments to help you understand them without programming experience.**

- **These configs include personal sensitivity, keybinds, and HUD settings. Adjust them to your needs.**

  The HUD was developed by zer0k, and each player customizes their own configuration. This project includes my personal HUD preferences, which you can adjust and export to suit your needs. Settings are normally saved through an API, but may occasionally fail to load correctly. I therefore keep an exported copy in the cfg to restore my setup without having to adjust everything manually each time.

- Checkpoint and teleport commands require server plugins. Assist availability depends on the game version and server rules.

### CS:GO Legacy

| Mode | File | Purpose |
| --- | --- | --- |
| Green | [csgokzgreen.cfg](csgo/csgokzgreen.cfg) | Native movement |
| Bind | [csgokzbind.cfg](csgo/csgokzbind.cfg) | WAD/SAD-compatible null binds, Mouse2 crouch-jump with automatic W release, and optional 2-tick crouch-jumps |
|  | [autoexec.cfg](csgo/autoexec.cfg) | Load Green on startup |

Both modes use **2.7 sensitivity** and initialize their own settings. Each switch prints only the final mode's console guide.

| Key | Green | Bind |
| --- | --- | --- |
| P | Switch to Bind | Switch to Green |
| O | Toggle A/D sounds, default OFF | Toggle A/D sounds, default OFF |
| Mouse2 | Hold to duck | Crouch-jump with automatic W release |
| K | Unbound | Toggle 2-tick crouch-jumps, default OFF |
| E | Use | Use; press before every 2-tick crouch-jump to reset the duck state |
| Wheel up | Checkpoint | Checkpoint when OFF; when ON, press E before each scroll-up crouch-jump |
| Wheel down | Normal jump | Normal jump |
| Mouse4 / Mouse5 | Unbound | Unbound |

- **P only switches modes.** The Mouse2 assist is active in Bind; returning to Green restores ordinary ducking.

- Both modes retain G for night vision, N for noclip, C to clear decals, X to paint, H to toggle the HUD, and J to toggle always-on jumpstats. Server commands require plugin support.

- **2-tick crouch-jump:** Press K to enable it, press E to reset the duck state, then scroll up normally to trigger the jump. **Press E to reset before every attempt.** Press K again to disable it and restore scroll-up checkpoints.

  Thanks to [ss god](https://steamcommunity.com/id/ausbb) for sharing the source. For details about the original file, see his [Bilibili article](https://www.bilibili.com/opus/629511818986799065).

- **WAD/SAD-compatible null binds:** Enter Bind mode to enable support for WAD and SAD key combinations, extending the original basic null setup that only supported WA or WD combinations.

  Thanks to [gus god](https://steamcommunity.com/id/lbgdre) for sharing the source configs `null.cfg`, `newnull.cfg`, and `unnull.cfg` in the Shengxiao Cup group after winning the second Shengxiao Cup in 2023. This project's changes are limited to combining and organizing those three configs and adding SAD support.

### CS2

| Mode | File | Purpose |
| --- | --- | --- |
| Green | [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) | Native movement |
| Bind | [cs2kzbind.cfg](cs2/cs2kzbind.cfg) | Currently only supports scroll-down jumps with automatic W release; other bind features will be explored and organized in the future |

Run `exec cs2kzgreen` first. Release movement, jump, and duck keys before pressing P to enter Bind. Press P again to reload Green and disable the assist.

| Key | Action |
| --- | --- |
| P | Switch Green / Bind |
| O | Toggle A/D keypress sounds |
| G | Toggle night vision; requires the server plugin |
| L | Cycle gamma: 1.0 / 1.8 / 2.2 / 2.6 |
| Mouse2 | Hold to duck |
| Z | Hold for Zed meme voice keys; release to restore KZ number keys |

Both modes retain G for night vision, N for noclip, C to clear decals, X to paint, H to toggle the HUD and player visibility, and J to toggle always-on jumpstats (`kz_jsalways`, executed directly as a console command). Server commands require plugin support.

Loading Green resets A/D sounds to OFF; entering Bind preserves their current state. In Bind, pressing W arms the next downward wheel takeoff to release W.

### Installation and loading

1. Download the repository using **Code → Download ZIP**, then extract it.

2. Open your Steam Library, find the game, and choose **Manage → Browse local files** to open its installation folder, then copy the configs. In the paths below, `…` represents your installation path; the drive and Steam library location may vary.

   **CS:GO:** Right-click **Counter-Strike: Global Offensive** and select **Manage → Browse local files**. The folder should be `…\steam\steamapps\common\csgo legacy`. Open `csgo` → `cfg`, then copy `csgokzgreen.cfg` and `csgokzbind.cfg` from the extracted `csgo/` folder into `…\steam\steamapps\common\csgo legacy\csgo\cfg`.

   **CS2:** Right-click **Counter-Strike 2** in your Steam Library, select **Manage → Browse local files**, then open `game` → `csgo` → `cfg`. Copy `cs2kzgreen.cfg` and `cs2kzbind.cfg` from the extracted `cs2/` folder into `…\steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg`.

3. Run the appropriate command below in the game console. Switch modes in either game with P.

| Game | Load Green | Load Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2kzgreen` | Load Green first, then press P |

To start CS:GO in Green, place `csgo/autoexec.cfg` in the same directory. If you already have an autoexec, preserve it and append `exec csgokzgreen`. If the game is running, execute `exec csgokzgreen` once to load the update.

Install both CS2 files together. Bind does not automatically load Green; use the Green entry for initial setup.
