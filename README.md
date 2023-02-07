# limpar-area-transferencia
Limpar área de transferência
private void showStatusItem_Click(object sender, EventArgs e)

from ctypes import windll
from time import sleep
from infi.systray import SysTrayIcon

def say_hello(systray):
    print("Hello, World!")
menu_options = (("Say Hello", None, say_hello),)
systray = SysTrayIcon("icon.ico", "Cópia Controlada", menu_options)
while True:
    try:
        if windll.user32.OpenClipboard(None):
            windll.user32.EmptyClipboard()
            windll.user32.CloseClipboard()
        sleep(2)
    except windll:
        print("Clipboard is empty.")
        sleep(2)

systray.start()
