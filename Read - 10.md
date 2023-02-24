#فرمت‌بندی رشته

پایتون قابلیت‌های زیادی برای فرمت‌بندی رشته‌ها (String Formatting) در اختیار ما گذاشته‌ است که می‌توان از آن‌ها برای قراردادن مقدار متغیرها درون رشته‌ استفاده کرده تا کد را بهینه‌تر بزنیم.

استفاده از f برای فرمت‌بندی رشته
ساده‌ترین روش برای فرمت‌بندی رشته، استفاده از کاراکتر f است. به این صورت که قبل از رشته مورد نظر کاراکتر f را می‌نویسید. حال برای قرار دادن یک مقدار در هر جای رشته کافی است آن‌ را بین یک {} بنویسید. برای درک این قابلیت به مثال زیر توجه کنید:

```angular2html
>>> age = 12
>>> height = 178.5
>>> isMale = True
>>> f'Age : {age}, Height : {height}, Gender : {isMale}'
'Age : 12, Height : 178.5, Gender : True'
```

هم‌چنین در پایتون ۳.۸ می‌توانید هنگام استفاده از f با قرار دادن علامت = جلوی یک متغیر ، اسم آن متغیر را نیز به همراه مقدارش چاپ کنید. این کار هنگام چاپ کردن مقادیر متغیرها برای دیباگ کد می‌تواند مفید باشد.

```
>>> variable = 5
>>> f"{variable=}"
'variable=5'
```

استفاده از % برای فرمت‌بندی رشته
یک روش دیگر استفاده از عملگر % بعد از String است. شیوه‌ کار این عملگر به‌ این ترتیب‌ است که ابتدا در رشته‌ مورد نظر یکی از عبارت‌های %d یا %f یا ‍‍%s (به ترتیب برای متغیرهای صحیح، اعشاری و رشته‌ای) را قرار می‌دهیم. سپس به دنبال رشته یا متغیر رشته‌ای و بعد از عملگر % متغیری که می‌خواهیم جای مقدار نوشته شده در رشته قرار بگیرد را می‌نویسم. برای مثال به کد زیر توجه‌ کنید:

```
greeting = "Hello %s!"
name = input("Please enter your name:\n")
print(greeting % name)
```

این کد یک اسم از کاربر گرفته و در خروجی به او سلام می‌کند. توجه کنید که می‌توانیم به تابع input() یک رشته ورودی بدهیم. این رشته قبل از ورودی گرفتن از کاربر در کنسول به عنوان prompt چاپ خواهد شد.

اگر بخواهیم در رشته مورد نظرمان بیش از یک متغیر قرار دهیم، می‌توانیم بعد از عملگر % همه مقادیری که می‌خواهیم در رشته قرار بگیرند را به ترتیبی که در درون رشته آمده‌اند، درون پرانتز بنویسیم و مفسر همه مقادیر را به ترتیب درون رشته جایگزین می‌کند. برای مثال فرض‌ کنید که در مثال بالا می‌خواهیم علاوه بر اسم کاربر، سن او را نیز بپرسیم و آن را نمایش دهیم. در آن صورت چنین کدی خواهیم داشت :



```angular2html
greeting = "Hello %s with %d years old!"
name = input("Please enter your name:\n")
age = int(input("Please enter your age:\n"))
print(greeting % (name, age))
```

توجه‌ کنید که اگر تعداد مقادیری که درون پرانتز می‌نویسیم با تعداد کل مقادیری که رشته نیاز دارد برابر نباشد، مفسر به ما استثنا می‌دهد. همچنین در صورتی که بخواهید در رشته خود کاراکتر % را داشته باشید، می‌توانید از %% استفاده‌ کنید.

نکته:

برای ذخیره اعداد اعشاری با دقت مشخص می‌توانید از %.Xf استفاده کنید که در آن  X همان تعداد رقم اعشاری است که می‌خواهید چاپ کنید. (برای مثال برای ذخیره عدد اعشاری با دو رقم اعشار می‌توانید از %.2f استفاده کنید.)

استفاده از format() برای فرمت‌بندی رشته

یکی از روش‌های دیگر برای این‌کار که می‌تواند کار ما را ساده‌تر کند استفاده از دستور .format() است. برای استفاده از این دستور دو شیوه وجود دارد که در اینجا به توضیح آ‌ن‌ها می‌پردازیم (این روش، که تنها در پایتون ۳ وجود دارد، یکی از وجوه تمایز این نسخه از پایتون با نسخه های قبلی آن است).


روش اول

در این روش مکان‌هایی از رشته که قرار است با مقادیر دیگر جایگزین شوند را با استفاده از {} مشخص کرده و تابع format رشته را با مقادیری که می‌خواهید در آن مکان‌ها قرار بگیرد صدا کنید. در این صورت در خروجی رشته‌ای دریافت خواهید کرد که در آن مکان‌های {} به‌ترتیب با ورودی‌های تابع جایگزین شده‌اند. برای مثال کد مثال قبل را اکنون با استفاده از این تابع دوباره می‌زنیم.

```angular2html
greeting = "Hello {} with {} years old!"
name = input("Please enter your name:\n")
age = int(input("Please enter your age:\n"))
print(greeting.format(name, age))
```

برخلاف عملگر %، در این حالت تنها زمانی مفسر دچار استثنا می‌شود که تعداد ورودی‌های تابع کم‌تر از تعداد ورودی‌های خواسته شده‌ باشد. (اگر تعداد ورودی‌ها بیشتر باشد به ورودی‌های اضافه توجهی نمی‌کند)


روش دوم

اصلی‌ترین وجه تمایزی که استفاده از .format() نسبت به عملگر % دارد و باعث شده تا در پایتون ۳ اضافه‌ شود همین روش است. در این روش می‌توان درون {} یک عدد مثل i قرار داد که نشان می‌دهد عضو iام ورودی باید این جا قرار گیرد. همچنین می‌توان درون {} یک متغیر قرار داد، سپس در ورودی‌های تابع آن را مقداردهی کرد و آن مقدار در آن جا قرار می‌گیرد. برای درک بیشتر به مثال زیر توجه‌کنید.


```angular2html
>>> "Hello {0} with {1} years old!".format("Ali", "23")
'Hello Ali with 23 years old!'
>>> "Hello {name} with {age} years old!".format(name = "Ali", age = "23")
'Hello Ali with 23 years old!'
>>> "Hello {0} with {age} years old!".format("Ali", age = "23")
'Hello Ali with 23 years old!'
```


توجه‌ کنید که در صورت به‌کاربردن این روش، دیگر نمی‌توانید از ‍‍{} به صورت خالی استفاده‌ کنید. همچنین از توضیحاتی که در روش قبل، بعد از : می‌آمد، نیز می‌توانیم در این‌جا به شکل زیر استفاده‌ کنیم.


```angular2html
>>> "{0:.3f} {0:+}".format(23.12)
'23.120 +23.12'
>>> "{num:.3f} {num:+}".format(num=23.12)
'23.120 +23.12'
```

