# fishing_bot
import time
import cv2
import numpy as np
from PIL import ImageGrab

average = [0,]

template = cv2.imread('template.png', 0)
w, h = template.shape[::-1]

for _ in range(1000):
    time.sleep(1)
    pyautogui.moveTo(100, 100)
    time.sleep(0.5)
    pyautogui.mouseDown()
    time.sleep(0.4)
    pyautogui.mouseUp()
    time.sleep(3)

    base_screen = ImageGrab.grab(bbox=(0,0,1750,450))
    base_screen.save('/Users/ipadi/screenshot/bot/base_screen.png')

    img_rgb = cv2.imread("base_screen.png")
    img_gray = cv2.cvtColor(img_rgb, cv2.COLOR_BGR2GRAY)

    res = cv2.matchTemplate(img_gray, template, cv2.TM_CCOEFF_NORMED)
    loc = np.where(res >=0.7)

for i in range(40):
    try:
        clean_screen_ImageGrab.grab(bbox=(x, y, x + w, y + h))
        mean = np.mean(clean_screen)
        diff = average[-1] - mean
        print(average[-1] - mean)
        if diff >= 0:
            pyautogui.moveTo(x / 2 + 15, y / 2 + 15)
            print('Курсор навёл на поплавок')
            pyautogui.mouseDown()
            time.sleep(0.4)
            pyautogui.mouseUp()
            break
        average.append(mean)
    except:
           for pt in zip(*loc[::-1]):
               x = int(pt[0])
               y = int(pt[1])
           time.sleep(0.2)
    pyautogui.moveTo(100, 100)
    try:
        del(x)
        del(y)
    except:
        pass
    average = [0,]
    time.sleep(1)

