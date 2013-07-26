بسم الله الرحمن الرحيم

ar-php extension is a wrapper extension to the great library [Ar-PHP](http://www.ar-php.org/) which is developed by [Khaled Al-Sham'aa](http://www.ar-php.org/about-php-arabic.html)

> Note: using the library directly as a vendor without using an extension is better but the problem is that we should modify a file in the library to make it work and i preferred not to touch the lib files. (maybe i will make a wiki to explain how)

## Library Features
* [Arabic text auto summarization](http://www.ar-php.org/ar-example-AutoSummarize-php-arabic.html)
* [Advanced Arabic search (stem based)](http://www.ar-php.org/Examples/ArQuery-php-arabic.html)
* [Render Arabic text (PDF, GD, SWF)](http://www.ar-php.org/Glyphs-example-php-arabic.html)
* [Present dates in Arabic or Hijri](http://www.ar-php.org/ar-example-Date-php-arabic.html)
* [Convert Hijri date into Unix timestamp](http://www.ar-php.org/ar-example-Mktime-php-arabic.html)
* [Parse Arabic textual datetime into timestamp](http://www.ar-php.org/ar-example-StrToTime-php-arabic.html)
* [Transliterate English words in Arabic](http://www.ar-php.org/ar-example-Transliteration-php-arabic.html)
* [Transliterate Arabic words in English](http://www.ar-php.org/example-EnTransliteration-php-arabic.html)
* [Spell numbers in Arabic idiom](http://www.ar-php.org/ar-example-Numbers-php-arabic.html)
* [Phonetically alike Arabic words](http://www.ar-php.org/ar-example-Soundex-php-arabic.html)
* [Arabic character set converter](http://www.ar-php.org/ar-example-CharsetC-php-arabic.html)
* [Arabic character set auto detection](http://www.ar-php.org/ar-example-CharsetD-php-arabic.html)
* [Identify Arabic in multi language documents](http://www.ar-php.org/ar-example-Identifier-php-arabic.html)
* [Identify names & places in Arabic text](http://www.ar-php.org/ar-example-WordTag-php-arabic.html)
* [Guess gender of Arabic names](http://www.ar-php.org/ar-example-Gender-php-arabic.html)
* [Convert keyboard language programmatically](http://www.ar-php.org/ar-example-KeySwap-php-arabic.html)
* [Calculate the time of Muslim prayer](http://www.ar-php.org/ar-example-Salat-php-arabic.html)
* [Compress string using Huffman-like coding](http://www.ar-php.org/ar-example-CompressStr-php-arabic.html)
* [Standardize Arabic text](http://www.ar-php.org/ar-example-Standard-php-arabic.html)
* [Arabic stemmer](http://www.ar-php.org/ar-example-Stemmer-php-arabic.html)
* [Arabic Cities List](http://www.ar-php.org/Examples/City-php-arabic.html)
* [Informations about Arabic countries](http://www.ar-php.org/Examples/Info-php-arabic.html)
* [Arabic text normalisation](http://www.ar-php.org/Examples/ArNormalise-php-arabic.html)

##Requirements

This extension developed using Yii version 1.1.14 RC but it should work in all Yii versions.

##Installation

1) download and extract the extension into extensions folder: protected/extensions/ar-php

2) download the library from [here](http://sourceforge.net/projects/ar-php/files/ar-php/).

3) extract the library into **Your-Application-Folder/vendor**   ,   example:
~~~
[php]
webroot/my-yii-project-folder/protected/vendor/I18N
~~~

4) configure the component by updating config/main.php as follow:
~~~
[php]
'import'=>array(
	...
	'ext.ar-php.*'
	...
),

'components'=>array(
	...
	'I18N_Arabic'=>array(
		'class'=>'EArPHP',
		'libPath'=>'application.vendor.I18N' // optional since it is the default value
	),
	...
),
~~~

##Usage

I tried to make the usage of the extension as easy as i can, in the [official website](http://www.ar-php.org/) there is an example of usage and it **will not work for our extension** but it will help us to compare between them, which is:
~~~
[php]
include('I18N/Arabic.php');
$obj = new I18N_Arabic('Numbers');

echo $obj->int2str(1975); // ألف و تسعمئة و خمس و سبعون
~~~

to generate the same example using ar-php extension use:
~~~
[php]
$obj = Yii::app()->I18N_Arabic->Numbers;

echo $obj->int2str(1975); // ألف و تسعمئة و خمس و سبعون 
~~~

or simply:
~~~
[php]
echo Yii::app()->I18N_Arabic->Numbers->int2str(1975); // ألف و تسعمئة و خمس و سبعون 
~~~

the same concept apply for all other features, and you can follow any feature link above for documentation and usage example.

##Resources
* code: [github](https://github.com/muaid/arphp.git)
* official Library: [Ar-PHP](http://www.ar-php.org/)
