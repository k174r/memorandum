# 8.ラベリング
## 二値化された画像の連結成分にラベルをつけよ．

原画像は同様のものを使用し、同様に原画像を始めに白黒濃淡画像に変換した。
``` m
ORG=imread('Aso.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; axis image;% 画像の表示
pause;
```
<br /><br />
原画像を白黒濃淡画像に変換したものを図1に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai8/kadai8_1.jpg)  
図1 原画像のグレースケール
<br /><br />

次に、以下のように輝度の閾値を128で二値化を行った。
``` m
IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
128で二値化を行った結果を図2に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai8/kadai8_2.jpg)  
図2 二値化画像
<br /><br />

次に、二値化した画像にラベリングを行うために以下のようにした。
``` m 
IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示
```
実行結果を図3に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai8/kadai8_3.jpg)  
図3 ラベリング
<br /><br />
