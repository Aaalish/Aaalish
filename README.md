pip install python-telegram-bot
from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext
# Вставьте ваш токен
TOKEN = '7196797680:AAFrtkwOHyh2SuPb_BsnWcaDW4J9CyZU3L4'
def start(update: Update, context: CallbackContext):
    update.message.reply_text('Привет! Я игровой бот. Введите /play, чтобы начать игру.')
def play(update: Update, context: CallbackContext):
    update.message.reply_text('Время играть! Напишите /help для получения помощи.')
def help_command(update: Update, context: CallbackContext):
    update.message.reply_text('Команды: /start, /play, /help')
def main():
    updater = Updater(TOKEN)
    dispatcher = updater.dispatcher
dispatcher.add_handler(CommandHandler('start', start))  dispatcher.add_handler(CommandHandler('play', play)) dispatcher.add_handler(CommandHandler('help', help_command))
    updater.start_polling()
   updater.idle()
if __name__ == '__main__':
    main()
