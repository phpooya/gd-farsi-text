
gd-text-farsi 
=======
(customized for Persian Language)
###Multilined text

```php
<?php

use GDText\Box;
use GDText\Color;

$im = imagecreatetruecolor(500, 500);
$backgroundColor = imagecolorallocate($im, 0, 18, 64);
imagefill($im, 0, 0, $backgroundColor);

$box = new Box($im);
$box->setFontFace('FarsiFont/B Nazanin.ttf'); // http://www.dafont.com/minecraftia.font
$box->setFontColor(new Color(255, 75, 140));
$box->setTextShadow(new Color(0, 0, 0, 50), 2, 2);
$box->setFontSize(23);
$box->setLineHeight(1.5);
//$box->enableDebug();
$box->setBox(20, 20, 460, 460);
$box->setTextAlign('right', 'top');

$gd = new FarsiGD();

$text = 'امروز آمدیم تا دانلود نسخه جدید خانواده فونت بی نازنین b nazanin را در اختیار کاربران محترم ایران فونت قرار بدهیم. خانواده این فونت که ما آن را نازنین پلاس میخوانیم شامل نازنین معمولی(Regular)، نازنین ضخیم (Bold) و نازنین سیاه (Black) است. این فونت از تمام حروف فارسی، عربی و انگلیسی به خوبی پشتیبانی می‌کند.  با این فونت با راحتی می توانید هم حروف عربی (حروف ة، ی، ک و...) را تایپ کنید و هم حروف انگلیسی را. این فونت در استفاده شما در کارهای مذهبی و البته کتب درسی و آموزشی مختلف می تواند بسیار راه گشا باشد. در صورت مشاهده هر گونه ایراد و یا ضعف در فونت خواهشمند است ما را در جریان قرار گذارید تا در سریع ترین زمان اشکالات اصلاح و رفع گردند. با تشکر.  منبع: Irfont.ir';

$text = $gd->persianText($text, 'fa', 'normal');
 
$box->draw($text);

header("Content-type: image/png;");
imagepng($im, null, 9, PNG_ALL_FILTERS);
```

![line height example](examples/persian.png)

