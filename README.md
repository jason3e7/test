something
=================
markdown 語法說明
-----------------
資料來源 http://markdown.tw/

Sublime Text 2
------------------
[mrkt 的程式學習筆記-Sublime Text 2][] <br/>
[前端觀察-一些必不可少的Sublime Text 2插件]


[mrkt 的程式學習筆記-Sublime Text 2]:http://kevintsengtw.blogspot.tw/p/sublime-text-2.html
[前端觀察-一些必不可少的Sublime Text 2插件]:http://www.qianduan.net/essential-to-sublime-the-text-2-plugins.html

+ jsFormat插件:選中一段文本，control+alt+f。

document.compatMode
------------------

IE對盒模型的渲染在 Standards Mode和Quirks Mode是有很大差別的，在Standards Mode下對於盒模型的解釋和其他的標準瀏覽器是一樣，但在Quirks Mode模式下則有很大差別，而在不聲明Doctype的情況下，IE默認又是Quirks Mode。所以為兼容性考慮，我們可能需要獲取當前的文檔渲染方式。

document.compatMode正好派上用場，它有兩種可能的返回值：BackCompat和CSS1Compat。

+ BackCompat：標準兼容模式關閉。瀏覽器客戶區寬度是document.body.clientWidth；
+ CSS1Compat：標準兼容模式開啟。 瀏覽器客戶區寬度是document.documentElement.clientWidth。

- BackCompat Standards-compliant mode is not switched on. (Quirks Mode)
- CSS1Compat Standards-compliant mode is switched on. (Standards Mode)


判断Javascript对象是否存在
--------------------------

<pre><code>
if (!myObj) {
	var myObj = { };
	  　　}
</pre></code>

<pre><code>
if (!window.myObj) {
	var myObj = { };
	　　}
</pre></code>

<pre><code>
if (typeof myObj == "undefined") {
	var myObj = { };
	　　}
</pre></code>

<pre><code>
if (myObj == undefined) {
	var myObj = { };
	　　}
</pre></code>


SASS
------------------

中文compass簡報
http://www.slideshare.net/kurotanshi/compass-sass#btnNext


安裝compass
http://blog.mukispace.com/compass-for-html-code-project/

http://wp.xdite.net/?p=2097

http://blog.visioncan.com/2011/compass-sass-your-css/

完整的介紹了compass
http://www.im-ux.com/archives/1222

SASS的語法分成兩種，一種叫做scss，另一種就是sass，sass這個語法的特色就是他不需要大括弧，而是用跟Python一樣的縮排方式取代大括弧的功用，至於scss則是跟一般的CSS語法一樣要有大括弧。SASS提供兩種編譯方式，一種是手動編譯，一種是監視編譯(–watch)，手動編譯就是當你撰寫好CSS時下指令去做編譯，監視編譯則是你指令一個目錄，當此目錄裡面的*.scss檔案有改變時（新增、覆寫等等），就會自動去做編譯的動作。

###變數Variables###
變數的命名第一個字一定要是$開頭

<pre><code>
 $text:15px;	 
 body{
	font-size:$text;
	}
 #top{
	width:$text;
	}

</pre></code>

###函式Mixin###

<pre><code>
 @mixin border-radius($angle){
	border-radius:$angle;
	-webkit-border-radius:$angle;
	-moz-border-radius:$angle;
	}

 #box{
	@include border-radius(10px);
 }

 //如果你要傳入多個參數可以用逗號分開

@mixin border-radius($angle){
	#box{
		border-radius:10px;
		-moz-border-radius:10px;
		-webkit-border-radius:10px;
	}
}
 
@include border-radius(10px);

 //也可以填一段完整的CSS語法進去
</pre></code>

###繼承Extend###

<pre><code>

//SCSS
.error {
  border: 1px #f00;
  background: #fdd;
}
.error.intrusion {
  font-size: 1.3em;
  font-weight: bold;
}

.badError {
  @extend .error;
  border-width: 3px;
}

//CSS

.error, .badError {
  border: 1px #f00;
  background: #fdd;
}

.error.intrusion,
.badError.intrusion {
  font-size: 1.3em;
  font-weight: bold;
}

.badError {
  border-width: 3px;
}

</pre></code>

###巢狀撰寫Nesting###

<pre><code>
a{
color:#f00;
&:hover{

	}
}
//SCSS
@mixin table-base {
  th {
    text-align: center;
    font-weight: bold;
  }
  td, th {padding: 2px}
}

@mixin left($dist) {
  float: left;
  margin-left: $dist;
}

#data {
  @include left(10px);
  @include table-base;
}

//CSS
#data {
  float: left;
  margin-left: 10px;
}
#data th {
  text-align: center;
  font-weight: bold;
}
#data td, #data th {
  padding: 2px;
}
</pre></code>



