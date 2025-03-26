from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# إعداد المتصفح
driver = webdriver.Chrome()

# فتح موقع Quotex
driver.get("https://quotex.io/")

# الانتظار لتحميل الصفحة
time.sleep(5)

# إدخال بيانات تسجيل الدخول
email_input = driver.find_element(By.NAME, "email")
password_input = driver.find_element(By.NAME, "password")

email_input.send_keys("your_email@example.com")
password_input.send_keys("your_password")
password_input.send_keys(Keys.RETURN)

time.sleep(5)  # انتظار تسجيل الدخول

# الضغط على زر "شراء" كاختبار
buy_button = driver.find_element(By.XPATH, 'xpath_زر_الشراء')
buy_button.click()

print("تم تنفيذ صفقة شراء")

# إبقاء المتصفح مفتوحًا لبعض الوقت
time.sleep(10)
driver.quit()
