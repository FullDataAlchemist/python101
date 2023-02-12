دستورات کنترلی ۱
در این بخش و بخش بعدی به دستورات پایه برای کنترل کردن جریان برنامه می‌پردازیم.

دستورات کنترلی دستوراتی هستند که با توجه به شرطی که برای آن‌ها تعریف می‌شود تصمیم می‌گیرند که چه دستوراتی بعد از آن‌ها انجام شوند.

محدوده‌بندی
مانند سایر زبان‌های برنامه‌‌‌نویسی، در پایتون‌ هم بعد از دستورات کنترلی محدوده‌ای وجود دارد که در آن دستوراتی نوشته می‌شود که طبق دستور کنترلی اجرا می‌شود.

در اغلب زبان های برنامه نویسی مانند java، c و ...، این محدوده با آکولاد {} مشخص می شود و کاراکتر‌های فضای سفید (Enter, Tab, Space) نادیده گرفته می‌شوند. اما در پایتون برای تعریف محدوده (Scope) باید تمام دستورات درون آن محدوده را با فاصله بیش‌تر نسبت به دستور قبل از شروع محدوده بنویسیم (قبل از آن‌ها یک Tab اضافه می‌گذاریم). درواقع پایتون با فاصله، ساختار می‌یابد. در صورتی هم که این کار را انجام ندهیم مفسر خطا داده و برنامه اجرا نمی‌شود.

```
x = 10
def f():
    if x % 2 == 0:
        print("even")
    else:
        print("odd")
```

در ادامه‌ی این درس‌نامه با شرط if/else‍ و در ادامه‌ی فصل با توابع در پایتون (def) آشنا خواهید شد.
هم‌چنین در ادامه‌ی تمامی دستورات کنترلی در محدوده‌ی آن‌ها حتما باید دستوری برای اجرا نوشته شود (اگر محدوده خالی باشد خطای IndentationError برگردانده می شود). در صورتی که نخواهیم در محدوده‌ای چیزی اجرا شود، می‌توانیم دستور pass را به تنهایی در آن محدوده قرار دهیم. این دستور به مفسر می‌گوید بدون انجام هیچ کاری از این خط عبور کن.

```
def f():
    pass
```

دستورهای شرطی
دستور if با توجه به شرطی که بعد از آن می‌آيد، جریان برنامه را به مسیر‌های مختلفی هدایت می‌کند. یعنی اگر شرط درست بود، دستورات محدوده مربوط به if اجرا می‌شود؛ در غیر این صورت ادامه دستورات اجرا می‌شوند.

ساختار دستور if در پایتون به این شکل است :

```
if condition:
    # statement
    pass
```

با دستور else می‌توان جریان برنامه را در صورت برقرار نبودن شرط نیز به سمت خاصی هدایت کرد.


```
if condition:
    # condition is true
    pass
else:
    # condition is false (Not true)
    pass
```


با دستور elif که خلاصه شده‌ی else if است، می‌توان در صورت عدم برقراری شرط قبلی، شرط دیگری را نیز بررسی کرد.

```
if condition1:
    # condition1 is true
    pass
elif condition2:
    # condition1 is false and condition2 is true
    pass
```

برای مثال فرض کنید می‌خواهیم برنامه‌ای بنویسیم که دو عدد از ورودی گرفته و عدد بزرگ‌تر را چاپ کند. در آن صورت می‌توانیم به شکل زیر از دستور if استفاده کنیم.

```
a = int(input())
b = int(input())
if a > b:
    print(a)
else:
    print(b)
```

آنچه اتفاق می افتد را توضیح دهید.