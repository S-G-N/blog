---
title: workNote
date: 2016-11-03 14:37:52
tags:
---

# 前端部署
1. 在代码服务器上用git用户名登录
```bash
su git
password:client
```
2. 进入目录/home/git/local/
```bash
./package.sh -v 0.9.4
```
# 研发自测环境node后台更新
```bash
211.100.75.219:26333
dev q1w2e3r4t5 client
/var/www/hisense/hisntvtestsrv/
git pull
```
<!-- more -->
## 项目仓库：

## Hisense
海信二期：ssh://git@211.100.75.201:26333/hisntv.git
海信三期：ssh://git@211.100.75.201:26333/hisntv2.git

## Manager
manager：ssh://git@211.100.75.201:26333/stbmgr.git 
manager前端：ssh://git@211.100.75.201:26333/stbmgrfrnt.git

## STB Interface
ssh://git@211.100.75.201:26333/stbiftool.git


## SVN
https://192.168.10.55/svn/TV_dev_report
https://192.168.10.55/svn/project_management/document
https://192.168.10.55/svn/italkTV_system/server_client_interface/hisence2.0
https://192.168.10.55/svn/webtv/hisense/pub/release/部署


### 海信应用安装
0.连接串口。
1.创建对应目录
```bash
mkdir -p /3rd_rw/appdata/launcher
mkdir -p /3rd_rw/launcher/img/appsicon
```
2.进入U盘对应目录(在上面窗口进hisn...文件夹)
```bash
cd /mnt
cd /usb/sdxx/
```
3.在U盘内执行，拷贝文件
```bash
cp italkbbtest.json /3rd_rw/appdata/launcher/Appinfo.json
cp dficon.png /3rd_rw/launcher/img/appsicon/dficon.png
```
4.保存(多次保存)
```
sync
```
5.重启
```
reboot
```
# 浏览器奇葩问题
1. 海信电视FHD平台burl事件触发两次
   parseInt解析08、09为0
2. video 元素的父容器影响视频播放品质，如图：
3. 对于视频的缩放只能操作视频的宽video.height()，高度是无法操控的，设置宽度后视频高度会按源比例缩放。使用object-fit：fill属性后UHD可达到全屏铺满整屏（因为是opera12.16，opera12.17及更早版本中使用的是Presto内核，这种内核特点就是渲染速度快，但兼容性差，需要加-o-前缀），而new UHD板子使用的是Blink内核（opera15及以后版本采用了Google的Blink内核）使用此属性并未将视频铺满整个屏幕，依然是原始比例伸缩，后来我发现小屏幕时能铺满，全屏时就不能铺满，全屏和小屏的区别可能就是影响此属性在newUHD（Blink内核）上的原因，试着给video加了边框，查看是否因为video元素没全屏铺满，并添加box-sixing:border-box才能全屏铺满，
![兼容性](/images/object-fit1.png)

4. user agent stylesheet是浏览器内置样式，当网页没有指定样式时，浏览器会以自己的默认样式进行渲染，不同的浏览器默认样式也不同，默认样式优先级最低，当网页添加了自己的样式时默认样式就会被覆盖。
```html
HTML转义字符大全
ISO Latin-1字符集:
&#09; — 制表符Horizontal tab
&#10; — 换行Line feed
&#13; — 回车Carriage Return
&#32; — Space
! &#33; — 惊叹号Exclamation mark
” &#34; &quot; 双引号Quotation mark
# &#35; — 数字标志Number sign
$ &#36; — 美元标志Dollar sign
% &#37; — 百分号Percent sign
& &#38; &amp; Ampersand
‘ &#39; — 单引号Apostrophe
( &#40; — 小括号左边部分Left parenthesis
) &#41; — 小括号右边部分Right parenthesis
* &#42; — 星号Asterisk
+ &#43; — 加号Plus sign
, &#44; — 逗号Comma
- &#45; — 连字号Hyphen
. &#46; — 句号Period (fullstop)
/ &#47; — 斜杠Solidus (slash)
0 &#48; — 数字0 Digit 0
1 &#49; — 数字1 Digit 1
2 &#50; — 数字2 Digit 2
3 &#51; — 数字3 Digit 3
4 &#52; — 数字4 Digit 4
5 &#53; — 数字5 Digit 5
6 &#54; — 数字6 Digit 6
7 &#55; — 数字7 Digit 7
8 &#56; — 数字8 Digit 8
9 &#57; — 数字9 Digit 9
: &#58; — 冒号Colon
; &#59; — 分号Semicolon
< &#60; &lt; 小于号Less than
= &#61; — 等于符号Equals sign
> &#62; &gt; 大于号Greater than
? &#63; — 问号Question mark
@ &#64; — Commercial at
A &#65; — 大写A Capital A
B &#66; — 大写B Capital B
C &#67; — 大写C Capital C
D &#68; — 大写D Capital D
E &#69; — 大写E Capital E
F &#70; — 大写F Capital F
G &#71; — 大写G Capital G
H &#72; — 大写H Capital H
I &#73; — 大写J Capital I
J &#74; — 大写K Capital J
K &#75; — 大写L Capital K
L &#76; — 大写K Capital L
M &#77; — 大写M Capital M
N &#78; — 大写N Capital N
O &#79; — 大写O Capital O
P &#80; — 大写P Capital P
Q &#81; — 大写Q Capital Q
R &#82; — 大写R Capital R
S &#83; — 大写S Capital S
T &#84; — 大写T Capital T
U &#85; — 大写U Capital U
V &#86; — 大写V Capital V
W &#87; — 大写W Capital W
X &#88; — 大写X Capital X
Y &#89; — 大写Y Capital Y
Z &#90; — 大写Z Capital Z
[ &#91; --- 中括号左边部分Left square bracket
\ &#92; --- 反斜杠Reverse solidus (backslash)
] &#93; — 中括号右边部分Right square bracket
^ &#94; — Caret
_ &#95; — 下划线Horizontal bar (underscore)
` &#96; — 尖重音符Acute accent
a &#97; — 小写a Small a
b &#98; — 小写b Small b
c &#99; — 小写c Small c
d &#100; — 小写d Small d
e &#101; — 小写e Small e
f &#102; — 小写f Small f
g &#103; — 小写g Small g
h &#104; — 小写h Small h
i &#105; — 小写i Small i
j &#106; — 小写j Small j
k &#107; — 小写k Small k
l &#108; — 小写l Small l
m &#109; — 小写m Small m
n &#110; — 小写n Small n
o &#111; — 小写o Small o
p &#112; — 小写p Small p
q &#113; — 小写q Small q
r &#114; — 小写r Small r
s &#115; — 小写s Small s
t &#116; — 小写t Small t
u &#117; — 小写u Small u
v &#118; — 小写v Small v
w &#119; — 小写w Small w
x &#120; — 小写x Small x
y &#121; — 小写y Small y
z &#122; — 小写z Small z
{ &#123; — 大括号左边部分Left curly brace
| &#124; — 竖线Vertical bar
} &#125; — 大括号右边部分Right curly brace
~ &#126; — Tilde
— &#127; — 未使用Unused
&#160; &nbsp; 空格Nonbreaking space
? &#161; &iexcl; Inverted exclamation
￠ &#162; &cent; 货币分标志Cent sign
￡ &#163; &pound; 英镑标志Pound sterling
¤ &#164; &curren; 通用货币标志General currency sign
￥ &#165; &yen; 日元标志Yen sign
| &#166; &brvbar; or &brkbar; 断竖线Broken vertical bar
§ &#167; &sect; 分节号Section sign
¨ &#168; &uml; or &die; 变音符号Umlaut
? &#169; &copy; 版权标志Copyright
a &#170; &ordf; Feminine ordinal
? &#171; &laquo; Left angle quote, guillemet left
? &#172; &not Not sign
? &#173; &shy; Soft hyphen
? &#174; &reg; 注册商标标志Registered trademark
ˉ &#175; &macr; or &hibar; 长音符号Macron accent
° &#176; &deg; 度数标志Degree sign
± &#177; &plusmn; 加或减Plus or minus
2 &#178; &sup2; 上标2 Superscrīpt two
3 &#179; &sup3; 上标3 Superscrīpt three
′ &#180; &acute; 尖重音符Acute accent
μ &#181; &micro; Micro sign
? &#182; &para; Paragraph sign
? &#183; &middot; Middle dot
? &#184; &cedil; Cedilla
1 &#185; &sup1; 上标1 Superscrīpt one
o &#186; &ordm; Masculine ordinal
? &#187; &raquo; Right angle quote, guillemet right
? &#188; &frac14; 四分之一Fraction one-fourth
? &#189; &frac12; 二分之一Fraction one-half
? &#190; &frac34; 四分之三Fraction three-fourths
? &#191; &iquest; Inverted question mark
à &#192; &Agrave; Capital A, grave accent
á &#193; &Aacute; Capital A, acute accent
? &#194; &Acirc; Capital A, circumflex
? &#195; &Atilde; Capital A, tilde
? &#196; &Auml; Capital A, di?esis / umlaut
? &#197; &Aring; Capital A, ring
? &#198; &AElig; Capital AE ligature
? &#199; &Ccedil; Capital C, cedilla
è &#200; &Egrave; Capital E, grave accent
é &#201; &Eacute; Capital E, acute accent
ê &#202; &Ecirc; Capital E, circumflex
? &#203; &Euml; Capital E, di?esis / umlaut
ì &#204; &Igrave; Capital I, grave accent
í &#205; &Iacute; Capital I, acute accent
? &#206; &Icirc; Capital I, circumflex
? &#207; &Iuml; Capital I, di?esis / umlaut
D &#208; &ETH; Capital Eth, Icelandic
? &#209; &Ntilde; Capital N, tilde
ò &#210; &Ograve; Capital O, grave accent
ó &#211; &Oacute; Capital O, acute accent
? &#212; &Ocirc; Capital O, circumflex
? &#213; &Otilde; Capital O, tilde
? &#214; &Ouml; Capital O, di?esis / umlaut
× &#215; &times; 乘号Multiply sign
? &#216; &Oslash; Capital O, slash
ù &#217; &Ugrave; Capital U, grave accent
ú &#218; &Uacute; Capital U, acute accent
? &#219; &Ucirc; Capital U, circumflex
ü &#220; &Uuml; Capital U, di?esis / umlaut
Y &#221; &Yacute; Capital Y, acute accent
T &#222; &THORN; Capital Thorn, Icelandic
? &#223; &szlig; Small sharp s, German sz
à &#224; &agrave; Small a, grave accent
á &#225; &aacute; Small a, acute accent
a &#226; &acirc; Small a, circumflex
? &#227; &atilde; Small a, tilde
? &#228; &auml; Small a, di?esis / umlaut
? &#229; &aring; Small a, ring
? &#230; &aelig; Small ae ligature
? &#231; &ccedil; Small c, cedilla
è &#232; &egrave; Small e, grave accent
é &#233; &eacute; Small e, acute accent
ê &#234; &ecirc; Small e, circumflex
? &#235; &euml; Small e, di?esis / umlaut
ì &#236; &igrave; Small i, grave accent
í &#237; &iacute; Small i, acute accent
? &#238; &icirc; Small i, circumflex
? &#239; &iuml; Small i, di?esis / umlaut
e &#240; &eth; Small eth, Icelandic
? &#241; &ntilde; Small n, tilde
ò &#242; &ograve; Small o, grave accent
ó &#243; &oacute; Small o, acute accent
? &#244; &ocirc; Small o, circumflex
? &#245; &otilde; Small o, tilde
? &#246; &ouml; Small o, di?esis / umlaut
÷ &#247; &divide; 除号Division sign
? &#248; &oslash; Small o, slash
ù &#249; &ugrave; Small u, grave accent
ú &#250; &uacute; Small u, acute accent
? &#251; &ucirc; Small u, circumflex
ü &#252; &uuml; Small u, di?esis / umlaut
y &#253; &yacute; Small y, acute accent
t &#254; &thorn; Small thorn, Icelandic
? &#255; &yuml; Small y, umlaut
symbols, mathematical symbols, and Greek letters
? &fnof;
Α &Alpha;
Β &Beta;
Γ &Gamma;
Δ &Delta;
Ε &Epsilon;
Ζ &Zeta;
Η &Eta;
Θ &Theta;
Ι &Iota;
Κ &Kappa;
Λ &Lambda;
Μ &Mu;
Ν &Nu;
Ξ &Xi;
Ο &Omicron;
Π &Pi;
Ρ &Rho;
Σ &Sigma;
Τ &Tau;
Υ &Upsilon;
Φ &Phi;
Χ &Chi;
Ψ &Psi;
Ω &Omega;
α &alpha;
β &beta;
γ &gamma;
δ &delta;
ε &epsilon;
ζ &zeta;
η &eta;
θ &theta;
ι &iota;
κ &kappa;
λ &lambda;
μ &mu;
ν &nu;
ξ &xi;
ο &omicron;
π &pi;
ρ &rho;
? &sigmaf;
σ &sigma;
τ &tau;
υ &upsilon;
φ &phi;
χ &chi;
ψ &psi;
ω &omega;
? &thetasym;
? &upsih;
? &piv;
? &bull;
… &hellip;
′ &prime;
″ &Prime;
￣ &oline;
? &frasl;
? &weierp;
? &image;
? &real;
? &trade;
? &alefsym;
← &larr;
↑ &uarr;
→ &rarr;
↓ &darr;
? &harr;
? &crarr;
? &lArr;
? &uArr;
? &rArr;
? &dArr;
? &hArr;
? &forall;
? &part;
?&exist;
?&empty;
? &nabla;
∈ &isin;
? &notin;
? &ni;
∏ &prod;
∑ &sum;
? &minus;
?&lowast;
√ &radic;
∝ &prop;
∞ &infin;
∠ &ang;
∧ &and;
∨ &or;
∩ &cap;
∪ &cup;
∫ &int;
∴ &there4;
～ &sim;
? &cong;
≈ &asymp;
≠ &ne;
≡ &equiv;
≤ &le;
≥ &ge;
? &sub;
? &sup;
? &nsub;
?&sube;
? &supe;
⊕ &oplus;
? &otimes;
⊥ &perp;
? &sdot;
?&lceil;
? &rceil;
? &lfloor;
?&rfloor;
? &lang;
? &rang;
? &loz;
? &spades;
? &clubs;
? &hearts;
? &diams;
markup-significant and internationalization characters:
“ &quot;
& &amp;
< &lt;
> &gt;
? &OElig;
? &oelig;
? &Scaron;
? &scaron;
? &Yuml;
? &circ;
? &tilde;
&ensp;
&emsp;
&thinsp;
? &zwnj;
? &zwj;
? &lrm;
?&rlm;
– &ndash;
— &mdash;
‘ &lsquo;
’ &rsquo;
? &sbquo;
“ &ldquo;
” &rdquo;
? &bdquo;
?&dagger;
? &Dagger;
‰ &permil;
? &lsaquo;
? &rsaquo;
€ &euro;
```



html标签自定义属性：不能驼峰   data-tip-type js里用驼峰获取


# 排序
// var arr= [
        //     {mark:3,sd:'第3'},
        //     {mark:4,sd:'第4'},
        //     {mark:1,sd:'第1'},
        //     {mark:7,sd:'第7'},
        //     {mark:2,sd:'第2'},
        //     {mark:5,sd:'第5'},
        //     {mark:8,sd:'第8'},
        //     {mark:6,sd:'第6'},
        // ]
        function bubbleSort(array){
            var i = 0,
                len = array.length,
                j,d;
            for(;i<len;i++){
                for(j=0;j<len;j++){
                    if(Number(array[i].mark)<Number(array[j].mark)){
                        d=array[j];
                        array[j]=array[i];
                        array[i]=d;
                    }
                }
            }
           // return array.reverse();//小到大
            return array.reverse();//大到小
        }
        bubbleSort(arr);