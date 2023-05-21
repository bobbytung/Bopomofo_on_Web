# Bopomofo Layout with OpenType features

For English readers, If you are i18n Engineer, Input Method developer, and Font Engineer.
In this repo we provide a [detailed document](https://github.com/cmex-30/Bopomofo_on_Web/blob/master/BOPOMOFO%20TYPOGRAPHY.pdf) as a reference included:

1. Bopomofo and Bopomofo extension(for Taiwanese and Hakka) layout samples.
2. Code points designated to use for input method.
3. Code points sequence for each tone marks.
4. OpenType features we want to use for Bopomofo layout.
5. Sample font that use features and GSUB function for layout adjestment.

In this document, we use registered OpenType feature and applied GSUB way that is working on modern font engine like HarfBuzz and CoreText. So that the sample font is immediately usable for web content that is well-marked with ruby tag with correct code points sequence.

Feel Free to use [the font](https://github.com/cmex-30/Bopomofo_on_Web/tree/master/font) under Open Font License. If you have any suggestion and feedback, please add issue in this repo.
Glad to know your usage on Web content and applications, please let me know: [bobbytung](mailto:bobbytung@wanderer,tw).

-----

# 注音符號數位化顯示計畫

本計畫主要目的是：尋求讓中文注音符號，在Web以及其他數位環境下，能以更符合數位化需求的方式呈現的方法。

## 傳統的做法：注音字型

![](https://github.com/bobbytung/Bopomofo_on_Web/blob/master/images/bopomofofont.jpg)
（攝於國語日報社展示櫥窗）

活字印刷時代，注音符號於印刷上使用將漢字及注音符號鑄於一體銅膜來製作鉛字。若一字有多種讀音，則鑄造多種鉛字備用。

當轉到電腦字體時代時，依然保持相同的作法。將注音符號與漢字造於電腦字型的同一個字符（Glyph）中，並且按照教育部[一字多音審訂表](https://github.com/g0v/moedict-data-csld/blob/master/國語一字多音審訂表2012.csv)造成多組字型檔案。注音字型由於能夠確實重現[國語注音符號手冊](http://language.moe.gov.tw/001/Upload/files/site_content/M0001/juyin/index.html)上對印刷排版注音符號比例的需求，而成為主流的數位排版印刷採用的方式。

## 為什麼不建議使用注音字型

但注音字型在廣泛應用於數位環境時，會遇到多種問題，如：

- 缺乏語義資訊

- 缺少無障礙支援

- 缺少擴充性

（詳細請讀「[從注音字體談資訊設計](https://medium.com/@bobtung/從注音字體談資訊設計-14cb09ff9d52)」）故以並不適宜用於數位內容的顯示。

-----

## 注音符號使用的字元

### 國語注音符號 | Mandarin Bopomofo Symbols

#### 一般注音符號 | General Bopomofo Symbols

#### 聲調符號 | Tone Marks

聲調 | 符號 | Unicode代碼 | Unicode名稱
------- | ------- | ------- | -------
輕聲 | ˙ | U+02D9 | DOT ABOVE
平聲 | ˉ | U+02C9 | MODIFIER LETTER MACRON[^1]
二聲 | ˊ | U+02CA | MODIFIER LETTER ACUTE ACCENT
三聲 | ˇ | U+02C7 | CARON
四聲 | ˋ | U+02CB | MODIFIER LETTER GRAVE ACCENT

[^1]: 雖有文字編碼，但僅用於輸入法選字對應等，不會用於顯示。

#### 注音符號 | Bopomofo Sympol

符號 | Unicode代碼 | Unicode名稱
------ | ------- | -------
ㄅ	 | 	U+3105 | BOPOMOFO LETTER B
ㄆ	 | 	U+3106 | BOPOMOFO LETTER P
ㄇ	 | 	U+3107 | BOPOMOFO LETTER M
ㄈ	 | 	U+3108 | BOPOMOFO LETTER F
ㄉ	 | 	U+3109 | BOPOMOFO LETTER D 
ㄊ	 | 	U+310A | BOPOMOFO LETTER T
ㄋ	 | 	U+310B | BOPOMOFO LETTER N
ㄌ	 | 	U+310C | BOPOMOFO LETTER L 
ㄍ	 | 	U+310D | BOPOMOFO LETTER G
ㄎ	 | 	U+310E | BOPOMOFO LETTER K
ㄏ	 | 	U+310F | BOPOMOFO LETTER H
ㄐ	 | 	U+3110 | BOPOMOFO LETTER J
ㄑ	 | 	U+3111 | BOPOMOFO LETTER Q
ㄒ	 | 	U+3112 | BOPOMOFO LETTER X
ㄓ	 | 	U+3113 | BOPOMOFO LETTER ZH
ㄔ	 | 	U+3114 | BOPOMOFO LETTER CH
ㄕ	 | 	U+3115 | BOPOMOFO LETTER SH
ㄖ	 | 	U+3116 | BOPOMOFO LETTER R
ㄗ	 | 	U+3117 | BOPOMOFO LETTER Z
ㄘ	 | 	U+3118 | BOPOMOFO LETTER C
ㄙ	 | 	U+3119 | BOPOMOFO LETTER S
ㄚ	 | 	U+311A | BOPOMOFO LETTER A
ㄛ	 | 	U+311B | BOPOMOFO LETTER O
ㄜ	 | 	U+311C | BOPOMOFO LETTER E
ㄝ	 | 	U+311D | BOPOMOFO LETTER EH
ㄞ	 | 	U+311E | BOPOMOFO LETTER AI
ㄟ	 | 	U+311F | BOPOMOFO LETTER EI
ㄠ	 | 	U+3120 | BOPOMOFO LETTER AU
ㄡ	 | 	U+3121 | BOPOMOFO LETTER OU
ㄢ	 | 	U+3122 | BOPOMOFO LETTER AN
ㄣ	 | 	U+3123 | BOPOMOFO LETTER EN
ㄤ	 | 	U+3124 | BOPOMOFO LETTER ANG
ㄥ	 | 	U+3125 | BOPOMOFO LETTER ENG
ㄦ	 | 	U+3126 | BOPOMOFO LETTER ER
ㄧ	 | 	U+3127 | BOPOMOFO LETTER I
ㄨ	 | 	U+3128 | BOPOMOFO LETTER U
ㄩ	 | 	U+3129 | BOPOMOFO LETTER IU

#### 罕用注音符號 Rare Use Bopomofo Symbol

符號 | Unicode代碼 | Unicode名稱
------ | ------- | -------
ㄪ | U+312A | BOPOMOFO LETTER V
ㄫ | U+312B | BOPOMOFO LETTER NG[^2]
ㄬ | U+312C | BOPOMOFO LETTER GN
ㄭ | U+312D | BOPOMOFO LETTER IH

[^2]: U+312Bㄫ同時為方音注音常用符號

## 注音符號延伸 | Bopomofo Extended

### 方音注音符號 | Bopomofo Symbols for Dialect

符號 | Unicode代碼 | Unicode名稱
------- | ------- | -------
ㄫ | U+312B | BOPOMOFO LETTER NG
ㆠ | U+31A0 | BOPOMOFO LETTER BU	
ㆡ | U+31A1 | BOPOMOFO LETTER ZI	
ㆢ | U+31A2 | BOPOMOFO LETTER JI	
ㆣ | U+31A3 | BOPOMOFO LETTER GU	
ㆤ | U+31A4 | BOPOMOFO LETTER EE
ㆥ | U+31A5 | BOPOMOFO LETTER ENN	
ㆦ | U+31A6 | BOPOMOFO LETTER OO	
ㆧ | U+31A7 | BOPOMOFO LETTER ONN	
ㆩ | U+31A9 | BOPOMOFO LETTER ANN	
ㆪ | U+31AA | BOPOMOFO LETTER INN	
ㆫ | U+31AB | BOPOMOFO LETTER UNN
ㆬ | U+31AC | BOPOMOFO LETTER IM
ㆭ | U+31AD | BOPOMOFO LETTER NGG
ㆮ | U+31AE | BOPOMOFO LETTER AINN	
ㆯ | U+31AF | BOPOMOFO LETTER AUNN
ㆰ | U+31B0 | BOPOMOFO LETTER AM
ㆱ | U+31B1 | BOPOMOFO LETTER OM	
ㆲ | U+31B2 | BOPOMOFO LETTER ONG

#### 方音聲調符號 | Tone Mark Symbol for Dialect

符號 | Unicode代碼 | Unicode名稱
------- | ------- | -------
˪ | U+02EA | MODIFIER LETTER YIN DEPARTING TONE MARK
˫ | U+02EB | MODIFIER LETTER YANG DEPARTING TONE MARK
ㆴ | U+31B4 | BOPOMOFO FINAL LETTER P
ㆵ | U+31B5 | BOPOMOFO FINAL LETTER T
ㆷ | U+31B7 | BOPOMOFO FINAL LETTER H
<sub>ㄍ</sub> | U+31BB | BOPOMOFO FINAL LETTER G [^3]

[^3]: U+31BB於2018年6月提交至ISO/IEC JTC1 WG2，將於未來加入Unicode標準之中，詳細請見[提案文件](https://unicode.org/wg2/docs/n4980_Proposal-Bopomofo_Extended.pdf)。

-----

## Web使用HTML Ruby標註

早在2001年網頁標準的測定中，就已經將注音符號納入[Ruby規範](https://www.w3.org/TR/2001/WD-css3-ruby-20010216/)之中，但標註方式以及顯示方式，直到2012年HTML 5規格確立以後才底定。

### 注音符號標注方式

請參照[W3C HTML Ruby Markup Extensions](https://www.w3.org/TR/html-ruby-extensions/)以及[W3C i18n Ruby Markup](https://www.w3.org/International/articles/ruby/markup)。

原則上在HTML中標註方式如下，每一字使用Mono Ruby方式標注：

- 二三四聲置於注音符號之後

```<ruby>我<rt>ㄨㄛˇ</rt></ruby>```

- 輕聲置於注音符號之前

```<ruby>呢<rt>˙ㄋㄜ</rt></ruby>```

另外，[Tabular ruby markup model](https://www.w3.org/International/articles/ruby/markup#tabular)目前瀏覽器支援性較低，不建議使用，標注方式如下：

```<ruby><rb>你<rb>好<rb>嗎<rt>ㄋㄧˇ<rt>ㄏㄠˇ<rt>˙ㄇㄚ</ruby>```

### 與注音符號相關的CSS語法

請參照[CSS Ruby Layout Module Level 1](https://www.w3.org/TR/css-ruby-1/)。

基本上需注意點如下：

- 在```<rt>```元素內指定Ruby文字尺寸，建議為基字的30%

```rt {font-size: 30%;}```

- 當要將注音於橫排時至於基字右側時，使用```ruby-position: inter-character;```

- 注音直排時，由於目前Unicode中調號於直排中（請見[UTR#50](http://www.unicode.org/reports/tr50/tr50-19.html)）並非直立文字，所以需要強制直立，如：

```rt {text-orientation: upright;}```

- 注音排列建議使其與基字居中對齊

``` rt {text-align: center;}```

### 使用注音調號字體

在CSS中宣告本專案提供的字體檔案即可

    @font-face {
     font-family: BopomofoPro;
     src: url("BopomofoPro-Regular.ttf");
    }
    body {
     font-family: BopomofoPro, serif;
    }

### 標注注意事項

- Chrome的Ruby接受對齊語法，所以需要在rt元素中加入text-align: center讓注音符號居中對齊。
- 注音字體指定若僅套用在ruby標籤時，會因為Fallback在Chrome上加寬與被標註漢字間的距離，所以須在body使用font-family: BopomofoGPOS, serif 來調整。
- 由於BopomofoGPOS中包含英文字，建議在 font-family: BopomofoPro; 前指定其他英文字體來取代。

-----

## 注音調號字體OpenType規格

本字體使用OpenType的功能來調整調號位置，詳細說明如下：

- 當基字橫排，注音置放於基字上方時，調號使用`ruby`來調整位置
- 當基字橫排或直排，注音直立置放於基字右方時，將調號更換為組合符號（如下表）後，使用GPOS`vert`來調整座標位置。

聲調 | Unicode代碼 | 取代符號 | Unicode代碼
------- | ------- | ------- | -------
ˊ | U+02CA |  ́ | U+0301
ˇ | U+02C7 |  ̌ | U+030C
ˋ | U+02CB |  ̀ | U+0300

詳細請見[完整的Font Feature規格](https://github.com/bobbytung/Bopomofo_on_Web/blob/master/font/feature)。

### 字型授權方式

測試字體（BopomofoGPOS.otf）使用[SIL Open Font License (OFL-1.1)授權](https://github.com/bobbytung/Bopomofo_on_Web/blob/master/font_license.html)。

-----

## 注音符號版面呈現測試

注音符號測試案例有七，皆使用注音調號字體來作為顯示：

1. [基字橫排，注音置於基字上方](https://bobbytung.github.io/Bopomofo_on_Web/case01/index.html)
2. [基字直排，注音置於基字右方](https://bobbytung.github.io/Bopomofo_on_Web/case02/index.html)
3. [基字橫排，注音使用ruby-position: inter-character置於基字右方](https://bobbytung.github.io/Bopomofo_on_Web/case03/index.html)
4. [注音出現於內文](https://bobbytung.github.io/Bopomofo_on_Web/case04/index.html)
5. [基字直排，注音置於基字右方（舊版）](https://bobbytung.github.io/Bopomofo_on_Web/case05/index.html)
6. [基字直排，注音置於基字右方（使用`vert`的更新版）](https://bobbytung.github.io/Bopomofo_on_Web/case06/index.html)
7. [五種狀況的組合顯示](https://bobbytung.github.io/Bopomofo_on_Web/case07/index.html)
8. [五種狀況的組合顯示，使用思源黑體2.000版](https://bobbytung.github.io/Bopomofo_on_Web/case08/index.html)

-----

## 其他測試與相容性

相容於[LibreOffice](https://github.com/harfbuzz/harfbuzz/issues/532#issuecomment-375284467)

-----

## 更新事項

- 2018/3/22更新字體
詢問Adobe Dr.Ken Lunde，建議使用OpenType GPOS 'vert'，But提供新版字體，追加Case 6。

- 2018/8/13更新字體授權

- 2018/8/19更新字體規格

- 2018/9/27更新Case 8，使用Dr.Ken Lunde提供的思源黑體2.000測試版

- 2018/11/20更新Case 8，CSS指定思源黑體2.000版，請於[這裡下載安裝/更新](https://github.com/adobe-fonts/source-han-sans/releases/download/2.000R/SourceHanSans.ttc)
