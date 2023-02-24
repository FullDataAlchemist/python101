لیست ۲
استفاده‌ از لیست به عنوان پشته
با استفاده از لیست در پایتون به سادگی می‌توان یک پشته (Stack) را پیاده سازی کرد. با تابع append() یک عضو به انتهای پشته اضافه و با تابع pop() آخرین عضو آن حذف می‌شود.

```angular2html
>>> stack = ["first", "second", "third"]
>>> stack
['first', 'second', 'third']
>>> stack.append('fourth')
>>> stack.append('fifth')
>>> stack
['first', 'second', 'third', 'fourth', 'fifth']
>>> stack.pop()
'fifth'
>>> stack
['first', 'second', 'third', 'fourth']
```


استفاده از لیست به عنوان صف
می‌توان با دو تابع append() و pop(0) صف (Queue) را با لیست پیاده سازی کرد. عضو اول لیست نشان دهنده سر صف و عضو آخر لیست نشان دهنده‌ی انتهای صف است.

```angular2html
>>> queue = ["ali", "mohammad"]
>>> queue.append("reza") # similar to push
>>> queue.append("amir") 
>>> queue
['ali', 'mohammad', 'reza', 'amir']
>>> queue[0] # similar to top
'ali'
>>> queue.pop(0)
'ali'
>>> queue
['mohammad', 'reza', 'amir']
```


پیمایش لیست
ساده‌ترین روش پیمایش لیست با ‍for و بدون استفاده از هیچ تابع واسطه‌ای است. چون لیست پیمایش‌شونده است پس می‌توان آن را به سادگی با for پیمود.

```angular2html
>>> myList = ['ali', 1, 2, 3, 'chetor']
>>> for it in myList:
...     print(it)
... 
ali
1
2
3
chetor
```

توابع کاربردی
در اینجا به چند تابع کاربردی می‌پردازیم که پیمایش اشیا را برای شما راحت‌تر می‌کند.

تابع enumerate
با این تابع می‌توان اندیس یک شیء که پیمایش می‌شود را نیز هم‌زمان با خود شیء در دسترس داشت.

```angular2html
>>> myList = [0, 1, 2, 3]
>>> for i, it in enumerate(myList):
...     print("the {0}th object in myList is {1}!".format(i+1, it))
... 
the 1th object in myList is 0!
the 2th object in myList is 1!
the 3th object in myList is 2!
the 4th object in myList is 3!
```

تابع zip
با استفاده از این تابع می‌توان چند لیست را به طور هم‌زمان پیمود.

```angular2html
>>> listA = [1, 2, 3, 4]
>>> listB = ['a', 'b', 'c', 'd']
>>> listC = ['I', 'II', 'III', 'IV']
>>> for a, b, c in zip(listA, listB, listC):
...     print("{0}th alphabet or {1} in greece is {2}".format(a, c, b))
... 
1th alphabet or I in greece is a
2th alphabet or II in greece is b
3th alphabet or III in greece is c
4th alphabet or IV in greece is d
```

تابع sorted
این تابع مرتب شده‌ی لیست ورودی را در قالب لیستی جدید بر می‌گرداند.


```angular2html
>>> ls = [2, 4, 3, 1]
>>> sorted(ls)
[1, 2, 3, 4]
```


تابع reversed
این تابع یک پیمایش‌گر لیست برمی‌گرداند که لیست ورودی را به صورت برعکس می‌پیماید. برای درک بهتر به مثال زیر دقت کنید:

```angular2html
>>> ls = ['a', 'bcd', 'salam', 'hello']
>>> reversed(ls)
<list_reverseiterator object at 0x10a189908>
>>> for i in reversed(ls):
...     print(i, end=' ')
... 
hello salam bcd a
```

دقت کنید که با دستورات for و reversed می‌توان لیست را به صورت برعکس پیمود.

تابع filter
این تابع به عنوان آرگومان به ترتیب یک تابع (فرض کنید f) و یک شیء قابل پیمایش (فرض کنید iter) را می‌گیرد. تابع f را برای همه‌ی عناصر شیء iter صدا می‌زند. اگر خروجی False بود آن عنصر را حذف می‌کند. نهایتا نتیجه را در قالب یک پیمایشگر بر‌می‌گرداند. به مثال زیر دقت کنید :

```
دقت کنید که با دستورات for و reversed می‌توان لیست را به صورت برعکس پیمود.

تابع filter
این تابع به عنوان آرگومان به ترتیب یک تابع (فرض کنید f) و یک شیء قابل پیمایش (فرض کنید iter) را می‌گیرد. تابع f را برای همه‌ی عناصر شیء iter صدا می‌زند. اگر خروجی False بود آن عنصر را حذف می‌کند. نهایتا نتیجه را در قالب یک پیمایشگر بر‌می‌گرداند. به مثال زیر دقت کنید :>>> def f(x):
...    return True if x%2 == 0 else False
...
>>> ls = [1, 2, 4, 3, 6, 4]
>>> filter(f, ls)
<filter object at 0x00B77E50>
>>> for x in filter(f, ls):
...     print(x, end=' ')
...
2 4 6 4
```

تابع map
ساختار این تابع همانند filter است ولی عملکرد آن‌ها با هم متفاوت است. به این صورت که تابع f را برای همه‌ی عناصر شیء iter صدا می‌زند و خروجی آن را جایگزین عنصر کنونی iter می‌کند. نهایتا نتیجه را در قالب یک پیمایشگر بر‌می‌گرداند. به مثال زیر دقت کنید :

```
>>> def f(x):
...    return int(x)
...
>>> ls = [2, '4', False, 3.14]
>>> map(f, ls)
<map object at 0x00B77F90>
>>> for x in map(f, ls):
...     print(x, end=' ')
...
2 4 0 3
>>> for x in map(int, ls):
...     print(x, end=' ')
...
2 4 0 3
```

در مثال بالا int را به عنوان آرگومان به map دادیم. ولی آن‌ را از قبل تعریف نکرده‌ بودیم. ولی همان‌طور که در درس‌های گذشته دیدیم، int یک ورودی می‌گیرد و آن را به عدد صحیح تبدیل می‌کند. در نتیجه می‌توان با استفاده از یک خط در یک خط به تعداد دلخواه ورودی گرفته و آن‌ها را با استفاده از تابع map به روش‌های گوناگونی تغییر داد. فرض کنید می‌خواهید در یک خط تعداد نامشخصی عدد را از کاربر دریافت کرده و جمع آن‌ها را بدست آورید :

```angular2html
>>> number = map(int, input().split())
1 2 3 4 5
>>> sum(number)
15
```

تابع sum
با استفاده از تابع sum می‌توان حاصل جمع مقادیر درون یک شیء قابل پیمایش را بدست آورد. دقت کنید که مقادیر درون شیء موردنظر باید حتما از نوع عددی باشند. به مثال زیر دقت کنید :

```angular2html
>>> ls = [1, 2, 3, 4]
>>> sum(ls)
10
>>> ls = ['a', 'b', 'c', 'd']
>>> sum(ls)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

