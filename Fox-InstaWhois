import os
import sys
print ("<+> Insatlling requirements pip library ...")
if "win" in sys.platform:
    os.system("pip install pyfiglet colorama instagram_private_api")
    os.system("cls")
else:
    os.system("pip3 install pyfiglet colorama instagram_private_api")
    os.system("clear")

from instagram_private_api import Client
import instagram_private_api
import ssl
from pyfiglet import Figlet
import colorama
import json
import getpass
rd = colorama.Fore.RED
cv = colorama.Fore.WHITE
bl = colorama.Fore.BLUE
gn = colorama.Fore.GREEN
mag = colorama.Fore.MAGENTA
yl = colorama.Fore.YELLOW
gm = colorama.Fore.LIGHTGREEN_EX






ssl._create_default_https_context = ssl._create_unverified_context

figlet = Figlet(font="standard").renderText("Fox InstaWhois")
try:
    print (mag + figlet)
    username = input(gn + "[-] Enter Your username --> ")
    password = getpass.getpass(rd + "[-] Enter Your password --> ")
    client = Client(username=username,password=password)
    client.login()
    username = input(rd + "[+] Please enter your desired username to get full info EX : nasa => ")
    user = client.username_info(username)

    datax = json.dumps(user)
    data = json.loads(datax)
    info = data['user']

    print (yl + f"[+] Username : {info['username']}\n[+] User ID : {info['pk']}\n[+] Full Name : {info['full_name']}\n[+] is private : {info['is_private']}\n" + gn + f"[+] Post Count : {info['media_count']}\n[+] Follower count  : {info['follower_count']}\n[+] Following Count : {info['following_count']}\n[+] Biography : {info['biography']}\n\n"+ bl + f"[+] Profile Pic URL : {info['profile_pic_url']}\n[+] Profile Pic ID : {info['profile_pic_id']}" + cv)
    exit()
except instagram_private_api.errors.ClientLoginError:
    print (rd + "Username Or Password is invalid Try again :) " + cv)
    exit()
