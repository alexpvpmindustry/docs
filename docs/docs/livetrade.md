---
title: 'Live Trading'
---

# Live Trade

The "live-trade" plugin is available for early access which enables live/paper trading with Jesse. You can read the [announcement article](https://jesse.trade/blog/news/the-live-trade-plugin-is-open-for-early-access) or head over to our website, [register](https://jesse.trade/register) and get your license, and then head over to the [installation guide](/docs/livetrade.html#installation). 

**Update:** We are at the finishing days of the early-access phase. All the promised items are now available and the strategy API is pretty stable by now. I will release version `1.0.0` soon.


::: warning
Before going live make sure the execution time of your strategy doesn't exceed your timeframe. For example, if you want to trade the 5min timeframe the execution of all your code for one new candle should be finished in under 5min.
:::

## Paper Trading

Paper trading is possible with Jesse and is a good way to test-drive a strategy without risking real money. 

You can enable paper trading by turning on the "Paper Trade" option on the "Live" page of the dashboard. 

## Supported Exchanges

At the moment these are the supported exchanges for live trading:

- [Bybit USDT Perpetual Futures](https://jesse.trade/bybit)
- [FTX Perpetual Futures](https://ftx.com/trade/BTC-PERP)
- [FTX Spot](https://ftx.com/trade/BTC/USD)
- [FTX US Spot](https://ftx.us/trade/BTC/USD)
- [Binance Perpetual Futures](https://www.binance.com/en/futures/BTCUSDT)
- [Binance Spot](https://www.binance.com/en/trade/BTC_USDT?theme=dark&type=spot)
- [Binance US Spot](https://www.binance.us)

New exchange drivers are developed based on demand. So if you need an exchange that is not supported, please reach out and let me know. 

## Installation
The package is pre-built and the access is limited to those with an active license. We made sure the installation is easy and made it automated as much as possible.

::: tip 🎥 Video Tutorial
In case you prefer watching a video, here's a [short screencast of installing the plugin on remote server for live trading](https://www.youtube.com/watch?v=cUNX5FAVVYo).
:::

### 1. Creating a license key
First, you need to create a license access key. Assuming you are already logged in to your Jesse.Trade account, go into the [API Tokens](https://jesse.trade/user/api-tokens) page and generate a new token. The name of it doesn't matter. Then copy the token and paste it into the `LICENSE_API_TOKEN` variable inside your project's `.env` file.

Now, assuming whether you are using Jesse with the Docker setup, or you installed the environment natively, **you have to choose your second step**:

### 2. Docker environment
If you are using Jesse using our [first-class Docker setup](./getting-started/docker.html), **you don't have to do anything**! 

Jesse will pick up on the change you just made in your `.env` file, download and install the correct version of the plugin for you. 

### 2. Native environment setups
All you have to do is to run a single command which will automatically download the correct version of the package according to your machine's CPU architecture, OS, Python version, and Jesse version:
```sh
jesse install-live
```

## Update

To update to the latest versions, usually you have to update Jesse itself first, and then the plugin. Here's the [guide](/docs/getting-started/update.html).
