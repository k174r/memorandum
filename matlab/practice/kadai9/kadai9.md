# 9.メディアンフィルタと先鋭化
## メディアンフィルターを適用し，ノイズ除去を行う。

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
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai9/kadai9_1.jpg)  
図1 原画像のグレースケール
<br /><br />

次にグレースケール画像にノイズを添付する。以下のようにした。
``` m
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; axis image; % 画像の表示
```
結果を図2に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai9/kadai9_2.jpg)  
図2 ノイズ添付画像
<br /><br />

次にノイズを添付した画像を平滑化フィルタにかけ、ノイズを除去する。
``` m
IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; axis image; % 画像の表示
```
結果を図3に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai9/kadai9_3.jpg)  
図3 平滑化フィルタ
<br /><br />

次に、メディアンフィルタでノイズ除去を行う。
``` m
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; axis image; % 画像の表示
```
結果を図4に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai9/kadai9_4.jpg)  
図4 メディアンフィルタ
<br /><br />

次に、設計したフィルタでのノイズ除去を行う。
``` m
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; axis image; % 画像の表示
```
結果を図5に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai9/kadai9_5.jpg)  
図5 設計したフィルタ
<br /><br />


