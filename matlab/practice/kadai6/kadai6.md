# 6.画像の二値化
## 画像を二値化する

原画像は同様のものを使用し、同様に原画像を始めに白黒濃淡画像に変換した。
``` m
ORG=imread('Aso.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; axis image;% 画像の表示
```
<br /><br />
原画像を白黒濃淡画像に変換したものを図1に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai6/kadai6_1.jpg)  
図1 原画像のグレースケール
<br /><br />

次に、以下のようにグレースケール画像を閾値128で二値化した。結果を図2に示す。
``` m
IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; axis image; % 画像の表示
```
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai6/kadai6_2.jpg)  
図2 閾値128による二値化
<br /><br />

次に、ディザ法を使って二値化を行う。具体的には以下のように関数ditherを使って行った。  
結果を図3に示す。
``` m
IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; axis image; % 画像の表示
```
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai6/kadai6_3.jpg)  
図3 ディザ法による二値化
<br /><br />
