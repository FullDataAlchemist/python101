# اجرای‌ برنامه


برای این کار برنامه خود را در یک فایل ذخیره می‌کنیم‌ (بهتر است پسوند فایل .py باشد.) سپس با Terminal و یا CMD به مکان فایل می‌رویم و مفسر پایتون را روی آن اجرا می‌کنیم.

برای مثال اگر در فایل Test.py برنامه زیر نوشته شده باشد.

```angular2html
print("salam")
```

در صورتی که لازم باشد بعد از چاپ عبارت به خط بعدی نرویم به این صورت عمل می‌کنیم (متغیر end را مقداردهی می‌کنیم):


```angular2html
print("Salam", end=' ')
print("Khoobi?")
```

دقت کنید که مقدار پیش‌فرض end برابر با \n است و شما می‌توانید آن را تغییر دهید.

همان‌طور که در مفسر می‌توانستیم یک متغیر تعریف کنیم، در کد پایتون هم می‌توانیم این کار را انجام دهیم؛ سپس آن را به دستور print که مقدار آن را چاپ می‌کند بدهیم. برای مثال در کد زیر ابتدا دو متغیر int تعریف می‌کنیم و سپس به دو روش آن‌ها را چاپ می‌کنیم.

```
x = 3
y = 5
print(x)
print("sum =", x + y)
```

با اجرای این کد، خروجی زیر چاپ خواهد‌ شد.

```angular2html
3
sum = 8
```

همان طور که می‌بینید می‌توان به دستور print چند ورودی داد که این دستور آن‌ها را با یک فاصله (space) از هم چاپ می‌کند.

از دیگر کارهایی که در برنامه‌نویسی بسیار مهم است، ورودی گرفتن است. در پایتون این کار با استفاده از دستور input() انجام می‌شود. خروجی این دستور یک رشته است که نشان‌دهنده یک خط از ورودی‌ است (در فصل های بعد توضیحات مفصلی درباره رشته داده خواهد شد).

برای مثال در کادر پایین کدی را مشاهده می‌کنید که یک رشته از ورودی گرفته و دو بار آن را در خروجی چاپ می‌کند.

```angular2html
s = input()
print(s, s)
```

