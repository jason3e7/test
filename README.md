something
=================
*markdown 語法說明*
-----------------
資料來源 http://markdown.tw/

*Sublime Text 2*
------------------
[mrkt 的程式學習筆記 Sublime Text 2][]


[mrkt 的程式學習筆記 Sublime Text 2]:http://kevintsengtw.blogspot.tw/p/sublime-text-2.html


document.compatMode
------------------

IE對盒模型的渲染在 Standards Mode和Quirks Mode是有很大差別的，在Standards Mode下對於盒模型的解釋和其他的標準瀏覽器是一樣，但在Quirks Mode模式下則有很大差別，而在不聲明Doctype的情況下，IE默認又是Quirks Mode。所以為兼容性考慮，我們可能需要獲取當前的文檔渲染方式。

document.compatMode正好派上用場，它有兩種可能的返回值：BackCompat和CSS1Compat。

+ BackCompat：標準兼容模式關閉。瀏覽器客戶區寬度是document.body.clientWidth；
+ CSS1Compat：標準兼容模式開啟。 瀏覽器客戶區寬度是document.documentElement.clientWidth。

- BackCompat Standards-compliant mode is not switched on. (Quirks Mode)
- CSS1Compat Standards-compliant mode is switched on. (Standards Mode)




