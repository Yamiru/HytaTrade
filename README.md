<p align="center">
  <img src="https://img.shields.io/badge/Hytale-Plugin-blue?style=for-the-badge" alt="Hytale Plugin">
  <img src="https://img.shields.io/badge/Version-1.0.0-green?style=for-the-badge" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/badge/Java-25-orange?style=for-the-badge" alt="Java 25">
</p>

# 🔄 HytaTrade

A lightweight, trading system for Hytale servers. Enable safe and secure item exchanges between players with dual confirmation, cooldowns, and comprehensive trade management.



## 🖼️ Preview Screenshot
![Screenshot](https://i.imgur.com/ihTCKYD.png)


## ✨ Features

- **Safe Trading** - Dual confirmation system ensures both parties agree before items are exchanged
- **Request System** - Send trade requests to other players with configurable timeout
- **Item Management** - Add items directly from your hand, remove items by index
- **Trade Overview** - View complete trade status showing both players' offered items
- **Cooldown System** - Prevent trade spam with configurable cooldown between trades
- **Distance Limit** - Optional maximum distance requirement for trading
- **Cancel Protection** - Items are safely returned if trade is cancelled

## 📦 Installation

1. upload plugin to server folder mods

2. restart server

# Trade Commands Guide

/trade <player> – Sent by the first player to request a trade.

/tradeaccept – Used by the second player to accept the trade request.

/tradeadd – Used by the first player to add the item currently held in hand to the trade.

/tradeconfirm – Used by the second player to confirm and complete the trade.

## 🎮 Commands

### Trading Commands

| Command | Alias | Description |
|---------|-------|-------------|
| `/trade <player>` | - | Send a trade request to another player |
| `/tradeaccept` | `/ta` | Accept an incoming trade request |
| `/tradedeny` | `/td` | Deny an incoming trade request |
| `/tradeadd` | `/tadd` | Add the item in your hand to the trade |
| `/traderemove <index>` | `/trem` | Remove an item from your trade offer by index |
| `/tradelist` | `/tlist` | Display current trade status and all offered items |
| `/tradeconfirm` | `/tok` | Confirm your side of the trade |
| `/tradecancel` | - | Cancel the current trade |
| `/tradehelp` | `/thelp` | Show help information |

### How Trading Works

1. **Initiate**: Player A uses `/trade PlayerB` to send a request
2. **Accept**: Player B uses `/tradeaccept` or `/ta` to accept
3. **Add Items**: Both players use `/tradeadd` while holding items
4. **Review**: Use `/tradelist` to see all offered items
5. **Confirm**: Both players use `/tradeconfirm` or `/tok`
6. **Complete**: Items are automatically exchanged when both confirm

## ⚙️ Configuration

The plugin creates a configuration file at `mods/Yamiru_HytaTrade/config.json`:

```json
{
  "TradeRequestTimeout": 60,
  "TradeCooldown": 10,
  "MaxTradeDistance": 50.0,
  "MaxItemsPerTrade": 27,
  "LogTrades": true
}
```

### Configuration Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `TradeRequestTimeout` | Integer | 60 | Seconds before a trade request expires |
| `TradeCooldown` | Integer | 10 | Seconds to wait between trades |
| `MaxTradeDistance` | Double | 50.0 | Maximum block distance for trading (0 = unlimited) |
| `MaxItemsPerTrade` | Integer | 27 | Maximum items each player can offer |
| `LogTrades` | Boolean | true | Log completed trades to console |

## 🔧 Requirements

- **Hytale Server** (latest version)
- **Java 25** or higher

## 🛡️ Safety Features

- **Dual Confirmation**: Both players must confirm before any items change hands
- **Confirmation Reset**: Adding or removing items resets both confirmations
- **Automatic Return**: Items are returned to owners if trade is cancelled
- **Thread Safety**: All inventory operations run on the world thread
- **Request Expiration**: Pending requests automatically expire after timeout


## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Yamiru**
- GitHub: [@yamiru](https://github.com/yamiru)
- Website: [yamiru.com](https://yamiru.com)


---

<p align="center">
  Made with ❤️ for the Hytale community
</p>
