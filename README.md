# Trading Sar Bot

A trading automation project for market signals, execution support, reporting, or strategy monitoring.

## Features

- Telegram bot command handling and operational notifications.

## Architecture

- **Repository:** `MilaArtyNew/trading-sar-bot`
- **Primary stack:** Python, Railway
- **Entrypoints and scripts:**
  - `bot.py`
- **Notable dependencies:** `aiohttp`, `python-dotenv`, `python-telegram-bot`

## Configuration

Configure the service with environment variables. Do not commit real secrets to the repository.

- `BINGX_API_KEY` — required or optional runtime configuration. See deployment environment for the actual value.
- `BINGX_SECRET_KEY` — required or optional runtime configuration. See deployment environment for the actual value.
- `DATA_DIR` — required or optional runtime configuration. See deployment environment for the actual value.
- `LEVERAGE` — required or optional runtime configuration. See deployment environment for the actual value.
- `MARGIN` — required or optional runtime configuration. See deployment environment for the actual value.
- `MAX_OPEN_POSITIONS` — required or optional runtime configuration. See deployment environment for the actual value.
- `MORNING_REPORT_CHAT_ID` — required or optional runtime configuration. See deployment environment for the actual value.
- `MORNING_REPORT_TOKEN` — required or optional runtime configuration. See deployment environment for the actual value.
- `PAPER_MODE` — required or optional runtime configuration. See deployment environment for the actual value.
- `SAR_PAPER_MODE` — required or optional runtime configuration. See deployment environment for the actual value.
- `SAR_SYMBOL` — required or optional runtime configuration. See deployment environment for the actual value.
- `TELEGRAM_CHAT_ID` — required or optional runtime configuration. See deployment environment for the actual value.
- `TELEGRAM_TOKEN` — required or optional runtime configuration. See deployment environment for the actual value.

## Setup

```bash
git clone https://github.com/MilaArtyNew/trading-sar-bot
cd trading-sar-bot
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Running Locally

```bash
python bot.py
```

## Bot Commands

- `/close_ema` — Project-specific command; see the bot implementation for exact behavior.
- `/close_ema_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/close_ema_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/close_sar` — Project-specific command; see the bot implementation for exact behavior.
- `/close_sar_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/close_sar_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/close_sar_sol` — Project-specific command; see the bot implementation for exact behavior.
- `/start_ema` — Project-specific command; see the bot implementation for exact behavior.
- `/start_ema_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/start_ema_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/start_sar` — Project-specific command; see the bot implementation for exact behavior.
- `/start_sar_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/start_sar_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/start_sar_sol` — Project-specific command; see the bot implementation for exact behavior.
- `/status` — Show current service or strategy status.
- `/stop_ema` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_ema_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_ema_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_sar` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_sar_btc` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_sar_eth` — Project-specific command; see the bot implementation for exact behavior.
- `/stop_sar_sol` — Project-specific command; see the bot implementation for exact behavior.
- `/trades` — Show trades.

If a command requires extra input and the argument is missing, the bot should ask a follow-up question instead of failing silently.

## Deployment Notes

- Keep secrets in the deployment platform environment variables, not in Git.
- Use the default branch as the source of truth for deployments.
- Check logs after every deployment and verify the `/status` or health endpoint when available.
- If the project uses a scheduler, verify timezone assumptions and idempotency before enabling it in production.

## Operational Notes

- Review logs after startup for missing environment variables or API authentication errors.
- Keep command names in English and document every user-facing command in this README.
- For Telegram bots, `/help` should list the same commands documented here.
- Inline buttons should edit the original message with the final status rather than sending duplicate messages.

## Troubleshooting

- **Bot does not respond:** verify the bot token, webhook/polling mode, and chat permissions.
- **Missing data:** check API keys, rate limits, and upstream service status.
- **Deployment starts but exits:** inspect platform logs for missing environment variables or import errors.
- **Commands differ from README:** update the command list here and in the bot command menu at the same time.

## Security

- Never commit `.env` files, API keys, private keys, Telegram tokens, or session strings.
- Use `.env.example` for placeholders only.
- Rotate any credential that was accidentally committed.
