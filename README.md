# pico-imagecurdir
Pico Plugin:記事ディレクトリに配置した画像ファイルを記事内で参照可能にする

Picoのコンテンツディレクトリに、直接画像を置いて、その画像を記事から参照できるようにするプラグインです。記事ごとに画像を配置する場合に画像用ディレクトリを用意する必要が無いため便利です。

## .htaccessへの追記

Pico1.0でこのプラグインを使う場合、.htaccessの8行目(`RewriteRule ^(.*)$ index.php?$1 [L,QSA]`の次の行)に、以下の記載を追加する必要があります。

```.htaccess
    RewriteRule ^content/.*\.(jpg|jpeg|png|gif)$ - [L]
```

記事格納フォルダがcontentという名前でない場合、この記述は不要です

## テンプレートに追加する値

 * Image:画像のファイル名または、拡張子。拡張子のみを指定した場合は、記事ファイルと同じファイル名とみなす(sample.mdのメタデータに.jpgと指定すると、sample.jpgという画像ファイルがあるものとみなす)
 
##  追加するTwig変数

 * Page.image:ページ画像を示すファイルパス

##  コンフィグオプション

なし
