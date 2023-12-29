# UDEMY-30-projects.

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

