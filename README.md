# cskz-cfg

个人 CS:GO / CS2 KZ 配置，包含原生移动绑定与辅助绑定方案。
Personal CS:GO / CS2 KZ configs with native movement binds and assisted bind setups.

## 简介 / Overview

这套配置主要用于个人 KZ 跑图，通过鼠标侧键切换配置。

Green 使用原生移动绑定；Binder 使用 Null、自动松 W、2 tick 等辅助绑定。
两个游戏的具体实现不同，详见下方说明。

These configs are primarily for KZ, with mouse side buttons for switching setups.

Green uses native movement binds. Binder uses assists such as null binds,
automatic W release, and 2-tick binds. The implementation differs between games.

## CS:GO

适用于 CS:GO Legacy。
For CS:GO Legacy.

| 模式 / Mode | 文件 / File | 说明 / Description |
| --- | --- | --- |
| Green | `csgokzgreen.cfg` | 原生移动绑定 / Native movement binds |
| Binder | `csgokzbind.cfg` | Null、自动松 W、2 tick / Null binds, automatic W release, and 2-tick binds |

- **Mouse4**：加载 Green / Load Green.
- **Mouse5**：加载 Binder / Load Binder.
- `csgokz.cfg`：兼容旧入口，默认加载 Green / Compatibility entry that loads Green.

首次使用先在控制台执行 `exec csgokzgreen`，加载通用按键和模式切换入口。

For initial setup, run `exec csgokzgreen` in the console to load shared keybinds
and enable mode switching.

## CS2

| 配置 / Setup | 文件 / File | 说明 / Description |
| --- | --- | --- |
| Green | `cs2mg.cfg` | 原生移动绑定，也用于 MG / Native movement binds, also used for MG |
| KZ | `cs2kz.cfg` | KZ 按键与可选辅助功能 / KZ keybinds and optional assists |
| 自动松 W / Automatic W release | `cs2-w.cfg` | 由 KZ 配置调用 / Loaded by the KZ config |

CS2 当前没有单独的 Binder 主配置，辅助功能由 KZ 配置提供开关。

CS2 currently has no separate Binder preset. Optional assists are controlled
from the KZ config.

- **Mouse4**：加载 Green（`cs2mg.cfg`）/ Load Green.
- **Mouse5**：加载 KZ（`cs2kz.cfg`）/ Load KZ.
- **P**：在 KZ 配置中开关自动松 W，重新加载 KZ 后默认关闭。
  / Toggle automatic W release in KZ; it defaults to off when KZ is reloaded.
- **O**：在 KZ 配置中开关 AD 节拍音。
  / Toggle A/D movement sounds in KZ.

首次使用在控制台执行 `exec cs2kz`。

For initial setup, run `exec cs2kz` in the console.

## 使用说明 / Usage notes

- 将对应游戏文件夹内的 `.cfg` 文件放入该游戏的 cfg 目录，再执行上述加载命令。
  Copy the `.cfg` files inside the corresponding game folder into that game's
  cfg directory, then run the loading command above.
- 同一游戏的文件请放在一起，保留文件名，以便配置之间相互调用。
  Keep files for the same game together and preserve their names so references work.
- Green 指原生移动绑定，不代表所有按键均为游戏默认。
  Green refers to native movement binds, not a completely default keyboard layout.
- 检查点、传送等功能依赖服务器插件；辅助绑定的支持情况取决于游戏版本与服务器规则。
  Checkpoints and teleport commands require server plugins. Assist support depends
  on the game version and server rules.
- 配置包含个人灵敏度、键位及服务器偏好，使用前请按自己的习惯调整。
  These configs include personal sensitivity, keybinds, and server preferences.
  Adjust them to your needs.
