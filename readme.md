# telegram bot
### This Python script creates a simple Telegram bot using the python-telegram-bot library. The bot can respond to basic commands, echo messages, and fetch real-time Bitcoin prices from an external API.

# installation
- venv:
- open trminal
- cmd
- creat vertual venv use `python -m venv .venv`
- active venv use `.venv\scripts\activate`
- install telegrambot use `python install telegrambot`
# import
- from telegram ForceReply, Update
- requests
- from telegram.ext Application, CommandHandler, ContextTypes, MessageHandler, filters

# The bot supports the following features :

1. /start Command : Greets the user using their Telegram name (with HTML formatting).
Example Response : Hi <b>@username</b>!


2. /help Command : Sends a basic help message.
Response: Help!


3. /price_btc Command : Uses the CoinGecko API to fetch the current Bitcoin price in USD.
Example Response: dollar: $31234


4. Text Message Echo :

The bot responds based on the exact message content:

If the user says "hi" → Responds : "hello"

If the user says "bye" → Responds : "bye"

For any other message → Repeats the same message back
# Defs:
- start :
```python
async def start(update: Update, context: ContextTypes.DEFAULT_TYPE)
```
Handles /start command and greets the user.

- help :
 ```python
 async def help_command(update: Update, context: ContextTypes.DEFAULT_TYPE)
 ```
Responds to /help with a simple message.

- echo :
```python
async def echo(update: Update, context: ContextTypes.DEFAULT_TYPE)
```
Responds to any text message based on its content.


- price_btc:
 ```python
 async def price_btc(update: Update, context: ContextTypes.DEFAULT_TYPE)
 ```
Fetches Bitcoin price from CoinGecko using requests.get()

- main :
 ```python
 def main()
 ```
Initializes the bot.
Adds all command/message handlers.
Starts the bot with run_polling().

# important
Set Your Bot Token

Replace:

```python
application = Application.builder().token("your token").build()
```

With your actual Telegram Bot Token from BotFather:

```python
application = Application.builder().token("YOUR_ACTUAL_BOT_TOKEN").build()
```
# Run the Bot

Save the script as bot.py and run it to the terminal :
python bot.py

# Interact via Telegram

Send /start, /help, /price_btc, or any text message to your bot.


