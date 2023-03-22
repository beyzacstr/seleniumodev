# seleniumodev
from selenium import webdriver
from selenium.webdriver.common.by import By
from time import sleep

class saucademotest :
    # username ve passwordun boş bırakılması
    def case1(self):
        driver=webdriver.Chrome()
        driver.get("https://www.saucedemo.com/")
        sleep(2)
        usernameInput=driver.find_element(By.ID,"user-name")
        usernameInput.send_keys("")
        sleep(2)
        passwordInput=driver.find_element(By.ID,"password")
        sleep(2)
        passwordInput.send_keys("")
        sleep(5)
        loginbutton=driver.find_element(By.ID,"login-button")
        loginbutton.click()
        sleep(10)
        errormesag=driver.find_element(By.XPATH,"/html/body/div/div/div[2]/div[1]/div/div/form/div[3]/h3")
        errormesag.text=="Epic sadface: Username is required"
        print(errormesag.text)


    def case2(self):
        driver=webdriver.Chrome()
        driver.get("https://www.saucedemo.com/")
        sleep(2)
        usernameInput=driver.find_element(By.ID,"user-name")
        usernameInput.send_keys("")
        sleep(2)
        passwordInput=driver.find_element(By.ID,"password")
        sleep(2)
        passwordInput.send_keys("")
        sleep(5)
        loginbutton=driver.find_element(By.ID,"login-button")
        loginbutton.click()
        sleep(100)
        errormesag2=driver.find_element(By.XPATH,"/html/body/div/div/div[2]/div[1]/div/div/form/div[3]/h3")
        errormesag2.text=="Epic sadface: Password is required"
        print(errormesag2.text)

    def case3(self):
        driver=webdriver.Chrome()
        driver.get("https://www.saucedemo.com/")
        sleep(2)
        usernameInput=driver.find_element(By.ID,"user-name")
        usernameInput.send_keys("locked_out_user")
        sleep(2)
        passwordInput=driver.find_element(By.ID,"password")
        sleep(2)
        passwordInput.send_keys("secret_sauce")
        sleep(5)
        loginbutton=driver.find_element(By.ID,"login-button")
        loginbutton.click()
        sleep(10)
        errormesag3=driver.find_element(By.XPATH,"/html/body/div/div/div[2]/div[1]/div/div/form/div[3]/h3")
        errormesag3.text=="Epic sadface: Sorry, this user has been locked out"
        print(errormesag3.text)
    
    def case4(self):
        driver=webdriver.Chrome()
        driver.get("https://www.saucedemo.com/")
        sleep(2)
        usernameInput=driver.find_element(By.ID,"user-name")
        usernameInput.send_keys("")
        sleep(2)
        passwordInput=driver.find_element(By.ID,"password")
        sleep(2)
        passwordInput.send_keys("")
        sleep(5)
        loginbutton=driver.find_element(By.ID,"login-button")
        loginbutton.click()
        sleep(5)
        redbutton=driver.find_element(By.CLASS_NAME,"error-button")
        redbutton.click()
        sleep(10)

    def case5(self):
        driver=webdriver.Chrome()
        driver.get("https://www.saucedemo.com/")
        sleep(2)
        usernameInput=driver.find_element(By.ID,"user-name")
        usernameInput.send_keys("standard_user")
        sleep(2)
        passwordInput=driver.find_element(By.ID,"password")
        sleep(2)
        passwordInput.send_keys("secret_sauce")
        sleep(5)
        loginbutton=driver.find_element(By.ID,"login-button")
        loginbutton.click()
        while True:
            continue
        

    
deneme=saucademotest()
deneme.case1()
deneme.case2()
deneme.case3()
deneme.case4()
deneme.case5()
