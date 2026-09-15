# cskz-cfg

个人 CS:GO / CS2 KZ 配置，按 Green（原生移动）和 Bind（辅助绑定）区分。

Personal CS:GO / CS2 KZ configs, organized into Green (native movement) and Bind (assisted binds).

## 简介 / Overview

CS:GO 与 CS2 均使用 **P 切换 Green / Bind**。CS:GO 的启动入口默认加载 Green；CS2 首次使用先执行 `exec cs2kzgreen`。

Both games use **P to switch Green / Bind**. The CS:GO startup entry loads Green; for CS2, run `exec cs2kzgreen` first.

CS:GO 与 CS2 已完成本轮基本功能实测。

CS:GO and CS2 have passed this round of basic in-game checks.

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
| Green | [cs2kzgreen.cfg](cs2/cs2kzgreen.cfg) | 2.70000000 |
| Bind | [cs2kzbind.cfg](cs2/cs2kzbind.cfg) | 沿用 Green / Inherited from Green |

Green 管理原生移动、通用按键、mhud 和个人偏好。Bind 只覆盖自动松 W 所需的 W、滚轮向下及 P 返回入口，不重复加载通用设置。

Green manages native movement, shared keybinds, mhud, and personal preferences. Bind only overrides W, scroll-down, and the P return binding for automatic W release; it does not reload shared settings.

首次使用先执行 `exec cs2kzgreen`。松开移动、跳跃和蹲伏键后按 P 进入 Bind，再按 P 重新加载 Green 并关闭辅助。

Run `exec cs2kzgreen` first. Release movement, jump, and duck keys before pressing P to enter Bind. Press P again to reload Green and disable the assist.

| 按键 / Key | 功能 / Action |
| --- | --- |
| P | Green / Bind 模式切换 / Switch Green / Bind |
| O | AD 节拍音开关 / Toggle A/D keypress sounds |
| G | `sw_nv` 夜视开关，依赖服务器插件 / Toggle night vision; requires the server plugin |
| L | Gamma 1.0 / 1.8 / 2.2 / 2.6 循环切换 / Cycle gamma values |
| Mouse2 | 按住蹲伏 / Hold to duck |
| J | `kz_jsalways`，直接执行控制台命令 / Execute the console command directly |
| Z | 按住使用 Zed meme 语音键位，松开恢复 KZ 数字键 / Hold for Zed meme voice keys; release to restore KZ number keys |

加载 Green 时 O 默认关闭；进入 Bind 时保持当前节拍音状态。Bind 中按 W 会为下一次向下滚轮起跳准备自动松 W。

Loading Green resets A/D sounds to OFF; entering Bind preserves their current state. In Bind, pressing W arms the next downward wheel takeoff to release W.

E 不打开购买菜单，Mouse3 保留玩家标记。配置不管理 F5/F6/F7/8 和 Mouse4/Mouse5，也不配置 `sw_nvs`。

E does not open the buy menu, and Mouse3 retains player ping. These configs do not manage F5/F6/F7/8 or Mouse4/Mouse5, and do not configure `sw_nvs`.

## 安装与加载 / Installation and loading

1. 下载仓库：点击 **Code → Download ZIP**，解压。  
   Download the repository using **Code → Download ZIP**, then extract it.

2. CS:GO：将 `csgo/` 内的 `csgokzgreen.cfg` 和 `csgokzbind.cfg` 复制到实际运行的 CS:GO Legacy 的 `csgo/cfg/` 目录。CS2：将 `cs2/` 内两份 cfg 复制到对应游戏 cfg 目录。  
   For CS:GO, copy `csgokzgreen.cfg` and `csgokzbind.cfg` from `csgo/` into the `csgo/cfg/` directory of your active CS:GO Legacy installation. For CS2, copy both files from `cs2/` into its cfg directory.

3. 打开游戏控制台，执行下方命令；两款游戏均使用 P 切换。  
   Run the appropriate command below in the game console. Switch modes in either game with P.

| 游戏 / Game | 加载 Green / Load Green | 加载 Bind / Load Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgokzgreen` | `exec csgokzbind` |
| CS2 | `exec cs2kzgreen` | 先加载 Green，再按 P / Load Green first, then press P |

CS:GO 若需启动默认 Green，将 `csgo/autoexec.cfg` 放入同一目录；如果已有 autoexec，只在原文件末尾添加 `exec csgokzgreen`，保留原有设置。游戏已运行时，手动执行一次 `exec csgokzgreen` 即可加载新版。

To start CS:GO in Green, place `csgo/autoexec.cfg` in the same directory. If you already have an autoexec, preserve it and append `exec csgokzgreen`. If the game is running, execute `exec csgokzgreen` once to load the update.

CS2 的两份文件需一起安装；Bind 不会自动调用 Green，首次加载请使用 Green 入口。

Install both CS2 files together. Bind does not automatically load Green; use the Green entry for initial setup.

## 使用说明 / Usage notes

- Green 指原生移动绑定，不代表全部键位均为游戏默认。  
  Green refers to native movement binds, not a completely default keyboard layout.

- O 的“节拍音”是在按下 A/D 时各播放一次提示音，不是固定 BPM 的循环节拍器。  
  O plays one sound per A/D keypress; it is not a looping fixed-BPM metronome.

- CS:GO 加载模式会重设灵敏度和可选开关；CS2 仅加载 Green 时重设灵敏度并关闭节拍音。切换后若移动中断，松开再按移动键。  
  CS:GO mode loads reset sensitivity and optional toggles; CS2 only resets sensitivity and A/D sounds when loading Green. If movement stops during a switch, release and press the movement key again.

- 检查点、传送等命令依赖服务器插件；辅助绑定是否可用取决于游戏版本与服务器规则。  
  Checkpoint and teleport commands require server plugins. Assist availability depends on the game version and server rules.

- 配置包含个人灵敏度、键位及 Zerok 偏好，使用前请按自己的习惯调整。  
  These configs include personal sensitivity, keybinds, and Zerok preferences. Adjust them to your needs.

## 文件名变更 / Renamed files

| 旧文件 / Previous file | 新文件 / Current file |
| --- | --- |
| `csgogreen.cfg` | `csgo/csgokzgreen.cfg` |
| `csgobind.cfg` | `csgo/csgokzbind.cfg` |
| `cs2mg.cfg` | `cs2/cs2kzgreen.cfg` |
| `cs2green.cfg` | `cs2/cs2kzgreen.cfg` |
| `cs2bind.cfg` | `cs2/cs2kzbind.cfg` |
| `cs2kz.cfg` | `cs2/cs2kzbind.cfg` |
| `cs2-w.cfg` | 合并进 / Merged into `cs2/cs2kzbind.cfg` |

旧的 `csgokz.cfg` 兼容入口已移除。如使用启动项或其他 cfg 调用旧文件名，请改成上面的新命令。

The old `csgokz.cfg` compatibility entry has been removed. Update any launch options or other configs that reference old filenames.
