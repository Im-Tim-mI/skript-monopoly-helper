# Monopoly Helper

**English** | [繁體中文](README.zh-TW.md)

Chat commands for playing Monopoly on a Minecraft board: cash balances, dice, rent payments, taxes, the GO salary and Chance / Fate cards - all limited to one game world.

> This repository has two editions of the same script: **繁體中文 (zh-TW)** is the original used on the author's Traditional Chinese server, and **English** is a full translation (commands, messages and variable names) with the same features.

## Features

- Per-player cash with a ranking of everyone on the map
- Two-dice rolls announced to the map, with a doubles notice
- 12 Chance and 12 Fate cards (receive / pay / message only) that are easy to edit
- Income and luxury taxes, GO salary and player-to-player payments
- OP tools: hand out starting cash, bank give / take / set
- Only works inside the configured world (`game_12` by default)

## Requirements

- [Paper](https://papermc.io/) server (developed on Paper 26.2 / Minecraft 26.2)
- [Skript](https://github.com/SkriptLang/Skript) (developed on 2.16.2)

## Installation

1. Install the plugins listed under [Requirements](#requirements).
2. Download **one** edition:

   | Edition | File(s) |
   |---|---|
   | English | [`en/monopoly-helper.sk`](en/monopoly-helper.sk) |
   | 繁體中文 (original) | [`zh-TW/大富翁小幫手.sk`](zh-TW/%E5%A4%A7%E5%AF%8C%E7%BF%81%E5%B0%8F%E5%B9%AB%E6%89%8B.sk) |

3. Copy the `.sk` file(s) into `plugins/Skript/scripts/` on your server.
4. Run `/sk reload monopoly-helper` (use the file name you copied) or restart the server.

> [!IMPORTANT]
> Install **only one** edition. Both editions are the same script in different languages - loading both makes them clash or run twice.

## Commands

| Command (English edition) | zh-TW edition | Description | Permission |
|---|---|---|---|
| `/monopoly_roll`<br>aliases: `/roll`, `/dice` | `/大富翁_骰子`<br>aliases: `/骰子`, `/roll`, `/dice` | Roll two dice | everyone |
| `/monopoly_cash [player]`<br>aliases: `/money`, `/balance`, `/cash` | `/大富翁_現金 [玩家]`<br>aliases: `/現金`, `/money`, `/balance`, `/cash`, `/錢` | Check cash | everyone |
| `/monopoly_top`<br>aliases: `/moneytop`, `/top` | `/大富翁_排行榜`<br>aliases: `/排行榜`, `/moneytop`, `/top`, `/排行` | Cash ranking of the players on the map | everyone |
| `/monopoly_pay <player> <amount>`<br>alias: `/pay` | `/大富翁_付錢 <玩家> <金額>`<br>aliases: `/付錢`, `/pay` | Pay rent / tolls to a player | everyone |
| `/monopoly_passgo`<br>alias: `/passgo` | `/大富翁_通過起點`<br>aliases: `/通過起點`, `/passgo`, `/起點` | Collect the GO salary | everyone |
| `/monopoly_tax income\|luxury`<br>alias: `/tax` | `/大富翁_繳稅 所得稅\|奢侈稅`<br>aliases: `/繳稅`, `/tax` | Pay the income or luxury tax | everyone |
| `/monopoly_chance`<br>alias: `/chance` | `/大富翁_機會`<br>aliases: `/機會`, `/chance` | Draw a Chance card | everyone |
| `/monopoly_fate`<br>aliases: `/fate`, `/destiny` | `/大富翁_命運`<br>aliases: `/命運`, `/fate`, `/destiny` | Draw a Fate card | everyone |
| `/monopoly_help`<br>aliases: `/dfwhelp`, `/monopoly` | `/大富翁_說明`<br>aliases: `/說明`, `/dfwhelp`, `/大富翁` | Show help | everyone |
| `/monopoly_start [amount]`<br>alias: `/dfwstart` | `/大富翁_開始遊戲 [金額]`<br>aliases: `/開始遊戲`, `/dfwstart` | Give starting cash to everyone on the map | OP |
| `/monopoly_bank give\|take\|set <player> <amount>`<br>alias: `/bank` | `/大富翁_銀行 給\|收\|設定 <玩家> <金額>`<br>aliases: `/銀行`, `/bank` | Bank actions | OP |

## Configuration

- All settings are in the `on load` block: world (`game_12`), starting cash (15000), GO salary (2000), income tax (2000) and luxury tax (1500).
- Edit the Chance / Fate texts and amounts there too; keep `{dfw::chanceCount}` / `{dfw::fateCount}` equal to the number of cards.
- Several messages mention `game_12` - update them if you use another world.

## Notes

- Short aliases such as `/pay`, `/money`, `/balance`, `/top` and `/bank` can clash with economy plugins like EssentialsX. Remove them from `aliases:` if needed; the full command names always work.
- Balances are stored in `{dfw::money::<uuid>}`, the same in both editions.
- Chinese command names need a recent Paper / Spigot; the zh-TW edition keeps English aliases as a fallback.

## Related projects

- [skript-monopoly-map-generator](https://github.com/Im-Tim-mI/skript-monopoly-map-generator) - Monopoly Map Generator
- [skript-player-menu-gui](https://github.com/Im-Tim-mI/skript-player-menu-gui) - Player Menu GUI
- [skript-game-world-manager](https://github.com/Im-Tim-mI/skript-game-world-manager) - Game World Manager

## License

**MIT + Commons Clause** - see [LICENSE](LICENSE) for the full text.

- ✅ You may use, copy, modify and share this script.
- ✅ You **may** install and run it - including modified versions - on Minecraft servers that charge money or are run for profit.
- ❌ You may **not** sell the script itself or modified versions of it, directly or indirectly, or require payment to obtain its files or source code.

Copyright (c) 2026 廷廷小教室、廷廷的家（Tim945）
