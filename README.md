# LickHunterPro Variable Pairs

On the LickHunterPro Discord a user named Sanduckchan created an overview on the Binance Futures liquidations. You can visit the site @ http://www.lickhunter.com/data/
The script fetches the pairs from the site and places them in the coins.json. The problem was with open orders. When the pairs got replaced you lost track of the open orders. That's why the script also checks your open orders on Binance Futures and combines those pairs with the pairs from the site.

# Features:
- Pairs based on **Top 10 burned by Volume - 24h**, **Top 10 by Liq-Events - 24h**, **Average Liq-Volume in USD - 24h** and **Average Liq-Amount - 24h**
- Set a maximum of traidingPairs
- Set a maximum of open orders, so you don't get too many open orders
- Open order isolation - When X percent of your wallet balance gets hit by open orders, only the open order pairs will be traded until the percentage drops below X

**This is an interim release to work with LickHunter Pro 1.76
This sets the same settings for all coins (you can change the values within the script), but that will be changed for the upcoming GUI version.
$longOffset = "2.7"
$shortOffset = "2.7"
$lickValue = "1000"
This release doesn't work for Bybit yet.**

# Prerequisites:
- PowerShell 5.1 - https://www.microsoft.com/en-us/download/details.aspx?id=54616
- You have to have a working LickHunterPro configuration, all settings in settings.json should be in place

# Installation:
- Place **Start-LickHunterPro-VarPairV1.xx.ps1** and **Stop-LickHunterPro.ps1** in the root of the LickHunterPro folder (Example: C:\LickHunterPro\).
- Edit **Start-LickHunter-Pro-VarPairV1.xx.ps1** with **NotePad++** or **Windows PowerShell ISE**
  - $botName = the name for your bot **Example: LHP001**
  - $longOffset = "2.7" **This applies to all coins for now - the soon to be published GUI will change that**
  - $shortOffset = "2.7" **This applies to all coins for now - the soon to be published GUI will change that**
  - $lickValue = "1000" **This applies to all coins for now - the soon to be published GUI will change that**
  - $maxPositions = "3" **The maximum orders you want to have open at the same time**
  - $maxPairs = "8" **The maximum pairs you want to trade, always the top of the chart is used**
  - $maxPositions = "3" **The maximum orders you want to have open at the same time**
  - $openOrderIsolationPercentage = "10" **Only trade open order pairs when X percentage of wallet balance is reached**
  - $tadingMode = **Choose a mode to base match your pairs. Modes: 1. $staticPairs 2. $whitelist 3. $tradingAge**
  - $staticPairs = **Trade only the pairs you want to trade**
  - $whitelist = **Set your personal whitelist of pairs you want to be able to trade**
  - $tradingAge = **All coins below trading age will not be traded**
  - $blacklist = **You can blacklist coins that are above your trading age, so they won't be traded**
  - $tradePairs = "1" **Choose 1, 2, 3 or 4, depending what chart your wan't to base your pairs on (1. Top 10 burned by Volume - 24h, 2. Top 10 by Liq-Events - 24h, 3. Average Liq-Volume in USD - 24h, 4. Average Liq-Amount - 24h)**
  - $fundingRateThreshold = **$true or $false, default is $false, set to $true if you don't want to trade pairs with a high Funding Rate**
  - $maxFundingRate = **For explanation about funding rate you can read this https://www.binance.com/en/support/faq/360033525031**  

- Save your changed settings
- Open Powershell and navigate to you LickHunterPro folder. From there run **Get-ChildItem | Unblock-File**
- Run **Start-LickHunterPro-VarPairV1.xx.ps1** from PowerShell

# Donate
- ETH: **0xA63Bca4aa47e42498889AB5185336FEa54835C7E**
- USDT/ERC20: **0xA63Bca4aa47e42498889AB5185336FEa54835C7E**
