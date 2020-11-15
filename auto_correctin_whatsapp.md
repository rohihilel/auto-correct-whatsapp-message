# auto-correct-whatsapp-message
#auto correcting WhatsApp message if you accidently wrote in english and you meant to write in hebrew And reverse.
#pip install selenium
#install chromedriver
from selenium import webdriver
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.common.keys import Keys
import time
from selenium.webdriver.chrome.options import Options
import pandas as pd

datainput = pd.read_csv(r'C:\Users\roee hilel\Downloads\english_words\english.csv')

chrome_options = Options()
#chrome_options.add_argument("start-maximized")
driver = webdriver.Chrome(r"C:\chromedriver.exe",
                              options=chrome_options)
driver.get("https://web.whatsapp.com")
input("enter")
driver.minimize_window()

while True:
    contact = input("for how?\n")



    inp_xpath_search = "//*[@id=\"side\"]/div[1]/div/label/div/div[2]"
    input_box_search = WebDriverWait(driver, 50).until(
        lambda driver: driver.find_element_by_xpath(inp_xpath_search))
    input_box_search.click()
    time.sleep(2)
    input_box_search.send_keys(contact)
    input_box_search.send_keys(Keys.ENTER)
    time.sleep(2)

    while True:



        word = input("enter massage:\n")
        word = word.lower()
        s = list(word)
        n = word.split()
        none = []
        if word == "ch":
            break

        else:

            if "z" in s or "y" in s or "x" in s or "w" in s or "v" in s or "u" in s or "t" in s or "s" in s or "r" in s or "q" in s or "p" in s or "o" in s or "n" in s or "m" in s or "l" in s or "k" in s or "j" in s or "i" in s or "h" in s or "g" in s or "f" in s or "e" in s or "d" in s or "c" in s or "b" in s or "a" in s:

                if [(m if m in datainput.values else (None, none.append(m))) for m in n] != n:
                    print("written in english")

                    for i in range(len(s)):

                        if s[i] == 'a':
                            s[i] = 'ש'

                        if s[i] == 'b':
                            s[i] = 'נ'

                        if s[i] == 'c':
                            s[i] = 'ב'
                        if s[i] == 'd':
                            s[i] = 'ג'

                        if s[i] == 'e':
                            s[i] = 'ק'

                        if s[i] == 'f':
                            s[i] = 'כ'
                        if s[i] == 'g':
                            s[i] = 'ע'

                        if s[i] == 'h':
                            s[i] = 'י'

                        if s[i] == 'i':
                            s[i] = 'ן'
                        if s[i] == 'j':
                            s[i] = 'ח'

                        if s[i] == 'k':
                            s[i] = 'ל'

                        if s[i] == 'l':
                            s[i] = 'ך'
                        if s[i] == 'm':
                            s[i] = 'צ'

                        if s[i] == 'n':
                            s[i] = 'מ'

                        if s[i] == 'o':
                            s[i] = 'ם'
                        if s[i] == 'p':
                            s[i] = 'פ'

                        if s[i] == 'q':
                            s[i] = '/'

                        if s[i] == 'r':
                            s[i] = 'ר'
                        if s[i] == 's':
                            s[i] = 'ד'

                        if s[i] == 't':
                            s[i] = 'א'

                        if s[i] == 'u':
                            s[i] = 'ו'
                        if s[i] == 'v':
                            s[i] = 'ה'

                        if s[i] == 'w':
                            s[i] = "'"

                        if s[i] == 'x':
                            s[i] = 'ס'
                        if s[i] == 'y':
                            s[i] = 'ט'

                        if s[i] == 'z':
                            s[i] = 'ז'
                        if s[i] == ',':
                            s[i] = 'ת'

                        if s[i] == '.':
                            s[i] = 'ץ'
                        if s[i] == 'y':
                            s[i] = 'ט'

                        if s[i] == ';':
                            s[i] = 'ף'
                    new = "".join(s)
                else:
                    new = word



            elif "א" in s or "ב" in s or "ג" in s or "ד" in s or "ה" in s or "ו" in s or "ז" in s or "ח" in s or "ט" in s or "י" in s or "כ" in s or "ל" in s or "מ" in s or "נ" in s or "ס" in s or "ע" in s or "פ" in s or "ק" in s or "צ" in s or "ר" in s or "ש" in s or "ת" in s or "'" in s or " " in s:
                print("written in hebrew")

                for i in range(len(s)):

                    if s[i] == 'ש':
                        s[i] = 'a'

                    if s[i] == 'נ':
                        s[i] = 'b'

                    if s[i] == 'ב':
                        s[i] = 'c'
                    if s[i] == 'ג':
                        s[i] = 'd'

                    if s[i] == 'ק':
                        s[i] = 'e'

                    if s[i] == 'כ':
                        s[i] = 'f'
                    if s[i] == 'ע':
                        s[i] = 'g'

                    if s[i] == 'י':
                        s[i] = 'h'

                    if s[i] == 'ן':
                        s[i] = 'i'
                    if s[i] == 'ח':
                        s[i] = 'j'

                    if s[i] == 'ל':
                        s[i] = 'k'

                    if s[i] == 'ך':
                        s[i] = 'l'
                    if s[i] == 'צ':
                        s[i] = 'm'

                    if s[i] == 'מ':
                        s[i] = 'n'

                    if s[i] == 'ם':
                        s[i] = 'o'
                    if s[i] == 'פ':
                        s[i] = 'p'

                    if s[i] == '/':
                        s[i] = 'q'

                    if s[i] == 'ר':
                        s[i] = 'r'
                    if s[i] == 'ד':
                        s[i] = 's'

                    if s[i] == 'א':
                        s[i] = 't'

                    if s[i] == 'ו':
                        s[i] = 'u'
                    if s[i] == 'ה':
                        s[i] = 'v'

                    if s[i] == "'":
                        s[i] = "w"

                    if s[i] == 'ס':
                        s[i] = 'x'
                    if s[i] == 'ט':
                        s[i] = 'y'

                    if s[i] == 'ז':
                        s[i] = 'z'
                    if s[i] == 'ת':
                        s[i] = ','

                    if s[i] == 'ץ':
                        s[i] = '.'

                    if s[i] == 'ף':
                        s[i] = ";"
                new = "".join(s)
                if [(m if m in datainput.values else (None, none.append(m))) for m in new.split()] != new.split():
                    new = word





            if len(none) == 0:
                print()
            else:
                print("may be not true, the words are: ")
                print(none)



            inp_xpath = "//*[@id=\"main\"]/footer/div[1]/div[2]/div/div[2]"
            input_box = driver.find_element_by_xpath(inp_xpath)

            input_box.send_keys(new + Keys.ENTER)



