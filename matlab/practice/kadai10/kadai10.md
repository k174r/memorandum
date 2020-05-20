# 10.画像のエッジ抽出 
## 次のプログラムを参考にして，エッジ抽出を体験せよ．

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
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai10/kadai10_1.jpg)  
図1 原画像のグレースケール
<br /><br />

次に、プレウィット法を用いてエッジ抽出する。
``` m
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```
結果を図2に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai10/kadai10_2.jpg)  
図2 プレウィット法
<br /><br />

次に、ソベル法を用いてエッジ抽出する。
``` m
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```
結果を図3に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai10/kadai10_3.jpg)  
図3 ソベル法
<br /><br />

次に、キャニー法を用いてエッジ抽出する。
``` m
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```
結果を図4に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai10/kadai10_4.jpg)  
図4 キャニー法
<br /><br />
