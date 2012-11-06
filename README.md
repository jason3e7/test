something
=================
*markdown 語法說明*
-----------------
資料來源 http://markdown.tw/

*Sublime Text 2*
------------------


document.compatMode
------------------

IE对盒模型的渲染在 Standards Mode和Quirks Mode是有很大差别的，在Standards Mode下对于盒模型的解释和其他的标准浏览器是一样，但在Quirks Mode模式下则有很大差别，而在不声明Doctype的情况下，IE默认又是Quirks Mode。所以为兼容性考虑，我们可能需要获取当前的文档渲染方式。
document.compatMode正好派上用场，它有两种可能的返回值：BackCompat和CSS1Compat。
BackCompat：标准兼容模式关闭。浏览器客

BackCompat Standards-compliant mode is not switched on. (Quirks Mode)
CSS1Compat Standards-compliant mode is switched on. (Standards Mode)