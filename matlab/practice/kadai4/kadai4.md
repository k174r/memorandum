# 4.画像のヒストグラム
## 画素の濃度ヒストグラムを生成せよ．

原画像は同様のものを使用し、2.階調数と疑似輪郭と同様に原画像を始めに白黒濃淡画像に変換した。
``` m
ORG=imread('Aso.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; axis image;% 画像の表示
pause;
```
<br /><br />
原画像を白黒濃淡画像に変換したものを図1に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai4/kadai4_1.jpg)  
図1 原画像のグレースケール
<br /><br />


濃度ヒストグラムを生成するためには以下のようにした。
``` m
imhist(ORG); % ヒストグラムの表示
```
ヒストグラムの結果を図2に示す。
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai4/kadai4_2.jpg)  
図2 濃度ヒストグラム
<br /><br />

