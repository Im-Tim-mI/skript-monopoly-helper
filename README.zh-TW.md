# 大富翁小幫手

[English](README.md) | **繁體中文**

在 Minecraft 棋盤上玩大富翁的指令工具：現金、擲骰、付租金、繳稅、通過起點與機會／命運卡，全部限定在指定的遊戲世界中使用。

> 本儲存庫包含同一個腳本的兩個版本：**繁體中文（zh-TW）** 是作者伺服器實際使用的原始版本；**English** 為完整英文翻譯版（指令、訊息與變數名稱皆為英文），功能相同。

## 功能特色

- 每位玩家獨立的現金，並可查看在場玩家的現金排行
- 擲兩顆骰子並向地圖內玩家公告，擲出雙重點數會提示
- 機會卡與命運卡各 12 張（獲得／支付／純提示），可自由修改
- 所得稅、奢侈稅、通過起點過路費與玩家間付款
- OP 工具：發放起始資金、銀行給錢／收錢／設定金額
- 只在指定世界（預設 `game_12`）內有效

## 需求

- [Paper](https://papermc.io/) 伺服器（開發環境 Paper 26.2 / Minecraft 26.2）
- [Skript](https://github.com/SkriptLang/Skript)（開發環境 2.16.2）

## 安裝

1. 先安裝[需求](#需求)中列出的插件。
2. 下載**其中一個**版本：

   | 版本 | 檔案 |
   |---|---|
   | 繁體中文（原始版本） | [`zh-TW/大富翁小幫手.sk`](zh-TW/%E5%A4%A7%E5%AF%8C%E7%BF%81%E5%B0%8F%E5%B9%AB%E6%89%8B.sk) |
   | English（英文） | [`en/monopoly-helper.sk`](en/monopoly-helper.sk) |

3. 把 `.sk` 檔案放進伺服器的 `plugins/Skript/scripts/`。
4. 執行 `/sk reload 大富翁小幫手`（請換成你放入的檔名），或重新啟動伺服器。

> [!IMPORTANT]
> **只能安裝其中一個版本。** 兩個版本是同一個腳本的不同語言，同時載入會互相衝突或重複執行。

## 指令

| 指令（中文版） | 英文版 | 說明 | 權限 |
|---|---|---|---|
| `/大富翁_骰子`<br>別名：`/骰子`、`/roll`、`/dice` | `/monopoly_roll`<br>別名：`/roll`、`/dice` | 擲兩顆骰子 | 所有人 |
| `/大富翁_現金 [玩家]`<br>別名：`/現金`、`/money`、`/balance`、`/cash`、`/錢` | `/monopoly_cash [player]`<br>別名：`/money`、`/balance`、`/cash` | 查看現金 | 所有人 |
| `/大富翁_排行榜`<br>別名：`/排行榜`、`/moneytop`、`/top`、`/排行` | `/monopoly_top`<br>別名：`/moneytop`、`/top` | 在場玩家現金排行 | 所有人 |
| `/大富翁_付錢 <玩家> <金額>`<br>別名：`/付錢`、`/pay` | `/monopoly_pay <player> <amount>`<br>別名：`/pay` | 付租金／過路費給玩家 | 所有人 |
| `/大富翁_通過起點`<br>別名：`/通過起點`、`/passgo`、`/起點` | `/monopoly_passgo`<br>別名：`/passgo` | 通過起點領過路費 | 所有人 |
| `/大富翁_繳稅 所得稅\|奢侈稅`<br>別名：`/繳稅`、`/tax` | `/monopoly_tax income\|luxury`<br>別名：`/tax` | 繳所得稅或奢侈稅 | 所有人 |
| `/大富翁_機會`<br>別名：`/機會`、`/chance` | `/monopoly_chance`<br>別名：`/chance` | 抽一張機會卡 | 所有人 |
| `/大富翁_命運`<br>別名：`/命運`、`/fate`、`/destiny` | `/monopoly_fate`<br>別名：`/fate`、`/destiny` | 抽一張命運卡 | 所有人 |
| `/大富翁_說明`<br>別名：`/說明`、`/dfwhelp`、`/大富翁` | `/monopoly_help`<br>別名：`/dfwhelp`、`/monopoly` | 顯示說明 | 所有人 |
| `/大富翁_開始遊戲 [金額]`<br>別名：`/開始遊戲`、`/dfwstart` | `/monopoly_start [amount]`<br>別名：`/dfwstart` | 發放起始資金給地圖內所有玩家 | OP |
| `/大富翁_銀行 給\|收\|設定 <玩家> <金額>`<br>別名：`/銀行`、`/bank` | `/monopoly_bank give\|take\|set <player> <amount>`<br>別名：`/bank` | 銀行操作 | OP |

## 設定

- 所有設定都在 `on load` 區塊：適用世界（`game_12`）、起始資金（15000）、通過起點過路費（2000）、所得稅（2000）、奢侈稅（1500）。
- 機會／命運卡的文字與金額也在同一區塊；`{dfw::chanceCount}` / `{dfw::fateCount}` 須等於卡片數量。
- 部分訊息寫有 `game_12`，若改用其他世界請一併修改。

## 注意事項

- `/pay`、`/money`、`/balance`、`/top`、`/bank` 等短別名可能與 EssentialsX 等經濟插件衝突，必要時可從 `aliases:` 移除；完整指令名稱永遠可用。
- 現金存放在 `{dfw::money::<uuid>}`，兩個版本共用相同變數。
- 中文指令需要較新的 Paper / Spigot；中文版另保留英文別名可備用。

## 相關專案

- [skript-monopoly-map-generator](https://github.com/Im-Tim-mI/skript-monopoly-map-generator)－大富翁地圖產生器
- [skript-player-menu-gui](https://github.com/Im-Tim-mI/skript-player-menu-gui)－玩家選單 GUI
- [skript-game-world-manager](https://github.com/Im-Tim-mI/skript-game-world-manager)－遊戲世界管理系統

## 授權

**MIT + Commons Clause**，完整條款請見 [LICENSE](LICENSE)。

- ✅ 可自由使用、複製、修改與分享本腳本。
- ✅ 本授權明確允許在收費或營利的 Minecraft 伺服器上安裝與運行本插件（含修改版）。
- ❌ 禁止的僅限於直接或間接販售本插件本體、修改版本，或以付費方式取得其檔案或原始碼。

Copyright (c) 2026 廷廷小教室、廷廷的家（Tim945）
