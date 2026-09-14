# cskz-cfg

个人 CS:GO / CS2 KZ 配置，按 Green（原生移动）和 Bind（辅助绑定）区分。

Personal CS:GO / CS2 KZ configs, organized into Green (native movement) and Bind (assisted binds).

## 简介 / Overview

CS:GO 使用 **P 切换 Green / Bind**，启动默认 Green；CS2 目前仍使用 **Mouse4 / Mouse5** 切换模式。

CS:GO uses **P to switch Green / Bind** and starts in Green. CS2 currently uses **Mouse4 / Mouse5** to switch modes.

CS:GO 已完成本轮基本功能实测；CS2 配置保留现状，待后续测试。

CS:GO has passed this round of basic in-game checks. CS2 configs remain unchanged, pending further testing.

## CS:GO Legacy

| 文件 / File | 用途 / Purpose |
| --- | --- |
| [csgokzgreen.cfg](csgo/csgokzgreen.cfg) | Green：原生移动 / Native movement |
| [csgokzbind.cfg](csgo/csgokzbind.cfg) | Bind：动态 Null、右键自动松 W 蹲跳与可选 2tick / Dynamic null binds, Mouse2 crouch-jump with automatic W release, and optional 2-tick binds |
| [autoexec.cfg](csgo/autoexec.cfg) | 启动默认加载 Green / Load Green on startup |

两种模式的灵敏度均为 **2.7**，各自独立加载所需设置，每次切换只显示最终模式的控制台说明。

Both modes use **2.7 sensitivity** and initialize their own settings. Each switch prints only the final mode's console guide.

| 按键 / Key | Green | Bind |
| --- | --- | --- |
| P | 切换到 Bind / Switch to Bind | 切换到 Green / Switch to Green |
| O | AD 节拍音开关，默认关闭 / Toggle A/D sounds, default OFF | AD 节拍音开关，默认关闭 / Toggle A/D sounds, default OFF |
| Mouse2 | 按住蹲伏 / Hold to duck | 蹲跳并自动松 W / Crouch-jump with automatic W release |
| K | 无绑定 / Unbound | 2tick 开关，默认关闭 / Toggle 2-tick binds, default OFF |
| E | 使用 / Use | 使用；2tick 开启时兼作序列重置 / Use; also reset the sequence when 2-tick binds are ON |
| 滚轮向上 / Wheel up | 存点 / Checkpoint | 2tick 关闭时存点，开启并按 E 后执行四步序列 / Checkpoint when OFF; four-step sequence after enabling and pressing E |
| 滚轮向下 / Wheel down | 普通跳跃 / Normal jump | 普通跳跃 / Normal jump |
| Mouse4 / Mouse5 | 无绑定 / Unbound | 无绑定 / Unbound |

- **P 只切换模式**，不单独开关自动松 W。进入 Bind 即启用右键辅助；返回 Green 后右键恢复普通蹲伏。  
  **P only switches modes.** The Mouse2 assist is active in Bind; returning to Green restores ordinary ducking.

- 两种模式均保留 G 夜视、N 穿墙、C 清贴花、X 喷涂、H HUD 切换；相关服务器命令需要插件支持。  
  Both modes retain G for night vision, N for noclip, C to clear decals, X to paint, and H to toggle the HUD. Server commands require plugin support.

- K 开启后，按 E 重置序列，再向上滚动依次执行蹲、跳、松跳、松蹲；四步完成后滚轮变为普通跳跃，下次按 E 重新准备。K 关闭后恢复存点。  
  Enable K, press E, then scroll up through duck, jump, release jump, and release duck. After four steps, the wheel performs normal jumps until E resets it. Disabling K restores checkpoints.

- Bind 加载时 A/D 先使用普通移动；首次松开 W 或 S 后启用 Null，按下 W/S 时临时使用普通 A/D。  
  Bind starts with ordinary A/D movement. Releasing W or S activates null binds; pressing W/S temporarily restores ordinary A/D.

## CS2

| 模式 / Mode | 文件 / File | 灵敏度 / Sensitivity |
| --- | --- | --- |
| Green | `cs2/cs2green.cfg` | 1.0 |
| Bind | `cs2/cs2bind.cfg` | 2.7 |

两种模式共用 KZ 检查点、传送、HUD 等功能及现有 Zerok 偏好。Bind 自动加载 Green，再应用自己的灵敏度和辅助开关。

Both modes share KZ checkpoint, teleport, HUD bindings, and the existing Zerok preferences. Bind loads Green first, then applies its own sensitivity and assist toggles.

| 按键 / Key | 功能 / Action | 加载 Bind 后 / On Bind load |
| --- | --- | --- |
| O | AD 节拍音 / A/D keypress sounds | 关闭 / OFF |
| P | 滚轮起跳自动松 W / Automatic W release on wheel takeoff | 关闭 / OFF |

自动松 W 已合并进 `cs2bind.cfg`，无需单独的 `cs2-w.cfg`。P 开启后，按 W 会为下一次向下滚轮起跳准备自动松 W；P 关闭后恢复普通 W 和向下滚轮跳跃。

Automatic W release is included in `cs2bind.cfg`; no separate `cs2-w.cfg` is required. With P enabled, pressing W arms the next downward wheel takeoff to release W. Disabling P restores normal W movement and scroll-down jumping.

## 安装与加载 / Installation and loading

1. 下载仓库：点击 **Code → Download ZIP**，解压。  
   Download the repository using **Code → Download ZIP**, then extract it.

2. CS:GO：将 `csgo/` 内的 `csgokzgreen.cfg` 和 `csgokzbind.cfg` 复制到实际运行的 CS:GO Legacy 的 `csgo/cfg/` 目录。CS2：将 `cs2/` 内两份 cfg 复制到对应游戏 cfg 目录。  
   For CS:GO, copy `csgokzgreen.cfg` and `csgokzbind.cfg` from `csgo/` into the `csgo/cfg/` directory of your active CS:GO Legacy installation. For CS2, copy both files from `cs2/` into its cfg directory.

3. 打开游戏控制台，执行下方命令；CS:GO 使用 P 切换，CS2 使用 Mouse4 / Mouse5 切换。  
   Run the appropriate command below in the game console. Switch CS:GO modes with P and CS2 modes with Mouse4 / Mouse5.

| 游戏 / Game | 加载 Green / Load Green | 加载 Bind / Load Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2green` | `exec cs2bind` |

CS:GO 若需启动默认 Green，将 `csgo/autoexec.cfg` 放入同一目录；如果已有 autoexec，只在原文件末尾添加 `exec csgokzgreen`，保留原有设置。游戏已运行时，手动执行一次 `exec csgokzgreen` 即可加载新版。

To start CS:GO in Green, place `csgo/autoexec.cfg` in the same directory. If you already have an autoexec, preserve it and append `exec csgokzgreen`. If the game is running, execute `exec csgokzgreen` once to load the update.

CS2 的 Bind 会调用同目录的 Green，两份文件需一起安装。

CS2 Bind loads Green from the same directory; install both files together.

## 使用说明 / Usage notes

- Green 指原生移动绑定，不代表全部键位均为游戏默认。  
  Green refers to native movement binds, not a completely default keyboard layout.

- O 的“节拍音”是在按下 A/D 时各播放一次提示音，不是固定 BPM 的循环节拍器。  
  O plays one sound per A/D keypress; it is not a looping fixed-BPM metronome.

- 加载模式会重设该模式的灵敏度，并关闭可选开关。切换后若移动中断，松开再按移动键。  
  Loading a mode reapplies its sensitivity and resets optional toggles. If movement stops during a switch, release and press the movement key again.

- 检查点、传送等命令依赖服务器插件；辅助绑定是否可用取决于游戏版本与服务器规则。  
  Checkpoint and teleport commands require server plugins. Assist availability depends on the game version and server rules.

- 配置包含个人灵敏度、键位及 Zerok 偏好，使用前请按自己的习惯调整。  
  These configs include personal sensitivity, keybinds, and Zerok preferences. Adjust them to your needs.

## 文件名变更 / Renamed files

| 旧文件 / Previous file | 新文件 / Current file |
| --- | --- |
| `csgogreen.cfg` | `csgo/csgokzgreen.cfg` |
| `csgobind.cfg` | `csgo/csgokzbind.cfg` |
| `cs2mg.cfg` | `cs2/cs2green.cfg` |
| `cs2kz.cfg` | `cs2/cs2bind.cfg` |
| `cs2-w.cfg` | 合并进 / Merged into `cs2/cs2bind.cfg` |

旧的 `csgokz.cfg` 兼容入口已移除。如使用启动项或其他 cfg 调用旧文件名，请改成上面的新命令。

The old `csgokz.cfg` compatibility entry has been removed. Update any launch options or other configs that reference old filenames.
