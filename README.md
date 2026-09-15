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

- 检查点、传送等命令依赖服务器插件；辅助绑定是否可用取决于游戏版本与服务器规则。部分服务器可能禁止使用相关 Bind 命令，请在使用前查阅并遵守对应服务器的规则。因违反服务器规则而导致的封禁，由使用者自行承担责任。部分 Bind 功能也可能在 Valve 更新游戏后失效，本项目不保证其能够长期稳定使用。

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

只需复制您所玩游戏的配置，无需下载整个仓库或解压文件。

1. 打开本项目中对应游戏的目录，分别打开下列两份 cfg 文件，复制文件中的全部内容。每份文件单独复制、单独保存，不要将两份内容合在一起。

   **CS:GO：**[csgo 目录](csgo/)中的 [csgokzgreen.cfg](csgo/csgokzgreen.cfg) 和 [csgokzbind.cfg](csgo/csgokzbind.cfg)。

   **CS2：**[cs2 目录](cs2/)中的 [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) 和 [cs2kzbind.cfg](cs2/cs2kzbind.cfg)。

2. 在 Steam 库中右键点击对应游戏，选择“管理 → 浏览本地文件”，进入下列目录。路径中的 `…` 表示您自己的安装位置，盘符和 Steam 库位置可能不同。

   **CS:GO：**右键点击 **Counter-Strike: Global Offensive**，打开的目录应为 `…\steam\steamapps\common\csgo legacy`。再进入 `csgo` → `cfg`，目标目录为 `…\steam\steamapps\common\csgo legacy\csgo\cfg`。

   **CS2：**右键点击 **Counter-Strike 2**，再进入 `game` → `csgo` → `cfg`，目标目录为 `…\steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg`。

3. 打开记事本，粘贴一份 cfg 的完整内容，选择“文件 → 另存为”。保存位置选择上一步的游戏 `cfg` 目录，文件名与项目中的文件名保持一致，例如 `cs2kzgreen.cfg`；**“保存类型”选择“所有文件”，编码选择 UTF-8，确保文件名不是 `cs2kzgreen.cfg.txt`。**用同样的方法保存另一份 cfg。如果已有同名文件，先备份再替换。

4. 打开游戏控制台，执行对应命令；两款游戏均使用 **P** 切换模式。

| 游戏 | 加载 Green | 加载 Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2kzgreen` | 先加载 Green，再按 P |

CS:GO 如需启动时自动加载 Green，打开本项目的 [autoexec.cfg](csgo/autoexec.cfg)，将内容复制到游戏同一 `cfg` 目录内的 `autoexec.cfg` 末尾。如果没有该文件，按上面的记事本方法创建。保留已有内容，并注意与原有配置的冲突；游戏已运行时，手动执行一次 `exec csgokzgreen` 即可加载新版。

CS2 无需 `autoexec.cfg`。两份配置需一起保存，首次加载请执行 `exec cs2kzgreen`，之后按 P 切换。


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

- Checkpoint and teleport commands require server plugins. Assist availability depends on the game version and server rules. Some servers may prohibit these binds; read and follow the rules of each server before using them. Users are solely responsible for bans resulting from violations of server rules. Some bind features may also stop working after Valve updates the game, and this project does not guarantee that they will remain functional or reliable over time.

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

Copy only the configs for the game you play. There is no need to download or extract the entire repository.

1. Open the relevant game folder in this project, then open each of the two cfg files below and copy its full contents. Copy and save each file separately; do not combine them.

   **CS:GO:** [csgokzgreen.cfg](csgo/csgokzgreen.cfg) and [csgokzbind.cfg](csgo/csgokzbind.cfg) in the [csgo folder](csgo/).

   **CS2:** [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) and [cs2kzbind.cfg](cs2/cs2kzbind.cfg) in the [cs2 folder](cs2/).

2. Right-click the relevant game in your Steam Library and select **Manage → Browse local files**, then navigate to the folder below. In these paths, `…` represents your installation location; the drive and Steam library location may vary.

   **CS:GO:** Right-click **Counter-Strike: Global Offensive**. The folder should be `…\steam\steamapps\common\csgo legacy`. Open `csgo` → `cfg`; the destination is `…\steam\steamapps\common\csgo legacy\csgo\cfg`.

   **CS2:** Right-click **Counter-Strike 2**, then open `game` → `csgo` → `cfg`. The destination is `…\steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg`.

3. Open Notepad, paste the full contents of one cfg, and choose **File → Save As**. Save it in the game's `cfg` folder from the previous step, using the exact filename from this project, such as `cs2kzgreen.cfg`. **Set “Save as type” to “All files” and encoding to UTF-8. Make sure the filename is not `cs2kzgreen.cfg.txt`.** Repeat for the other cfg. Back up any existing files with the same names before replacing them.

4. Open the game console and run the appropriate command below. Use **P** to switch modes in either game.

| Game | Load Green | Load Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2kzgreen` | Load Green first, then press P |

To load Green automatically when CS:GO starts, open this project's [autoexec.cfg](csgo/autoexec.cfg) and append its contents to `autoexec.cfg` in the same game `cfg` folder. If the file does not exist, create it using the Notepad steps above. Preserve existing content and check for conflicts with your own configs. If the game is already running, execute `exec csgokzgreen` once to load the update.

CS2 does not require `autoexec.cfg`. Save both configs, run `exec cs2kzgreen` for the initial load, then use P to switch modes.
