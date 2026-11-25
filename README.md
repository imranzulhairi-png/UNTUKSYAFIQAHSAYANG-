
# UNTUKSYAFIQAHSAYANG-

import os
import time
import math

# Warna ANSI
PINK = "\033[95m"
RED = "\033[91m"
PURPLE = "\033[35m"
WHITE = "\033[97m"
RESET = "\033[0m"

# Tulisan di tengah hati
message = "loveyoumalove"

def clear():
    os.system("clear")

def draw_heart(scale):
    width = 40
    height = 18

    for y in range(height, -height, -1):
        line = ""

        for x in range(-width, width):
            # Formula matematik bentuk hati
            xx = x / 20
            yy = y / 10

            value = (xx**2 + yy**2 - 1)**3 - xx**2 * yy**3

            if value <= 0:
                line += "*"
            else:
                line += " "

        print(line)

def show_love():
    colors = [PINK, RED, PURPLE]

    while True:
        for color in colors:
            clear()

            print(color)

            draw_heart(1)

            print()
            print(WHITE + "       " + message + RESET)
            print()
            print(color + "       ♥ ♥ ♥ ♥ ♥" + RESET)

            time.sleep(0.3)

try:
    show_love()

except KeyboardInterrupt:
    clear()
    print(PINK + "loveyoumalove ♥" + RESET)
    print("Program dihentikan.")

