رجکس چیست؟

رجکس، مخفف عبارت Regular Expression است. این عبارت اصطلاحی است که به الگوهایی که برای استخراج اطلاعات از داده‌های متنی استفاده می‌شوند، اطلاق می‌شود. این الگوها خود داده‌هایی از جنس رشته هستند. در واقع رجکس، الگویی است که ما تعریف می‌کنیم تا یک رشته‌ی مطابق میل خود را ورودی بگیریم یا از میان یک متن، قسمتی را که دلخواه خود است پیدا کنیم. شایان ذکر است که رجکس مفهوم مستقلی است و فقط مخصوص پایتون نیست، بلکه در همه زبان‌های برنامه نویسی وجود دارد. در این درس‌نامه، به بررسی کلی رجکس (مستقل از پایتون) می‌پردازیم.

به عنوان مثال برای ثبت‌نام در بسیاری از سایت‌ها لازم است آدرس ایمیل خود را وارد کنیم. برای چک کردن اینکه آیا این آدرس ایمیل با الگوی آدرس‌های ایمیل مطابقت دارد یا خیر از رجکس استفاده می‌شود. یا ممکن است در برنامه‌ای نیاز داشته باشیم پلاک ماشین کاربر را از او ورودی بگیریم، و ورودی او را با یک الگوی رجکس مقایسه می‌کنیم تا از معتبر بودن آن مطمئن باشیم و اگر کاربر اطلاعات غلط وارد کرد برنامه‌ی ما به مشکل نخورد.


نکته: 

ممکن است این سوال پیش بیاید که "وقتی می‌توانیم از متدهای رشته استفاده کنیم چرا رجکس؟" مثلا برای اعتبارسنجی یک شماره موبایل کافی است بدین صورت آن‌را اعتبارسنجی کنیم:

```angular2html
mobile_number = input()
if len(mobile_number) == 11 and mobile_number.startswith('09') and mobile_number.isdigit(): 
    print('✅Valid mobile number')
else:
    print('❌Invalid mobile number')
```

چالش

سعی کنید مانند قطعه‌کد فوق (اعتبارسنجی شماره موبایل)، با استفاده از متدهای رشته، ورودی را بر اساس الگوی ایمیل اعتبارسنجی کنید.

برای اعتبارسنجی‌های ساده از جمله شماره موبایل شاید استفاده از رجکس تفاوت چندانی با استفاده از متدهای رشته نداشته باشد؛ اما گاهی اوقات لازم است صحت‌سنجی‌های پیچیده‌ای (مانند چالش فوق) انجام شود که نمی‌توان با متدهای رشته، همه شرط‌ها را در رشته ورودی سنجید (حتی اگر بتوان این کار را انجام داد کد حاصل تمیز نخواهد بود)؛ در چنین مواقعی قدرت واقعی رجکس در مقابل متدهای رشته نمایان می‌شود.

ساختن الگو با رجکس بسیار ساده است، تقریبا همه‌ی حروف و اعداد به جای خودشان در الگو هستند (اگر بنویسیم abc‍، هر رشته‌ای که این سه حرف را پشت سر هم داشته باشد، با الگوی ما مطابقت دارد). اما بعضی علامت‌ها، کاربردهای خاصی در رجکس دارند، در زیر به معرفی این علامت‌ها می‌پردازیم:

علائم معنادار

علامت .

این علامت می‌تواند با همه‌ی کاراکترهای دیگر مطابقت کند. برای مثال رشته‌های زیر با الگوی .... مطابقت دارند:

```angular2html
"abcd"
"$^%#"
"1234"
```

علامت \
این علامت برای به کار بردن علامت‌های خاص به جای خودشان به کار می‌رود، مثلا اگر بخواهیم از علامت . استفاده کنیم به طوری که فقط با کاراکتر . مطابقت کند و با باقی کاراکترها مطابقت نداشته باشد، از این علامت استفاده می‌کنیم. گاهی این علامت به حروف خاص نیز معنای دیگری می‌بخشد، که جلوتر به آن پرداخته شده است.

برای مثال در نمونه زیر، الگوی ...\. با دو رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد، چون در انتهایش . ندارد:

```angular2html
"abc."
"123."
"defg"
```

علامت \d
این علامت با همه‌ی ارقام (کاراکترهای 0 تا 9) مطابقت دارد. به عنوان مثال الگوی .sd\d را در نظر بگیرید. این الگو با دو رشته اول مطابقت دارد ولی با رشته آخر مطابقت ندارد؛ چون کاراکتر آخر آن رقم نیست:

```angular2html
"asd7"
"6sd1"
"dsdg"
```

علامت \D
این علامت با همه‌ی کاراکترها به جز ارقام (کاراکترهای 0 تا 9) مطابقت دارد. به عنوان مثال الگوی .\D را در نظر بگیرید. این الگو با دو رشته اول مطابقت دارد ولی با رشته آخر مطابقت ندارد؛ چون کاراکتر آخر آن رقم است:

```
"bQ"
"6s"
"d5"
```

علامت \w
این علامت با همه‌ی حروف (کوچک و بزرگ) انگلیسی، ارقام (کاراکترهای 0 تا 9) و کاراکتر _ مطابقت دارد. برای مثال در نمونه زیر، الگوی \w\w با دو رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد:

```angular2html
"aB"
"6_"
"<?"
```

علامت \W
این علامت با همه‌ی کاراکترها به جز حروف (کوچک و بزرگ) انگلیسی، ارقام (کاراکترهای 0 تا 9) و کاراکتر _ مطابقت دارد. برای مثال در نمونه زیر، الگوی ..\W با دو رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد، چون در انتهایش کاراکتر عددی دارد:

```angular2html
"bQ@"
"6_!"
"d56"
```

علائم نمایانگر تعداد
علامت +
این علامت نشان‌دهنده‌ی این است که کاراکتر قبل از آن یک بار یا بیشتر تکرار شده باشد، و می‌تواند با باقی علامت‌های گفته شده هم ترکیب شود. برای مثال الگوی sx+ با دو رشته اول مطابقت دارد ولی با رشته آخر مطابقت ندارد:

```angular2html
"sx"
"sxxx"
"s"
```

علامت *
این علامت نشان‌دهنده‌ی این است که کاراکتر قبل از آن صفر بار یا بیشتر تکرار شده باشد، و می‌تواند با باقی علامت‌های گفته شده هم ترکیب شود. برای مثال الگوی sx* با هر سه رشته اول مطابقت دارد:


```angular2html
"sx"
"sxxx"
"s"
```

علامت ?
این علامت نشان‌دهنده‌ی این است که کاراکتر قبل از آن صفر بار یا یک بار آمده باشد، یعنی این کاراکتر می‌تواند در رشته باشد یا نباشد. این علامت هم می‌تواند با باقی علامت‌های گفته شده ترکیب شود.

برای مثال در نمونه زیر، الگوی d?e?f با چهار رشته‌ اول مطابقت دارد ولی با رشته آخر مطابقت ندارد، چون کاراکتر e دو بار تکرار شده است:

```angular2html
"df"
"ef"
"f"
"def"
"deef"
```

علامت ‍{}
هنگامی که یک کاراکتر به تعداد مشخصی در رشته‌مان تکرار شده باشد از این علامت استفاده می‌کنیم. مثلا a{23} یعنی حرف a ۲۳ بار پشت سر هم تکرار شده باشد، یا g{4,9} یعنی حرف g بین ۴ تا ۹ بار پشت سر هم تکرار شده باشد. هم‌چنین این علامت میتواند با همه‌ی علامت‌های تعریف شده ترکیب شود و به معنی تکرار الگوهای مشخص شده در آن علامت‌ها به تعداد مشخص است.

برای مثال در نمونه زیر، الگوی .{3,8} با سه رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد، چون طولش بین ۳ و ۸ نیست:

```angular2html
"@!#$"
"IAmAli"
"12345678"
"Hi"
```

علائم انتخاب و دسته‌بندی
علامت ‍[]
گاهی اوقات می‌خواهیم یک کاراکتر در رشته‌ی ما از بین تعداد خاصی کاراکتر باشد، در این موارد این گروه از کاراکترها را در بین علامت [] قرار می‌دهیم. دقت کنید این علامت فقط با یک حرف Match می‌شود. و اگر یک کاراکتر با کاراکترهای مشخص شده در بین این علامت مطابقت داشت، به سراغ کاراکتر الگوی نوشته شده بعد از بسته شدن این علامت می‌رود و مطابقت آن را چک می‌کند.

برای مثال در نمونه زیر، الگوی [abc][def][ghi] با دو رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد، چون کاراکترهای دوم و سوم به دسته‌های مشخص شده تعلق ندارند:

```angular2html
"beg"
"cdi"
"abc"
```

همچنین برای مشخص کردن گروهی از کاراکترها که بین کاراکترهای خاصی قرار دارند حرف شروع و حرف پایان را با - جدا می‌کنیم. مثلا [H-M] نشان دهنده‌ی تمام حروف بین H و M، با احتساب خود این دو حرف است؛ یعنی [H-M] معادل [HIJKLM] است.

برای مثال در نمونه زیر، الگوی [i-p] با سه رشته‌ اول مطابقت دارد ولی با رشته آخر مطابقت ندارد، چون ‍‍x بین کاراکترهای ‍‍i و p قرار ندارد:

```angular2html
"o"
"i"
"p"
"x"
```

همچنین با اضافه کردن کاراکتر ^ به ابتدای علامت []، اگر کاراکتری برابر با کاراکترهای درون این علامت باشد آن کاراکتر با الگو مطابقت نمی‌کند. برای مثال در نمونه زیر، الگوی abc[^def] ‍‍ با دو رشته‌ اول مطابقت ندارد؛ ولی با آخری مطابقت دارد، چون در انتهایش یکی از کاراکترهای d یا e یا f نیامده است:

```angular2html
"abcd"
"abcf"
"abck"
```

علامت ()
این علامت برای جدا کردن گروهی از کاراکترها در الگو به کار می‌آید، مخصوصا وقتی که می‌خواهیم از علامت‌های شمارشی برای گروهی از کاراکترها به جای یک کاراکتر استفاده کنیم.

برای مثال در نمونه زیر، الگوی "(abc)+" با دو رشته‌ اول مطابقت دارد ولی با آخری مطابقت ندارد، چون در آن کاراکتر d به کار رفته است.

```angular2html
"abcabcabc"
"abc"
"abdccccc"
```

علائم شروع و پایان
علامت ^
اگر این علامت اول الگویی به کار رود، به این معنی است که رشته باید با الگو شروع شود. مثلا الگوی ^Mah.+ با دو رشته اول تطابق دارد ولی با رشته سوم تطابق ندارد، چون با Mah شروع نشده است.

```angular2html
"Mahtab"
"Mahan"
"TabMah"
```

علامت ‍$
اگر این علامت آخر الگویی به کار رود، به این معنی است که رشته باید با الگو پایان یابد. مثلا الگوی .+pour$ با دو رشته اول تطابق دارد ولی با رشته سوم تطابق ندارد، چون با pour پایان نیافته است.

```
"َAlipour"
"Rashidpour"
"pourMansour"
```

