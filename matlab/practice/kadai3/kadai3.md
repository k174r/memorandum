# 3. 閾値処理
## 閾値を4パターン設定し,閾値処理した画像を示せ．
<br /><br />


原画像は同様のものを使用し、2.階調数と疑似輪郭と同様に原画像を始めに白黒濃淡画像に変換した。
``` m
ORG=imread('Aso.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; axis image;% 画像の表示
pause;
```
原画像を白黒濃淡画像に変換したものを図1に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai3/kadai3_1.jpg)  
図1 原画像のグレースケール
<br /><br />


次に、原画像の輝度値の閾値を4パターン(64、96、128、192)に設定し、処理する。
<br /><br />
閾値を64に設定するためには以下のようにした。
``` m
IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar; axis image;
```
閾値を64に設定した画像を図2に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai3/kadai3_2.jpg)  
図2 閾値64
<br /><br />


閾値を96に設定するためには以下のようにした。
``` m
IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar; axis image;
```
閾値を96に設定した画像を図3に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai3/kadai3_3.jpg)  
図3 閾値96
<br /><br />


閾値を128に設定するためには以下のようにした。
``` m
IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar; axis image;
```
閾値を128に設定した画像を図4に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai3/kadai3_4.jpg)  
図4 閾値128
<br /><br />


閾値を192に設定するためには以下のようにした。
``` m
IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar; axis image;
```
閾値を192に設定した画像を図5に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai3/kadai3_5.jpg)  
図3 閾値192
<br /><br />
