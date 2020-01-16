## Exchange marketplaces supported

- [X] [Bittrex](https://bittrex.com/)
- [X] [Binance](https://www.binance.com/) ([*Note for binance users](#a-note-on-binance))

## Features

- [x] **Based on Python 3.6+**: For botting on any operating system - Windows, macOS and Linux.
- [x] **Persistence**: Persistence is achieved through sqlite.
- [x] **Dry-run**: Run the bot without playing money.
- [x] **Backtesting**: Run a simulation of your buy/sell strategy.
- [x] **Strategy Optimization by machine learning**: Use machine learning to optimize your buy/sell strategy parameters with real exchange data.
- [x] **Edge position sizing** Calculate your win rate, risk reward ratio, the best stoploss and adjust your position size before taking a position for each specific market. [Learn more](https://www.freqtrade.io/en/latest/edge/).
- [x] **Whitelist crypto-currencies**: Select which crypto-currency you want to trade or use dynamic whitelists.
- [x] **Blacklist crypto-currencies**: Select which crypto-currency you want to avoid.
- [x] **Manageable via Telegram**: Manage the bot with Telegram.
- [x] **Display profit/loss in fiat**: Display your profit/loss in 33 fiat.
- [x] **Daily summary of profit/loss**: Provide a daily summary of your profit/loss.
- [x] **Performance status report**: Provide a performance status of your current trades.

## Quick start

Freqtrade provides a Linux/macOS script to install all dependencies and help you to configure the bot.

```bash
git clone git@github.com:freqtrade/freqtrade.git
cd freqtrade
git checkout develop
./setup.sh --install
```

## Basic Usage

### Bot commands

```
usage: freqtrade [-h] [-v] [--logfile FILE] [--version] [-c PATH] [-d PATH]
                 [-s NAME] [--strategy-path PATH] [--dynamic-whitelist [INT]]
                 [--db-url PATH] [--sd-notify]
                 {backtesting,edge,hyperopt} ...

Free, open source crypto trading bot

positional arguments:
  {backtesting,edge,hyperopt}
    backtesting         Backtesting module.
    edge                Edge module.
    hyperopt            Hyperopt module.

optional arguments:
  -h, --help            show this help message and exit
  -v, --verbose         Verbose mode (-vv for more, -vvv to get all messages).
  --logfile FILE        Log to the file specified
  --version             show program's version number and exit
  -c PATH, --config PATH
                        Specify configuration file (default: None). Multiple
                        --config options may be used.
  -d PATH, --datadir PATH
                        Path to backtest data.
  -s NAME, --strategy NAME
                        Specify strategy class name (default:
                        DefaultStrategy).
  --strategy-path PATH  Specify additional strategy lookup path.
  --dynamic-whitelist [INT]
                        Dynamically generate and update whitelist based on 24h
                        BaseVolume (default: 20). DEPRECATED.
  --db-url PATH         Override trades database URL, this is useful if
                        dry_run is enabled or in custom deployments (default:
                        None).
  --sd-notify           Notify systemd service manager.
```

### Telegram RPC commands

- `/start`: Starts the trader
- `/stop`: Stops the trader
- `/status [table]`: Lists all open trades
- `/count`: Displays number of open trades
- `/profit`: Lists cumulative profit from all finished trades
- `/forcesell <trade_id>|all`: Instantly sells the given trade (Ignoring `minimum_roi`).
- `/performance`: Show performance of each finished trade grouped by pair
- `/balance`: Show account balance per currency
- `/daily <n>`: Shows profit or loss per day, over the last n days
- `/help`: Show help message
- `/version`: Show version

## Requirements

### Uptodate clock

The clock must be accurate, syncronized to a NTP server very frequently to avoid problems with communication to the exchanges.

### Min hardware required

To run this bot a cloud instance with a minimum of:

- Minimal (advised) system requirements: 2GB RAM, 1GB disk space, 2vCPU

is recommended.

### Software requirements

- [Python 3.6.x](http://docs.python-guide.org/en/latest/starting/installation/)
- [pip](https://pip.pypa.io/en/stable/installing/)
- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [TA-Lib](https://mrjbq7.github.io/ta-lib/install.html)
- [virtualenv](https://virtualenv.pypa.io/en/stable/installation/) (Recommended)
- [Docker](https://www.docker.com/products/docker) (Recommended)
