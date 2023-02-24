مجموعه
مجموعه (‍Set) یک داده‌ساختار تغییرپذیر در پایتون مانند مجموعه در ریاضی است. تفاوت مجموعه با لیست در این است که مجموعه ترتیب و تکرار ندارد. برای ساخت مجموعه می‌توان از {} یا set() استفاده کرد. البته باید به این نکته توجه کرد که برای ساختن مجموعه تهی فقط می‌توان از set() استفاده کرد.

```angular2html
>>> type(set())
<class 'set'>
>>> st = {2, 3, 1}
>>> st
{1, 2, 3}
>>> len(st)
3
>>> type(st)
<class 'set'>
>>> st = {}
>>> type(st)
<class 'dict'>
```

در خط آخر می‌توان دید که با استفاده از {} می‌توان یک لغت‌نامه ساخت. بعدا در مورد آن توضیح خواهیم داد.

افزودن به مجموعه
برای اضافه کردن یک مقدار به مجموعه از تابع add استفاده می‌کنیم. اگر مقدار ورودی این تابع از قبل در مجموعه وجود داشته باشد از اجرای این دستور چشم‌پوشی می‌شود :

```angular2html
>>> names = set()
>>> names.add('ali')
>>> names.add('mohamadreza')
>>> names.add('amir')
>>> names.add('amir')
>>> names
{'amir', 'mohamadreza', 'ali'}
```

جست‌و‌جو در مجموعه
برای اینکه بفهمیم یک مقدار در یک مجموعه‌ وجود دارد از عملگر in استفاده می‌کنیم. به طور کلی اگر خروجی دستور x in mySet برابر True باشد یعنی مقدار x در مجموعه mySet وجود دارد در غیر این صورت چنین مقداری در مجموعه موردنظر وجود ندارد. به مثال زیر دقت کنید :

```angular2html
>>> nums = set()
>>> nums.add(1)
>>> nums.add(2)
>>> nums.add(3)
>>> 1 in nums
True
>>> 4 in nums
False
```

حذف از مجموعه
برای حذف یک مقدار از یک مجموعه از تابع remove یا discard استفاده می‌کنیم. تفاوت این دو تابع در این است که اگر مقدار ورودی remove در مجموعه موردنظر نباشد خطا رخ می‌دهد. به مثال زیر توجه کنید :

```angular2html
>>> a = {1, 2, 3}
>>> a.remove(1)
>>> a.discard(2)
>>> a
{3}
>>> a.discard(4)
>>> a.remove(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 4
```

عملگر‌ها در مجموعه
همانطور که برای کار با مجموعه‌ها در ریاضیات تعدادی عملگر وجود دارد، در پایتون نیز چنین عملگرهایی وجود دارد. این عملگرها در عین سادگی بسیار کاربرد دارند.

اشتراک و اجتماع
برای بدست آوردن اشتراک بین دو مجموعه a و b می توان از تابع intersection یا عملگر & استفاده کرد. همچنین از تابع union و عملگر | برای بدست آوردن اجتماع دو مجموعه استفاده می‌کنیم.

```angular2html
>>> a = {1, 2, 3}
>>> b = {3, 2, 4}
>>> a.intersection(b)
{2, 3}
>>> b.intersection(a)
{2, 3}
>>> a & b
{2, 3}
>>> b.union(a)
{1, 2, 3, 4}
>>> a | b
{1, 2, 3, 4}
```

تفاضل و دلتا (تفاضل متقارن)
برای بدست آوردن تفاضل a و b می توان از تابع difference یا عملگر - استفاده کرد. همچنین از تابع symmetric_difference و عملگر ^ برای بدست آوردن دلتا استفاده می‌کنیم. دقت کنید که a ^ b برابر با تفاضل اجتماع و اشتراک a و b به عبارتی همان (a | b) - (a & b) می‌باشد.

```angular2html
>>> a = {1, 2, 3}
>>> b = {3, 2, 4}
>>> a.difference(b)
{1}
>>> b - a
{4}
>>> a ^ b
{1, 4}
>>> b.symmetric_difference(a)
{1, 4}
```

معرف مجموعه
مجموعه نیز مانند لیست، معرف دارد. تفاوت معرف‌ مجموعه با معرف‌ لیست این است که بجای [] از {} استفاده می‌کنیم. به مثال‌های زیر دقت کنید :

```angular2html
>>> a = set("salam")
>>> b = set("varam")
>>> {x for x in a if x not in b}
{'s', 'l'}
```