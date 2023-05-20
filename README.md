# lazy-gost
اسکریپت lazy gost برای ایجاد سریع تانلینگ گاست با متد forward + tls

قدم اول

دانلود فایل های مورد نیاز و تنظیمات اولیه (در هردو سرور اجرا شود) : 
```
apt install git curl socat -y
git clone https://github.com/omid-j-d/lazy-gost
cp /root/lazy-gost/gost.sh /root/
chmod +x gost.sh
```


این دستور فقط در سرور خارج اجرا شود 
```
cp /root/lazy-gost/ssl.sh /root/
chmod +x ssl.sh
```


قدم دوم

دریافت گواهی ssl ( این دستور را فقط در سرور خارج اجرا کنید) 
```
bash ssl.sh
```
بعد از اجرا اسکریپت در گزینه اول ادرس ساب دامین سرور خارجتون رو وارد کنید و در بخش دوم ادرس ایمیل خود را وارد کنید 

قدم سوم 

نصب gost بر روی هر دو سرور خارج و ایران
```
bash gost.sh
```
بعد از اجرای دستور در صورتی که در سرور خارج اسکریپت را اجرا میکنید o و در صورتی که در سرور داخل ایران اجرا میکنید i را انتخاب کنید 
در گزینه دوم پورت کانفیگ خود را وارد کنید
در گزینه سوم پورت تانل را انتخاب کنید (ترجیحا 443 یا 2056)
در سرور ایران یک گزینه بیشتر دارد که باید در اون ادرس سابدامین سرور خارجتون رو تایپ کنید
در اخر هم یک عدد برای سرویس گاست انتخاب کنید (این مورد برای تانل از چند سرور به یک سرور متفاوت میتواند مفید باشد)


طریقه مشاهده وضعیت سرویس:

برای مشاهده وضعیت سرویس میتوانید از دستور زیر استفاده کنید
``` systemctl status gost{service_number} ```

کافیست در دستور بالا به جای {service_number} عددی که در هنگام ایجاد سرویس وارده کرده اید را جای گذاری کنید 

پیشنهاد: اگر از termius استفاده میکنید میتوانید یک snippet ایجاد کنید و تمامی کد هارا در یک بسته قرار دهید تا با یک کلیک تمامی دستورات اجرا شود




