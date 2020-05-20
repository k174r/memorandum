## 画像をダウンサンプリングして（標本化間隔を大きくして）表示する

標準画像「Aso」を原画像とする．この画像は縦199画素，横200画素によるディジタルカラー画像である．
``` m
ORG=imread('Aso.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示  
```  
以上によって原画像を読み込み，表示した結果を図１に示す．
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/Aso.png)  
図1 原画像
<br /><br />
原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．
``` m
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
```
以上による1/2サンプリングの結果を図２に示す．
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai1/kadai1_1.jpg)  
図2 1/2サンプリング
<br /><br />
同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，
``` m
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
``` 
以上による1/4サンプリングの結果を図３に示す．
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai1/kadai1_2.jpg)  
図3 1/4サンプリング
<br /><br />
1/8から1/32サンプリングは，
``` m
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
```  
を繰り返す．サンプリングの結果を図４～６に示す．
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai1/kadai1_3.jpg)  
図4 1/8サンプリング
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai1/kadai1_4.jpg)  
図5 1/16サンプリング
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai1/kadai1_5.jpg)  
図6 1/32サンプリング
<br /><br />
このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
