
gd-text-farsi (customized for Persian Language)
=======

###Basic usage example
```php
<?php

use GDText\Box;
use GDText\Color;

$im = imagecreatetruecolor(500, 500);
$backgroundColor = imagecolorallocate($im, 0, 18, 64);
imagefill($im, 0, 0, $backgroundColor);

$box = new Box($im);
$box->setFontFace(__DIR__.'/Franchise-Bold-hinted.ttf'); // http://www.dafont.com/franchise.font
$box->setFontColor(new Color(255, 75, 140));
$box->setTextShadow(new Color(0, 0, 0, 50), 2, 2);
$box->setFontSize(40);
$box->setBox(20, 20, 460, 460);
$box->setTextAlign('left', 'top');
$box->draw("Franchise\nBold");

$box = new Box($im);
$box->setFontFace(__DIR__.'/Pacifico.ttf'); // http://www.dafont.com/pacifico.font
$box->setFontSize(80);
$box->setFontColor(new Color(255, 255, 255));
$box->setTextShadow(new Color(0, 0, 0, 50), 0, -2);
$box->setBox(20, 20, 460, 460);
$box->setTextAlign('center', 'center');
$box->draw("Pacifico");

$box = new Box($im);
$box->setFontFace(__DIR__.'/Prisma.otf'); // http://www.dafont.com/prisma.font
$box->setFontSize(70);
$box->setFontColor(new Color(148, 212, 1));
$box->setTextShadow(new Color(0, 0, 0, 50), 0, -2);
$box->setBox(20, 20, 460, 460);
$box->setTextAlign('right', 'bottom');
$box->draw("Prisma");

header("Content-type: image/png");
imagepng($im);
```

Example output:

![fonts example](examples/fonts.png)

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
$box->setFontSize(8);
$box->setLineHeight(1.5);
//$box->enableDebug();
$box->setBox(20, 20, 460, 460);
$box->setTextAlign('left', 'top');

$gd = new FarsiGD();

$text = 'امروز آمدیم تا دانلود نسخه جدید خانواده فونت بی نازنین b nazanin را در اختیار کاربران محترم ایران فونت قرار بدهیم. خانواده این فونت که ما آن را نازنین پلاس میخوانیم شامل نازنین معمولی(Regular)، نازنین ضخیم (Bold) و نازنین سیاه (Black) است. این فونت از تمام حروف فارسی، عربی و انگلیسی به خوبی پشتیبانی می‌کند.  با این فونت با راحتی می توانید هم حروف عربی (حروف ة، ی، ک و...) را تایپ کنید و هم حروف انگلیسی را. این فونت در استفاده شما در کارهای مذهبی و البته کتب درسی و آموزشی مختلف می تواند بسیار راه گشا باشد. در صورت مشاهده هر گونه ایراد و یا ضعف در فونت خواهشمند است ما را در جریان قرار گذارید تا در سریع ترین زمان اشکالات اصلاح و رفع گردند. با تشکر.  منبع: Irfont.ir';

$text = $gd->persianText($text, 'fa', 'normal');
 
$box->draw($text);

header("Content-type: image/png;");
imagepng($im, null, 9, PNG_ALL_FILTERS);
```

![line height example](examples/persian.png)

*line height demo*


![align example](examples/alignment.gif)

*text alignment demo*

![debug example](examples/debug.png)

*debug mode enabled demo*
