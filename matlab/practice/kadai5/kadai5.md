# 5.判別分析法
## 判別分析法を用いて画像二値化せよ．

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
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai5/kadai5_1.jpg)  
図1 原画像のグレースケール
<br /><br />

判別分析法を用いて原画像を二値化するには以下のようにした。  
また、実行した結果を図2に示す。
``` m
H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
max_val = 0;
max_thres = 1;
for i=1:255
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
C2 = H(i+1:256);
n1 = sum(C1); %画素数の算出
n2 = sum(C2);
myu1 = mean(C1); %平均値の算出
myu2 = mean(C2);
sigma1 = var(C1); %分散の算出
sigma2 = var(C2);
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;
end;
end;

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
<br /><br />
![原画像](https://github.com/Keitaro749/image_processing/blob/master/image/kadai5/kadai5_2.jpg)  
図2 二値化画像
<br /><br />
