لغت‌نامه
لغت‌نامه (dictionary) یک داده‌ساختار تغییر‌پذیر در پایتون است. لغت‌نامه را می‌توان لیستی تعریف کرد که اندیس‌های آن به جای این که عدد باشند، اشیای تغییر‌ناپذیر هستند. مانند رشته‌ها، اعداد و چندتایی‌هایی که شامل اشیای تغییرپذیر نمی‌شوند. لغت‌نامه از جفت‌هایی تشکیل شده‌ است. هرکدام از این جفت‌ها دارای یک کلید (key) و مقدار (value) می‌باشند. کلیدها نمی‌توانند تکراری باشند و هر کلید مقدار خاص و یکتایی دارد. می‌توان به مقدار هر کلید با داشتن آن، دسترسی پیدا کرد و آن را تغییر داد. دقت کنید که کلیدها تغییرناپذیر هستند.

ساختن لغت‌نامه
برای ساختن لغت‌نامه در پایتون از {} استفاده می‌کنیم به طوری که در آن جفت‌های کلید و مقدار به شکل key:value هستند و جفت‌ها با , از هم جدا شده‌اند. با استفاده از dict[key] میتوان به مقدار یک کلید خاص دسترسی پیدا کرد.

برای درک بهتر به مثال زیر دقت کنید :

```angular2html
>>> dict = {"ali": 12, "amir": 2.3}
>>> dict
{'ali': 12, 'amir': 2.3}
>>> dict['ali']
12
>>> dict['ali'] = 23
>>> dict
{'ali': 23, 'amir': 2.3}
>>> list(dict)
['ali', 'amir']
```

دقت کنید که list(dict) لیست کلید‌های dict را برمی‌گرداند. با استفاده dict() نیز می‌توان لغت‌نامه ساخت. ورودی آن لیستی از جفت‌های کلید و مقدار است. اگر به آن ورودی ندهید یک لغت‌نامه خالی برای شما می‌سازد. به مثال زیر دقت کنید :

```angular2html
>>> dict()
{}
>>> dict([("ali", 12), ("amir", 2.3)])
{'ali': 12, 'amir': 2.3}
```

افزودن و تغییر در لغت‌نامه
برای اضافه کردن یک مقدار x به لغت‌نامه dict با کلید key از dict[key] = x استفاده می‌کنیم. اگر کلید key از قبل در dict موجود باشد. مقدار آن به x تغییر می‌کند.



```angular2html
>>> age = {'mohamadreza':17}
>>> age['ali'] = 22
>>> age['mohamadreza'] = 18
>>> age
{'mohamadreza': 18, 'ali': 22}
```


جست‌وجو و دسترسی
برای اینکه بفهمیم یک کلید در یک لغت‌نامه وجود دارد از عملگر in استفاده می‌کنیم. به طور کلی اگر خروجی دستور x in myDict برابر True باشد یعنی کلید x در لغت‌نامه myDict وجود دارد در غیر این صورت چنین کلیدی در لغت‌نامه موردنظر وجود ندارد. به مثال زیر دقت کنید :


```angular2html
>>> square = {1: 1, 2: 4, 3: 9, 4: 16}
>>> 3 in square
True
>>> square[3]
9
>>> 5 in square
False
>>> square[5]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 5
```

از کد بالا می‌توان فهمید که برای دسترسی به مقدار کلید key در لغت‌نامه dict از dict[key] استفاده می‌شود. درضمن اگر این کلید در لغت‌نامه وجود نداشته باشد خطا رخ می‌دهد.

حذف از لغت‌نامه
برای حذف یک کلید و مقدار آن از یک لغت‌نامه از تابع pop یا دستور del استفاده می‌کنیم. تفاوت این دو روش در این است که تابع pop بعد از حذف، مقدار کلید موردنظر را بر می‌گرداند. برای درک این موضوع به مثال زیر توجه کنید :

```angular2html
>>> square = {1: 1, 2: 4, 3: 9, 4: 16}
>>> square.pop(3)
9
>>> del square[1]
>>> square
{2: 4, 4: 16}
>>> square.pop(5)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 5
```


دقت کنید که اگر کلید موردنظر در لغت‌نامه موجود نباشد خطای KeyError رخ می‌دهد.

دریافت مقادیر
با استفاده از dict.get(key, x) در صورتی که کلید key در لغت‌نامه باشد مقدار آن و در غیر این صورت x برگردانده می‌شود. دقت کنید که تعیین مقدار x اختیاری است. برای درک این موضوع به مثال زیر دقت کنید :

```angular2html
>>> grade = {'mamad': 20, 'ali':19, 'pooyan':19}
>>> grade.get('ali')
19
>>> grade['mahdi'] = grade.get('mahdi', 19) + 1 
>>> grade.get('mahdi')
20
```

در خط سوم برنامه ابتدا مقدار نمره mahdi را دریافت می‌کنیم. از آنجایی که mahdi در grade وجود ندارد مقدار ۱۹ با یک جمع می‌شود. در نهایت مقدار ۲۰ با کلید mahdi در grade قرار می‌گیرد.

گرفتن کلیدها و مقادیر
با استفاده از توابع keys و ‍values به ترتیب می‌توان کلیدها و مقادیر موجود در یک لغت‌نامه را بدست آورد. خروجی هر دو تابع یک شئ قابل پیمایش است با این تفاوت که نوع خروجی یکی dict_values و نوع دیگری dict_keys است. برای دریک این موضوع به مثال زیر دقت کنید :

```angular2html
>>> age = {'ali': 21, 'mmdreza': 18, 'mahdi': 22, 'pooyan':25}
>>> type(age.values())
<class 'dict_values'>
>>> type(age.keys())
<class 'dict_keys'>
>>> age.values()
dict_values([21, 18, 22, 25])
>>> list(age.values())
[21, 18, 22, 25]
>>>
```

معرف لغت‌نامه
لغت‌نامه نیز مانند لیست و مجموعه معرف دارد. تفاوت معرف‌ لغت‌نامه با معرف‌ لیست در این است که در عبارت اول، باید بین کلید و مقدار مربوطه یک : نوشته شود. برای مثال :

```angular2html
>>> {x:x*x for x in range(5)}
{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

اگر کلید‌ها فقط رشته باشند می‌توان لغت‌نامه را با dict() به گونه‌ای ساخت که در آن کلیدها و مقدار‌ها به صورت key=value آمده‌ و با کاما از هم جدا شده‌اند. دقت کنید که لازم نیست کلیدها را درون ' یا " بنویسید.
```angular2html
>>> dict(ali=12, amir=2.3)
{'ali': 12, 'amir': 2.3}
```

برای پیمایش کردن لغت‌نامه‌ها با for می‌توان از dict.items() استفاده کرد که خروجی آن مانند لیستی از جفت‌های کلید و مقدارهاست. مانند:

```angular2html
>>> d = {'ali': 'A', 'amir': 'B'}
>>> for k, v in d.items():
...     print(k + " got " + v)
... 
ali got A
amir got B
```