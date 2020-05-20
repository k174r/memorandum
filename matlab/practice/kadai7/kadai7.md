# 7.ダイナミックレンジの拡大
## 画素のダイナミックレンジを０から２５５にせよ。

原画像は同様のものを使用し、同様に原画像を始めに白黒濃淡画像に変換した。
``` m
ORG=imread('Aso.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; axis image;% 画像の表示
```
<br /><br />
原画像を白黒濃淡画像に変換したものを図1に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai7/kadai7_1.jpg)  
図1 原画像のグレースケール
<br /><br />

ダイナミックレンジとはそれぞれの画素が持つ輝度の最小値と最大値の幅のことである。上記のグレースケール画像のヒストグラムを以下のように表示して確認してみる。ヒストグラムを図2に示す。
``` m
imhist(ORG); % 濃度ヒストグラムを生成、表示
```
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai7/kadai7_2.jpg)  
図2 ヒストグラム
<br /><br />
図2の横軸からダイナミックレンジの最大値は200以上250以下の範囲であることが分かる。

次に、ダイナミックレンジを拡大する。
``` m
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; axis image; % 画像の表示
pause;
ORG = uint8(ORG);
imhist(ORG); % 濃度ヒストグラムを生成、表示
```
上記によりグレースケール画像のダイナミックレンジが拡大される。  
ダイナミックレンジを拡大したグレースケール画像を図3に、そのヒストグラムを図4に示す。
<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai7/kadai7_3.jpg)  
図3 ダイナミックレンジを拡大したグレースケール画像

<br /><br />
![原画像](https://github.com/k174r/memorandum/blob/master/matlab/practice/image/kadai7/kadai7_4.jpg)  
図4 ダイナミックレンジを拡大したグレースケール画像のヒストグラム
<br /><br />
図4の横軸のヒストグラムより、ダイナミックレンジ拡大後のヒストグラムは拡大前のヒストグラムより最大値が大きくなっていることが確認できる。  
また、`ORG = uint8(ORG);`は計算時のdouble型とのずれをなくすためである。


matlabでは`mn = min(ORG(:));`で最小値を、`mx = max(ORG(:));`で最大値のようにそれぞれmatlab画面のワークスペース部に表示させることができる。グレースケール画像ではmn=3、mx=224であり、ダイナミックレンジを拡大後はmn=0、mx=255であることが確認できた。
