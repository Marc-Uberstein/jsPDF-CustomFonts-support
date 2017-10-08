# jsPDF-CustomFonts-support

JsPDF is an open source that loads JavaScript in an HTML5 environment and creates a pdf document.

The current version does not support Custom Fonts. I will try to implement this feature.


## Current Version

Version 0.2

[jsPDF libary](http://parall.ax/products/jspdf)

I do not claim to be the author of the jsPDF library, this code simply adds preliminary custom fonts support.

## Version History

0.1 Initial proof of concept

## Getting Started

This document will walk you through the basics of jsPDF and will show you how to create PDF files in the browser.

To begin with the default configuration, you should include six files:

* **jspdf.js**,
* **FileSaver.js**,
* **split_text_to_size.js**,
* **standard_fonts_metrics.js**,
* **customfonts.js**,
* **vfs_fonts.js** - default font definition (it contains 8 Fonts, you can however [use custom fonts instead](https://www.giftofspeed.com/base64-encoder/))

```html
<!DOCTYPE html>
<html>

<head>
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <title>jsPDF customfonts example</title>
    <script language="javascript" type="text/javascript" src="./plugins/FileSaver.js"></script>
    <script language="javascript" type="text/javascript" src="./plugins/split_text_to_size.js"></script>
    <script language="javascript" type="text/javascript" src="./plugins/standard_fonts_metrics.js"></script>
    <script language="javascript" type="text/javascript" src="jspdf.js"></script>
    <script language="javascript" type="text/javascript" src="customfonts.js"></script>
    <script language="javascript" type="text/javascript" src="vfs_fonts.js"></script>
</head>
<body>
...
```

## addCustomFonts Method

```javascript
doc.addFont(fileName, fontName, fontStyle);


```

## Example Code

```javascript
var doc = new jsPDF();


doc.addFont('HMKMMAG.TTF', 'MagicR', 'normal');
doc.addFont('gothic.ttf', 'LiLing', 'normal');
// doc.addFont('GuardianSans.ttf', 'GuardianSans', 'normal');


doc.setFont('MagicR');
doc.text(15, 15, '안녕하세요 저는 jsPDF의 custom font 개발자 이관형입니다.');

doc.setFont('LiLing');
doc.text(15, 30, 'こんにちは。あなたの名前は何ですか？');

doc.save('jspdf.pdf');

```

## License
MIT
