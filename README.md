SCSS Media Queries Mixins
==================================================
SCSS用に作られたMedia Queriesを記述するためのMixinです。  
このMixinを利用するにはSass ver.3.2以上が必要です。

http://sass-lang.com/

お知らせ
--------------------------------------------------
2012-11-08: v3.0:オリエンテーション属性の有無を引数で指定できるようになりました。デバイスサイズを自由に設定できるmq-custom() Mixinが追加されました。  
2012-11-07: v2.1:タブレットRetinaディスプレイ向けMixinのバグフィックスを行いました。 

読み込み方法
--------------------------------------------------
出力用のscssファイルにインポートします。

```css
@import "media_queries";
```

説明
--------------------------------------------------
### スマートフォン端末向け
** mq-mobile ( $orientation: portrait, $version: old ) **  
@param $orientation Direction of a device  
@param $version [old|modern|future|any] The version of a device  
@param $add_orientation boolean [true|false] add orientation attribute  

### タブレット端末向け
** mq-tablet ( $orientation: portrait, $version: old ) **  
@param $orientation Direction of a device  
@param $version [old|modern|any] The version of a device  
@param $add_orientation boolean [true|false] add orientation attribute  

### デスクトップ端末向け
** mq-desctop ( $size: narrow, $version: modern ) **  
@param $size Direction of a device  
@param $version [modern|future] The version of a device 

### カスタムデバイスサイズ
** mq-custom ( $min_width, $max_width, $pixel_ratio: false, $orientation: false ) **
@param $min_width number(px) Minimum device size  
@param $max_width number(px) Maximum device size  
@param $pixel_ratio number Device px ratio  
@param $add_orientation boolean [true|false] add orientation attribute  

### 記述サンプル
```css
@include mq-mobile('portrait', 'old') {
        ...
}
@include mq-mobile('landscape', 'old') {
        ...
}
@include mq-tablet('portrait', 'old') {
        ...
}
@include mq-tablet('landscape', 'old') {
        ... 
}
@include mq-desctop('modern') {
        ...
}
@include mq-desctop('wide') {
        ... 
}
@include mq-desctop('hd') {
        ...
}
@include mq-desctop('over') {
        ...
}
```

記述サンプル
----------------------------------------------------
本来、CSSだけでは@media宣言内に規則集合（宣言ブロックとセレクタ）を
書かなければいけません。

mixinは@includeで呼び出します。このmixinは宣言ブロック内でも利用でき、
プロパティのみを宣言することができます。

```css
#wrapper
{
        //layout
        width   : 100%;

        //media queries
        @include mq-mobile('portrait', 'old') {
                width   : 320px;
        }
        @include mq-mobile('landscape', 'old') {
                width   : 480px;
        }
        @include mq-mobile('landscape', 'future') {
                //iPhone 5 landscape
                width   : 568px;
        }
        @include mq-tablet('portrait', 'old') {
                width   : 768px;
        }
        @include mq-tablet('landscape', 'old') {
                width   : 1024px;
        }
        @include mq-desctop('modern') {
                width   : 1024px;
        }
        @include mq-desctop('wide') {
                width   : 1280px;
        }
        @include mq-desctop('hd') {
                width   : 1600px;
        }
        @include mq-desctop('over') {
                width   : 100%;
                
                //nest
                a
                {
                        color    : red;        
                }
        }
}
```

このMixinを使って作られたサイト
----------------------------------------------------
* http://dev.classmethod.jp/
* http://design.classmethod.jp/

ライセンス
----------------------------------------------------
SCSS Media Queries Mixins
 
Aauthor   : Ryuichi Nonaka  
Version   : 3.0  
Copyright : 2012 Ryuichi Nonaka  
Date      : 2012/11/08  

Released under the MIT license

