# *****************************************************************************************************
#  Guessing a number game.
# *****************************************************************************************************

# import random
# print('You have three chances. Guess the number within three attempts.')
# for i in range(1,4):
#     print('attempt:- ',i)
#     guess_number = int(input('Enter your guess for a number from 1 to 10.:- '))
#     print('Your guessed number is :- ', guess_number)
#     random_number = random.randint(1, 10)
#     print('The number is :- ',random_number)
#     if random_number == guess_number:
#         print('Oh, great,you guessed the correct number.')
#     else:
#         print('Great attempt. Try again!.')
# print('All attempts were completed. Play agian!. Thank you for playing. See you again.')

# *****************************************************************************************************
#   Dice Simulation
# *****************************************************************************************************
# import random
# print('Hello player! welcome to the dice simulator game.')
# dices_count = int(input('Enter the number of dice you are rolling only in numbers words are not allowed:- '))
# # elif not type(dices_count) is int:
# #     raise TypeError("Only integers are allowed") -- Not working
# if dices_count < 1:
#     print('Invalid count.Please Play again!')
# random_output = []
# for i in range(1,dices_count + 1):
#     random_output.append(random.randint(1, dices_count))
# print('The dice values are' ,random_output)

# *****************************************************************************************************
#   Hangman game
# *****************************************************************************************************

# import random
# import time
# name = input('enter your name:- ')
# print('Hello!',name,', Welcome to Hangman game. Start guessing the word. All the best ', name)
# print('Can you guess the Apple products. word has all lower case letters')
# l = ['iphone','macbook','watch','ipad']
# word = random.choice(l)
# time.sleep(1)
# print("start guessing......")
# time.sleep(0.5)
# guesses = ''
# attempts = 5
# while attempts > 0:
#     fail = 0
#     for i in word:
#         if i in guesses:
#             print(i,end="")
#         else:
#             print("_",end="")
#             fail += 1
#     if fail == 0:
#         print(' Hey '+ name + ' congrats you won the game')
#         break
#     guess = input("guess a character in the word of apple product")
#     guesses += guess
#     if guess not in word:
#         attempts -= 1
#         print('oh,',guess, 'is not in the word')
#         print(name,',You have ',attempts,'more guesses')
#         if attempts == 0:
#             print(name, " , You tried your best but failed to guess the word. Try again!")

# *****************************************************************************************************
#  rock scissor papers
# *****************************************************************************************************
# import random
# import sys
# class RPS:
#     def __init__(self):
#         print('welcome to 9000!')
#         self.moves: dict = {'rock':'🪨','paper': '📄','scissor':'✂️'}
#         self.valid_moves : list[str] = list(self.moves.keys())
#     def play_game(self):
#         user_move : str =  input('rock, paper ,or scissors?').lower()
#         if user_move == 'exit':
#             sys.exit()
#         if user_move not in self.valid_moves:
#             print('Invalid moves......')
#             return self.play_game()
#         ai_move : str = random.choice(self.valid_moves)
#         self.display_moves(user_move, ai_move)
#         self.check_move(user_move, ai_move)
#     def display_moves(self,user_move: str, ai_move : str):
#         print('-------')
#         print(f'you:{self.moves[user_move]}')
#         print(f'you:{self.moves[ai_move]}')
#         print('-------')
#     def check_move(self,user_move: str, ai_move : str):
#         if user_move == ai_move:
#             print('It\'s a tie!')
#         elif user_move == 'rock' and ai_move == 'scissors':
#             print('you win!')
#         elif user_move == 'scissors' and ai_move == 'paper':
#             print('you win!')
#         elif user_move == 'paper' and ai_move == 'rock':
#             print('you win!')
#         else:
#             print('Ai wins')
# if __name__ == '__main__':
#     rps = RPS()
#     while True:
#         rps.play_game()

# *****************************************************************************************************
#  Password generator
# *****************************************************************************************************

# import random
# import string
# upperlist = list(string.ascii_lowercase)
# lowerlist = list(string.ascii_uppercase)
# digitlist = list(string.digits)
# speciallist = list(string.punctuation)
# fl = random.choice(upperlist)
# sl = random.choice(lowerlist)
# tl = random.choice(digitlist)
# fol = random.choice(speciallist)
# fil = random.choice(upperlist)
# sil = random.choice(lowerlist)
# sel = random.choice(digitlist)
# eil = random.choice(speciallist)
# pwdlist = [fl,sl,tl,fol,fil,sil,sel,eil]
# random.shuffle(pwdlist)
# password = ''.join(pwdlist)
# print(password)

# *****************************************************************************************************
#  QR code generator
# *****************************************************************************************************

# # import modules
# import qrcode
# from PIL import Image
# # taking image which user wants
# # in the QR code center
# Logo_link = '/Users/cskraju/Downloads/Collage-of-Python-built-in-functions-code-snippets-icons-and-Python-logo.jpg'
# logo = Image.open(Logo_link)
# # taking base width
# basewidth = 100
# # adjust image size
# wpercent = (basewidth/float(logo.size[0]))
# hsize = int((float(logo.size[1])*float(wpercent)))
# logo = logo.resize((basewidth, hsize))
# QRcode = qrcode.QRCode(
# 	error_correction=qrcode.constants.ERROR_CORRECT_H
# )
# # taking url or text
# url = 'https://www.linkedin.com/in/chiluru-santhosh-kumar-raju-61ba1421a/'
# # adding URL or text to QRcode
# QRcode.add_data(url)
# # generating QR code
# QRcode.make()
# # taking color name from user
# QRcolor = 'Green'
# # adding color to QR code
# QRimg = QRcode.make_image(
# 	fill_color=QRcolor, back_color=(45,45,48)).convert('RGB')
# # set size of QR code
# pos = ((QRimg.size[0] - logo.size[0]) // 2,
# 	(QRimg.size[1] - logo.size[1]) // 2)
# QRimg.paste(logo, pos)
# # save the QR code generated
# QRimg.save('gfg_QR.png')
# print('QR code generated!')

# *****************************************************************************************************
#  website checker
# *****************************************************************************************************

# import csv
# import requests
# from http import HTTPStatus
# from fake_useragent import UserAgent
#
#
# def get_websites(csv_path: str) -> list[str]:
#     """Loads websites from a csv file"""
#
#     websites: list[str] = []
#     with open(csv_path, 'r') as file:
#         reader = csv.reader(file)
#         for row in reader:
#             if 'https://' not in row[1]:
#                 websites.append(f'https://{row[1]}')
#             else:
#                 websites.append(row[1])
#
#     return websites
#
#
# def get_user_agent() -> str:
#     """Returns a user agent that can be used with requests"""
#
#     ua = UserAgent()
#     return ua.chrome
#
#
# def get_status_description(status_code: int) -> str:
#     """Uses the status code to return a readable description"""
#
#     for value in HTTPStatus:
#         if value == status_code:
#             description: str = f'({value} {value.name}) {value.description}'
#             return description
#
#     return '(???) Unknown status code...'
#
#
# def check_website(website: str, user_agent: str):
#     """Gets that status code for a website and prints the result"""
#     try:
#         code: int = requests.get(website, headers={'User-Agent': user_agent}).status_code
#         print(website, get_status_description(code))
#     except Exception:
#         print(f'**Could not get information for website: "{website}"')
#
#
# def main():
#     sites: list[str] = get_websites('/Users/cskraju/Downloads/websites-2.csv')
#     user_agent: str = get_user_agent()
#
#     # Check websites
#     for i, site in enumerate(sites):
#         check_website(site, user_agent)
#
#
# if __name__ == '__main__':
#     main()

# *****************************************************************************************************
#  common password checker
# *****************************************************************************************************

# def check_pwd(password: str):
#     with open('/Users/cskraju/Downloads/10-million-password-list-top-100.txt','r') as file:
#         common_pwds : list[str] = file.read().splitlines()
#     for i, common_pwds in enumerate(common_pwds, start = 1):
#         if password == common_pwds:
#             print(f'{password} : ❌ (#{i})')
#             return
#     print(f'{password} : ✅ (Unique)')
# def main():
#     user_pwd : str =  input('enter your password')
#     check_pwd(user_pwd)
# if __name__ == '__main__':
#     main()
# ---------------------**********************-----------------
# import string
# def password_strength_checker(pwd):
#     upperlist = list(string.ascii_lowercase)
#     lowerlist = list(string.ascii_uppercase)
#     digitlist = list(string.digits)
#     speciallist = list(string.punctuation)
#     ul = []
#     ll = []
#     dl = []
#     sl = []
#     for i in lowerlist:
#         if i in pwd:
#             ll.append('true')
#     for j in upperlist:
#         if j in pwd:
#             ul.append('true')
#     for k in digitlist:
#         if k in pwd:
#             dl.append('true')
#     for l in speciallist:
#         if l in pwd:
#             sl.append('true')
#     lul = set(ul)
#     lll = set(ll)
#     ldl = set(dl)
#     lsl = set(sl)
#     if len(pwd) > 7 and (len(lul) == len(lll) == len(ldl) == len(lsl) == 1):
#         print(f'{pwd} is a strong password ✅')
#     else:
#         print(f'{pwd} is a weak password ❌. Please enter a strong password')
# pwd  = input('enter your password:-- \n')
# password_strength_checker(pwd)

# *****************************************************************************************************
# image download from url
# *****************************************************************************************************
#
# import os
# import requests
# def img_extensions(img_url: str) -> str | None:
#     extensions : list[str] = ['.png','.jpeg','.jpg','.gif','.svg']
#     for e in extensions:
#         if e in img_url:
#             return e
# def img_download(img_url : str,name: str,folder : str = None ):
#     if e:=img_extensions(img_url):
#         if folder:
#             img_name: str = f'{folder}/{name}{e}'
#         else:
#             img_name : str = f'{name}{e}'
#     else:
#         raise Exception('Image extension could not be located')
#     if os.path.isfile(img_name):
#         raise Exception('File name already exists......')
#     try:
#         img_content : bytes = requests.get(img_url).content
#         with open(img_name, 'wb') as handler:
#             handler.write(img_content)
#             print(f'Downloaded : {img_name} successfully')
#     except Exception as ex:
#         print(f'Error: {ex}')
# if __name__ == '__main__':
#     input_url: str = input('Enter a url: ')
#     input_name : str = input('Enter a name for image: ')
#     print('Downloading...')
#     img_download(input_url,input_name,folder = '/Users/cskraju/pythonProject/openpyxl/Linesfile and attriubutes file./Python projects udemy/Images')

# *****************************************************************************************************
# GUI tax calculator
# *****************************************************************************************************
#
# import customtkinter as ctk
# class TaxCalculator:
#     def __init__(self):
#         # Initialize our window
#         self.window = ctk.CTk()
#         self.window.title('Tax Calculator')
#         self.window.geometry('350x230')
#         self.window.resizable(True, True)
#         # Widget padding
#         self.padding: dict = {'padx': 20, 'pady': 15}
#         # Income label and entry
#         self.income_label = ctk.CTkLabel(self.window, text='Enter Income:')
#         self.income_label.grid(row=0, column=0, **self.padding)
#         self.income_entry = ctk.CTkEntry(self.window)
#         self.income_entry.grid(row=0, column=1, **self.padding)
#         # Tax label and entry
#         self.tax_rate_label = ctk.CTkLabel(self.window, text='Enter tax Percent:')
#         self.tax_rate_label.grid(row=1, column=0, **self.padding)
#         self.tax_rate_entry = ctk.CTkEntry(self.window)
#         self.tax_rate_entry.grid(row=1, column=1, **self.padding)
#         #  Result label and entry
#         self.result_label = ctk.CTkLabel(self.window, text='Tax amount :')
#         self.result_label.grid(row=2, column=0, **self.padding)
#         self.result_entry = ctk.CTkEntry(self.window)
#         self.result_entry.insert(0, '0')
#         self.result_entry.grid(row=2, column=1, **self.padding)
#         # Calculate button
#         self.calculate_button = ctk.CTkButton(self.window, text='Click to Calculate', command=self.calculate_tax)
#         self.calculate_button.grid(row=3, column=0, **self.padding)
#     def update_result(self, text: str):
#         """Updates the result of the tax field."""
#
#         self.result_entry.delete(0, ctk.END)
#         self.result_entry.insert(0, text)
#     def calculate_tax(self):
#         """Calculates the total tax based on the percent."""
#         try:
#             income: float = float(self.income_entry.get())
#             tax_rate: float = float(self.tax_rate_entry.get())
#             self.update_result(f'₹ {income * (tax_rate / 100):,.2f}')
#         except ValueError:
#             self.update_result('Invalid input')
#     def run(self):
#         """Runs the tkinter app."""
#         self.window.mainloop()
# if __name__ == '__main__':
#     tc = TaxCalculator()
#     tc.run()

# import tkinter as tk
#
# class CalculatorApp:
#     def __init__(self, master):
#         self.master = master
#         self.master.title("Calculator")
#
#         # Entry widget to display the input and result
#         self.entry = tk.Entry(master, width=20, font=('Arial', 14), bd=5, insertwidth=4, justify='right')
#         self.entry.grid(row=0, column=0, columnspan=4)
#
#         # Buttons for digits and arithmetic operations
#         buttons = [
#             '7', '8', '9', '/',
#             '4', '5', '6', '*',
#             '1', '2', '3', '-',
#             '0', '.', '=', '+'
#         ]
#
#         # Dictionary to store the operator and the corresponding function
#         self.operators = {'/': self.divide, '*': self.multiply, '-': self.subtract, '+': self.add}
#
#         # Create and place the buttons
#         row_val = 1
#         col_val = 0
#         for button_text in buttons:
#             tk.Button(master, text=button_text, width=5, height=2, command=lambda btn=button_text: self.on_button_click(btn)).grid(row=row_val, column=col_val)
#             col_val += 1
#             if col_val > 3:
#                 col_val = 0
#                 row_val += 1
#
#         # Variables to store previous result and current operator
#         self.previous_result = 0
#         self.current_operator = None
#
#     def on_button_click(self, button_text):
#         if button_text.isdigit() or button_text == '.':
#             # If the button clicked is a digit or decimal point
#             current_text = self.entry.get()
#             new_text = current_text + button_text
#             self.entry.delete(0, tk.END)
#             self.entry.insert(0, new_text)
#         elif button_text in {'/', '*', '-', '+'}:
#             # If the button clicked is an arithmetic operator
#             self.calculate_result()
#             self.current_operator = button_text
#             self.previous_result = float(self.entry.get())
#             self.entry.delete(0, tk.END)
#         elif button_text == '=':
#             # If the button clicked is the equal sign
#             self.calculate_result()
#             self.current_operator = None
#
#     def calculate_result(self):
#         if self.current_operator and self.entry.get():
#             current_value = float(self.entry.get())
#             operation_function = self.operators.get(self.current_operator)
#             if operation_function:
#                 result = operation_function(self.previous_result, current_value)
#                 self.entry.delete(0, tk.END)
#                 self.entry.insert(0, str(result))
#                 self.previous_result = result
#
#     # Define arithmetic operation functions
#     def add(self, x, y):
#         return x + y
#
#     def subtract(self, x, y):
#         return x - y
#
#     def multiply(self, x, y):
#         return x * y
#
#     def divide(self, x, y):
#         if y != 0:
#             return x / y
#         else:
#             return "Error"
#
# if __name__ == "__main__":
#     root = tk.Tk()
#     app = CalculatorApp(root)
#     root.mainloop()

# *****************************************************************************************************
# Emotion text to emoji converter
# *****************************************************************************************************
# import sys
# from textblob import TextBlob
# from dataclasses import dataclass
# @dataclass
# class Mood:
#     emoji : str
#     sentiment : float
# def get_mood(input_text : str, *, sensitivity : float) -> Mood:
#     polarity: float = TextBlob(input_text).sentiment.polarity
#     friendly_threshold: float = sensitivity
#     hostile_threshold: float = -sensitivity
#     if polarity >= friendly_threshold:
#         return Mood('😍', polarity)
#     elif polarity <= hostile_threshold:
#         return Mood('😡',polarity)
#     else:
#         return Mood('😐',polarity)
# def run_bot():
#     print('enter some text to get emoji')
#     while True:
#         user_input : str = input('You:-')
#         mood: Mood = get_mood(user_input,sensitivity = 0.3)
#         print(f'Bot:- {mood.emoji} {mood.sentiment}')
#         if user_input == 'exit':
#             sys.exit()
# if __name__ == '__main__':
#     run_bot()
#

# *****************************************************************************************************
# PDF reader
# *****************************************************************************************************

# import re
# from collections import Counter
# from PyPDF2 import PdfReader
# def text_in_pdf(pdf_file: str) -> list[str]:
#     with open(pdf_file, 'rb') as pdf:
#         reader = PdfReader(pdf, strict=False)
#         print('pages: ', len(reader.pages))
#         print('-' * 20)
#         pdf_text: list[str] = [page.extract_text() for page in reader.pages]
#         return pdf_text
# def count_words(text_list: list[str]) -> Counter:
#     all_words: list[str] = []
#     for text in text_list:
#         split_text: list[str] = re.split(r'\s+|[,;?!.-}]\s*', text.lower())
#         all_words += [word for word in split_text if word]
#     return Counter(all_words)
# def main():
#     textinpdf: list[str] = text_in_pdf('/Users/cskraju/pythonProject/openpyxl/Linesfile and attriubutes file./Python projects udemy/sample.pdf')
#     counter: Counter = count_words(text_list=textinpdf)
#     for word, mention in counter.most_common(10):
#         print(f'{word:10}: {mention} times')
#     for page in textinpdf:
#         print(page)
#     print(textinpdf)
#
# if __name__ == '__main__':
#     main()

# *****************************************************************************************************
# chat bot
# *****************************************************************************************************
# import difflib
# from difflib import get_close_matches
# def best_match(user_question: str,questions: dict) -> str | None:
#     questions: list[str] = [q for q in questions]
#     matches: list = get_close_matches(user_question,questions,n = 1,cutoff = 0.6)
#     if matches:
#         return matches[0]
# def chat_bot(knowledge: dict):
#     user_input: str = input('you:- ')
#     best_match1: str | None = best_match(user_input,knowledge)
#     if answer := knowledge.get(best_match1):
#         print(f'Bot: {answer}')
#     else:
#         print(f'Bot: I do not understand...............')
# if __name__ == '__main__':
#     brain: dict = {'hello':'Hey there',
#                    'how are you':'I am good thanks',
#                    'bye':'see you'}
#     chat_bot(knowledge=brain)

# *****************************************************************************************************
# public API
# *****************************************************************************************************
# from flask import Flask,request
# from random import randint,choice
# from datetime import datetime
# app = Flask(__name__)
# @app.route('/')
# def index():
#     phrases : list[str] = ['welcome to this page','You are looking good today!','The weather is great']
#     return {'phrase': choice(phrases),
#             'date': datetime.now()}
# @app.route('/api/random')
# def random():
#     number_input = request.args.get('number',type = int, default= 100)
#     text_input = request.args.get('text',type = str,default = 'default_text')
#     if isinstance(number_input,int):
#         return {
#             {'input' : number_input},
#             {'random': randint(0, number_input)},
#             {'text': text_input},
#             {'date': datetime.now()}
#         }
# if __name__ == '__main__':
#     app.run()

# *****************************************************************************************************
# habit tracker
# *****************************************************************************************************

# from datetime import datetime
# from dataclasses import dataclass
# @dataclass
# class Habit:
#     name: str
#     time_since: str
#     remaining_days: str
#     minutes_saved: float
#     money_saved: str
# def track_habit(name:str,start:datetime,cost: float,minutes_used: float) -> Habit:
#     goal: int = 60
#     hourly_wage: int = 30
#     time_elapsed: float = (datetime.now() - start).total_seconds()
#     hours: float = round(time_elapsed/60/60,1)
#     days: float = round(hours/24,2)
#     money_saved: float= round(days * minutes_used)
#     total_money_saved: str = f'₹(){round(money_saved +(minutes_used/60 * hourly_wage),2)}'
#     days_to_go :float | str = round(goal - days)
#     remaining_days : str = 'Cleared!' if days_to_go <= 0 else f'{days_to_go}'
#     time_since: str = f'{days} days' if hours > 72 else  f'{hours} hours'
#     return Habit(name = name,time_since= time_since,remaining_days= remaining_days,money_saved= money_saved,minutes_saved=money_saved)




