SCSS Media Queries Mixins
==================================================
SCSS用に作られたMedia Queriesを記述するためのMixinです。
このMixinを利用するにはSass ver.3.2以上が必要です。

使い方
--------------------------------------------------
```css
@import "media_queries";
```

記述サンプル
--------------------------------------------------
```css
@include mq-mobile('portrait', 'old') {

}
@include mq-mobile('landscape', 'old') {
        
}
@include mq-tablet('portrait', 'old') {
        
}
@include mq-tablet('landscape', 'old') {
        
}
@include mq-desctop('modern') {
        
}
@include mq-desctop('wide') {
        
}
@include mq-desctop('hd') {
        
}
@include mq-desctop('over') {
        
}
```
