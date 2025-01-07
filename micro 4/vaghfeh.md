## نام ازمایش
استفاده از وقفه در آردوینو

## تجهیزات مورد نیاز:
   * آردوینو uno
   * سیم

   * 
## کد آزمایش:

volatile bool led_state = LOW;

void setup()

{

pinMode(13, OUTPUT);

pinMode(2, INPUT_PULLUP);

attachInterrupt(digitalPinToInterrupt(2), blink, FALLING);

}

void loop()

{

digitalWrite(13, led_state);

}

void blink() {

led_state = !led_state; }
## توضیحات کد

    تعریف متغیرها متغیر led_state به عنوان متغیر وضعیت LED تعریف شده که مقدار اولیه آن LOW است.

    تابع setup پین 13 به عنوان خروجی برای LED تنظیم شده است. پین 2 به عنوان ورودی با مقاومت پول‌داون داخلی (INPUT_PULLUP) تنظیم شده است. وقفه‌ای تعریف شده که هنگام تشخیص لبه نزولی روی پین 2، تابع blink اجرا شود.

    تابع loop مقدار وضعیت LED (led_state) روی پین 13 نوشته می‌شود که باعث روشن یا خاموش شدن LED می‌شود.

    تابع وقفه (ISR) در این تابع وضعیت LED تغییر می‌کند (روشن به خاموش و برعکس).

## توضیحات سخت افزاری مدار

پایه کاتد LED به زمین (GND) و پایه آند LED به پین 13 متصل شود.
کلید فشاری بین پین 2 و زمین (GND) متصل گردد.
از تنظیمات پول‌داون داخلی آردوینو برای پایدارسازی سیگنال استفاده شده است.


## تصویر مدار
![توضیح تصویر](https://github.com/Rahel12384/Microprocessor-7/blob/main/micro%204/IMG_20250107_155534_494.jpg)


