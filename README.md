# cskz-cfg

个人 CS:GO / CS2 KZ 配置，按 Green（原生移动）和 Bind（辅助绑定）区分。

Personal CS:GO / CS2 KZ configs, organized into Green (native movement) and Bind (assisted binds).

## 简介 / Overview

两款游戏统一使用 **Mouse4 加载 Green，Mouse5 加载 Bind**。Green 保留 KZ 常用功能键，移动使用原生命令；Bind 在此基础上提供可选辅助功能。

Both games use **Mouse4 for Green and Mouse5 for Bind**. Green combines native movement with KZ utility keys. Bind adds optional movement assists.

每次加载 Bind，**O / P / K 对应的可选功能默认关闭**，按键后开启。CS:GO 的动态 Null 保留原有逻辑，不受这些开关控制；CS2 不包含 Null 或 2tick。

Each Bind load resets its optional **O / P / K features to OFF**. CS:GO keeps its existing dynamic null-bind logic, independently of these toggles. CS2 includes neither null binds nor 2-tick binds.

## CS:GO Legacy

| 模式 / Mode | 文件 / File | 灵敏度 / Sensitivity |
| --- | --- | --- |
| Green | `csgo/csgogreen.cfg` | 2.7 |
| Bind | `csgo/csgobind.cfg` | 2.7 |

Green 使用原生移动绑定。Bind 自动加载 Green 的通用配置，再加入 WAD/SAD 兼容的动态 A/D Null 与以下开关。

Green uses native movement binds. Bind loads Green's shared settings first, then adds WAD/SAD-compatible dynamic A/D null binds and the toggles below.

| 按键 / Key | 功能 / Action | 加载 Bind 后 / On Bind load |
| --- | --- | --- |
| O | AD 节拍音 / A/D keypress sounds | 关闭 / OFF |
| P | 鼠标右键蹲跳并自动松 W / Mouse2 crouch-jump with automatic W release | 关闭 / OFF |
| K | 四步 2tick 滚轮绑定 / Four-step 2-tick wheel sequence | 关闭 / OFF |

- P 关闭时，鼠标右键恢复普通武器右键功能。  
  With P disabled, Mouse2 uses the normal secondary-attack command.
- K 开启后，按 E 重置序列，再向上滚动滚轮依次执行蹲、跳、松跳、松蹲；关闭后，滚轮向上恢复存点。  
  With K enabled, press E to reset the sequence, then scroll up through duck, jump, release jump, and release duck. Disabling K restores scroll-up checkpoints.
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

2. 将 `csgo/` 或 `cs2/` 文件夹**里面的两份 cfg**复制到对应游戏的 cfg 目录，保留文件名。  
   Copy **both cfg files inside** `csgo/` or `cs2/` into the corresponding game's cfg directory, keeping their filenames.

3. 打开游戏控制台，执行对应命令；之后即可使用 Mouse4 / Mouse5 切换。  
   Open the game console and run the appropriate command below. Mouse4 / Mouse5 will then switch modes.

| 游戏 / Game | 加载 Green / Load Green | 加载 Bind / Load Bind |
| --- | --- | --- |
| CS:GO Legacy | `exec csgogreen` | `exec csgobind` |
| CS2 | `exec cs2green` | `exec cs2bind` |

Bind 会调用同目录的 Green 文件，两份文件必须一起安装。

Bind loads the Green file from the same directory, so both files must be installed together.

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
| `csgokzgreen.cfg` | `csgo/csgogreen.cfg` |
| `csgokzbind.cfg` | `csgo/csgobind.cfg` |
| `cs2mg.cfg` | `cs2/cs2green.cfg` |
| `cs2kz.cfg` | `cs2/cs2bind.cfg` |
| `cs2-w.cfg` | 合并进 / Merged into `cs2/cs2bind.cfg` |

旧的 `csgokz.cfg` 兼容入口已移除。如使用启动项或其他 cfg 调用旧文件名，请改成上面的新命令。

The old `csgokz.cfg` compatibility entry has been removed. Update any launch options or other configs that reference old filenames.
