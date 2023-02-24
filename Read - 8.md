#کتابخانه datetime

یکی دیگر از کتابخانه‌های مفید پایتون، کتابخانه datetime‍ است که برای دسترسی به زمان و ذخیره کردن آن به کار می‌رود. این کتابخانه در فریم‌ورک‌های وب مانند جنگو، بسیار پرکاربرد است.

مانند سایر کتابخانه‌ها، این کتابخانه را به شکل زیر می‌توانید به برنامه اضافه‌ کنید:

```angular2html
import datetime

```

استفاده از time

کتابخانه datetime دارای ویژگی‌های مختلفی است. یکی از آن ویژگی‌ها که در کار کردن با زمان‌های موجود در یک روز (یعنی زمان‌های کوچکتر از ۲۴ ساعت) می‌تواند مفید باشد، time است. برای این که بتوان به تنهایی این ویژگی را به برنامه اضافه کرد می‌توان از دستور زیر استفاده کرد :


```angular2html
from datetime import time

```

با کلیدواژه from در فصل‌های بعد به طور مفصل‌تر آشنا می‌شوید.

برای ساختن یک شی از نوع time می‌توان به آن ۴ ورودی داد که به ترتیب ساعت، دقیقه، ثانیه و میکروثانیه را مشخص می‌کنند. همچنین در صورتی که کم‌تر از ۴ ورودی دریافت کند بقیه ورودی‌ها صفر فرض می‌شوند. با استفاده از همین نام‌ها هم می‌توان به این ویژگی‌ها و مقادیر آن‌ها دسترسی داشت.

```angular2html
>>> from datetime import time
>>> t = time(17, 21, 20, 2021)
>>> t.hour = 10
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: attribute 'hour' of 'datetime.time' objects is not writable
>>> print(t.hour, t.minute, t.second, t.microsecond)
17 21 20 2021
>>> t = time()
>>> print(t.hour, t.minute, t.second, t.microsecond)
0 0 0 0
>>> type(t)
<class 'datetime.time'>
>>> t = time(34, 21)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: hour must be in 0..23
```

همان‌طور که می‌بینید می‌توان با دادن تعداد مختلفی (صفر تا چهار) ورودی به time‍‍ یک شکل از این نوع تولید کرد که جنس آن‌ها datetime.time است. همچنین ویژگی‌‌های یک شی از این نوع را نمی‌توان تغییر داد به عبارتی فقط خواندنی (Read-only) است.

نکته مهم دیگر که در تعریف time وجود دارد این است که هر یک از این چهار ورودی باید از نوع int و هر کدام از آن‌ها باید در بازه‌ای مشخص (که در جدول زیر گفته‌شده) باشند، در غیر این صورت استثنای ValueError دریافت خواهید کرد.

استفاده از date

date یکی از ویژگی‌های کتابخانه datetime است که برای کارکردن با روزها به کار می‌رود. برای اضافه‌کردن این شی می‌توانید مانند قبل از ‍‍from استفاده‌ کنید.

```
from datetime import date
```

برای ساختن یک ویژگی از این نوع هم می‌توانید به ‍‍date سه ورودی بدهید که به ترتیب سال و ماه و روز را مشخص می‌کند (توجه کنید که برخلاف time این‌جا باید حتما هر سه ورودی را بدهید). مثال‌های زیر را در نظر بگیرید.



```angular2html
>>> from datetime import date
>>> d = date(2019, 5, 23)
>>> print(d.year, d.month, d.day)
2019 5 23
>>> d.year = 23
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: attribute 'year' of 'datetime.date' objects is not writable
>>> d
datetime.date(2019, 5, 23)
>>> type(d)
<class 'datetime.date'>
>>> d = date(2019, 5)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: Required argument 'day' (pos 3) not found
>>> d = date(2019, 5, 32)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: day is out of range for month
```

همان طور که می‌بینید می‌توانیم یک شی از این نوع را با date تعریف‌ کرده و سپس به آن‌ دسترسی خواندن داشته باشیم، یعنی ‍date هم تغییرناپذیر است و همانند time نمی‌توانیم آن‌ها را تغییر دهیم.

همچنین هر یک از سه ویژگی سال، ماه و روز فقط می‌توانند در بازه‌های زیر باشند. در غیر این صورت ValueError دریافت خواهیدکرد.

توجه کنید که مقدار ویژگی روز، به مقدار ماه وابسته است (ممکن است بتواند مقدار ۳۱ را دریافت‌ بکند یا خیر).


استفاده از datetime

این ویژگی ترکیب دو ویژگی قبلی است و با استفاده از آن می‌توانید مقدار دقیق یک زمان را نگه‌داری کنید. برای تعریف یک ویژگی از این نوع مانند ویژگی‌های قبلی می‌توانید از datetime استفاده‌ کنید و به آن بین ۳ تا ۷ ورودی بدهید. این ورودی‌ها به ترتیب بزرگی (سال، ماه، روز و ...) ویژگی‌های آن زمان را مشخص می‌کنند. با استفاده از نام ویژگی‌ها به مقادیرشان و همچنین با استفاده از date و time می‌توان به دو قسمت از آن‌ (شامل تاریخ و زمان) دسترسی داشت. برای درک بهتر مثال زیر را در نظر بگیرید.



```angular2html
>>> from datetime import datetime
>>> dt = datetime(1, 2, 3, 4, 5, 6, 7)
>>> print(dt.year, dt.month, dt.day)
1 2 3
>>> print(dt.hour, dt.minute, dt.second, dt.microsecond)
4 5 6 7
>>> dt.date()
datetime.date(1, 2, 3)
>>> dt.time()
datetime.time(4, 5, 6, 7)
>>> type(dt)
<class 'datetime.datetime'>
>>> dt
datetime.datetime(1, 2, 3, 4, 5, 6, 7)
>>> dt = datetime(1, 2, 3, 4)
>>> print(dt.hour, dt.minute, dt.second, dt.microsecond)
4 0 0 0
```

می‌بینید که اگر تعدادی از ورودی‌های مربوط به time را ندهیم به طور پیش‌فرض صفر در نظر گرفته می‌شوند. تمام این ورودی‌ها مانند قبل باید در بازه مشخص‌شده قرار بگیرند.



یکی از خوبی‌های این ویژگی این است که با استفاده از تابع now() می‌توان به مقدار دقیق تاریخ و زمان در حال حاضر دسترسی داشت .



```angular2html
>>> datetime.now()
datetime.datetime(2019, 4, 29, 16, 15, 19, 375528)
```


