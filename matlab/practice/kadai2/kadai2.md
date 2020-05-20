# 2. 階調数と疑似輪郭
## ２階調，４階調，８階調の画像を生成せよ

kadai1と同様に標準画像「Aso」を原画像とする．
<br /><br />
``` m
ORG=imread('Aso.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールへの変換  
imagesc(ORG); axis image; % 画像の表示  
```
以上により，原画像を読み込み，グレースケールに変更したのち,表示した結果を図１に示す．
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_1.jpg)  
図1 原画像のグレースケール
<br /><br />
原画像のグレースケールを2階調画像を生成するためには以下のようにした。
``` m
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
2階調画像の結果を図2に示す．
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_2.jpg)  
図2 2階調
<br /><br />
4階調階調画像を生成するためには以下のようにした。
``` m
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
4階調画像の結果を図3に示す。
<br /><br />
![原画像](# 2. 階調数と疑似輪郭
## ２階調，４階調，８階調の画像を生成せよ

kadai1と同様に標準画像「Aso」を原画像とする．
<br /><br />
``` m
ORG=imread('Aso.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % グレースケールへの変換  
imagesc(ORG); axis image; % 画像の表示  
```
以上により，原画像を読み込み，グレースケールに変更したのち,表示した結果を図１に示す．
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_1.jpg)  
図1 原画像のグレースケール
<br /><br />
原画像のグレースケールを2階調画像を生成するためには以下のようにした。
``` m
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
2階調画像の結果を図2に示す．
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_2.jpg)  
図2 2階調
<br /><br />
4階調階調画像を生成するためには以下のようにした。
``` m
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
4階調画像の結果を図3に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_3.jpg)  
図3 4階調
<br /><br />
同様に8階調画像を生成するためには以下のようにした。
``` m
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>128;
IMG3 = ORG>192;
IMG4 = ORG>256;
IMG5 = ORG>320;
IMG6 = ORG>384;
IMG = IMG0 + IMG1 + IMG2 +IMG3 + IMG4+ IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
8階調画像の結果を図4に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_4.jpg)  
図4 8階調
<br /><br />)  
図3 4階調
<br /><br />
同様に8階調画像を生成するためには以下のようにした。
``` m
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>128;
IMG3 = ORG>192;
IMG4 = ORG>256;
IMG5 = ORG>320;
IMG6 = ORG>384;
IMG = IMG0 + IMG1 + IMG2 +IMG3 + IMG4+ IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```
8階調画像の結果を図4に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/MATLAB/blob/master/image/kadai2/kadai2_4.jpg)  
図4 8階調
<br /><br />
