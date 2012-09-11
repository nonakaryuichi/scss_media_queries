SCSS Media Queries Mixins
==================================================
SCSS用に作られたMedia Queriesを記述するためのMixinです。  
このMixinを利用するにはSass ver.3.2以上が必要です。

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
@param $version [old|modern|any] The version of a device  

### タブレット端末向け
** mq-tablet ( $orientation: portrait, $version: old ) **  
@param $orientation Direction of a device  
@param $version [old|modern|any] The version of a device  

### デスクトップ端末向け
** mq-desctop ( $size: narrow ) **  
@param $size Direction of a device  

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
