#md 檔案竟然也能直接使用 HTML 標籤！？
##意外發現 ``*.md`` 文件內的 HTML 寫法也會被呈現！？
- 意外發現 ``*.md`` 文件內除了中規中矩的 ``markdown`` 格式寫法。
MDwiki 也可以直接把 ``*.md`` 裡面不是 ``markdown`` 的純 HTML 寫法，直接作用在網頁上！？

- 不過這樣就很像直接寫 HTML 而已XD！
壞處的話是還好啦，不是很大量的話不礙觀瞻(咦?)。
但當初用 markdown 就是為了更簡單的專注編輯內文，視覺上簡潔方便後續維護。
裡面插入一堆 HTML 的話就走倒退路線了XD
建議真的有必要再用吧，盡量避免比較好。

- 啊！不過有一點可能滿好用的！！
就是利用 HTML 的 註解寫法，可以偷加註解而不呈現在畫面上。
Markdown 本身沒有註解的語法，雖然有什麼要備忘可以利用 HTML 上面的註解寫法XD
~~~
<!-- 
    HTML 註解區域
-->
~~~
<!-- 
    HTML 註解區域
-->

----

##馬上來測試看看
###HTML 標籤 ``iframe`` 測試
-  插入一個 Google Drive 的影片檔線上播放看看（會透過 ``iframe`` HTML 標籤）
~~~
<center>
<iframe style="width : 100%;" frameborder="0" allowfullscreen src="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720" width="640" height="480"></iframe>
</center>
~~~

####效果
- 這是操作免費[檔案變動監視軟體 DirectoryMonitor](https://www.google.com.tw/search?newwindow=1&q=DirectoryMonitor+%E9%98%BF%E6%A6%AE&oq=DirectoryMonitor+%E9%98%BF%E6%A6%AE&gs_l=serp.3..30i10.1299.5522.0.5904.19.13.6.0.0.0.120.1181.9j4.13.0....0...1c.1j4.64.serp..2.15.818...0i13.eAX9NC_IGiw) + [同步軟體 FreeFileSync](https://www.google.com.tw/search?newwindow=1&q=FreeFileSync+%E9%98%BF%E6%A6%AE&oq=FreeFileSync+%E9%98%BF%E6%A6%AE&gs_l=serp.3..0.407.2032.0.3750.7.7.0.0.0.0.144.814.3j4.7.0....0...1c.1j4.64.serp..1.2.277.yK-23SciBkw)，達成有變動就同步效果的備忘錄影。

<center>
<iframe id="test_googledrive" style="width : 100%;" frameborder="0" allowfullscreen src="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720" width="640" height="480"></iframe>
</center>

----

##測試結合燈箱（Lightbox）效果
###初期用 HTML 測試，之後寫 JavaScript 自動判斷連結決定是否要用燈箱。
- 不用燈箱的狀況，都是因為現代框架安全性問題導致。有以下幾種情況不適合。
  1. https 協定下，安全性瀏覽器會自動阻止 http 網頁入框架。
  2. 通過協定可載入，但是對方網域設定 ``X-Frame-Options`` 阻止載入。要避免這這情況，純前端環境只能人工加入篩選不友善網域。
  如果有後端環境，可以寫代理網頁先行連線去讀取對方網域查看 ``X-Frame-Options`` 數值。

#####這是直接寫 HTML 的方式完成，所以實際上內文已經很複雜了。
#####如果以後可以改成 Gimmicks 之類的外掛，應該會比較好。（已改用 JavaScript 觸發判斷）

- MDwiki 雖然好像有內建 [colorbox](http://www.jacklmoore.com/colorbox)，但我一直用不成功。
- 換另一個燈箱做另外安裝：[fancybox](http://fancyapps.com/fancybox/#examples)（v2.1.5-0）
很幸運這個燈箱的效果，不會跟之前寫的新開視窗衝突。
  - 效果：<a class="googleiframe" data-fancybox-type="iframe" href="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720" title="這是操作免費檔案變動監視軟體 DirectoryMonitor + 同步軟體 FreeFileSync，達成有變動就同步效果的備忘錄影。">Iframe</a>
<!-- <a class="fancybox fancybox.iframe" href="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720">Iframe</a> -->
  - 範例測試：<a href="http://fancyapps.com/fancybox/#examples" title="http://fancyapps.com/fancybox/#examples">fancyapps.com/fancybox/#examples</a>
  - 需要另外安裝一些檔案，下載完整包後挑出其中需要的部分檔案即可：
    - 基本上 ``source`` 跟 ``lib`` 兩個資料夾直接複製過來 ``MDwiki/fancybox`` 即可。
更詳細的檔案如下：
      - fancybox/lib/jquery.mousewheel-3.0.6.pack.js
      - fancybox/source/jquery.fancybox.css
      - fancybox/source/jquery.fancybox.pack.js
      - fancybox/source/helpers/jquery.fancybox-buttons.css
      - fancybox/source/helpers/jquery.fancybox-buttons.js
      - fancybox/source/helpers/jquery.fancybox-media.js
      - fancybox/source/helpers/jquery.fancybox-thumbs.css
      - fancybox/source/helpers/jquery.fancybox-media.js
      - fancybox/source/helpers/jquery.fancybox-thumbs.css
      - fancybox/source/helpers/jquery.fancybox-thumbs.js
      - ``fancybox/source/`` 裡面的相關圖片檔
  - 並且在 ``.html`` 中的 ``</head>`` 之前加入這段：
~~~
<!-- Lightbox fancybox 燈箱開始-->
    <!-- Add mousewheel plugin (this is optional) -->
    <script type="text/javascript" src="fancybox/lib/jquery.mousewheel-3.0.6.pack.js"></script>

    <!-- Add fancyBox -->
    <link rel="stylesheet" href="fancybox/source/jquery.fancybox.css?v=2.1.5" type="text/css" media="screen" />
    <script type="text/javascript" src="fancybox/source/jquery.fancybox.pack.js?v=2.1.5"></script>

    <!-- Optionally add helpers - button, thumbnail and/or media -->
    <link rel="stylesheet" href="fancybox/source/helpers/jquery.fancybox-buttons.css?v=1.0.5" type="text/css" media="screen" />
    <script type="text/javascript" src="fancybox/source/helpers/jquery.fancybox-buttons.js?v=1.0.5"></script>
    <script type="text/javascript" src="fancybox/source/helpers/jquery.fancybox-media.js?v=1.0.6"></script>

    <link rel="stylesheet" href="fancybox/source/helpers/jquery.fancybox-thumbs.css?v=1.0.7" type="text/css" media="screen" />
    <script type="text/javascript" src="fancybox/source/helpers/jquery.fancybox-thumbs.js?v=1.0.7"></script>

    <script type="text/javascript">
        $(document).ready(function() {
            $(".fancybox").fancybox();
        });
    </script>

    <script type="text/javascript">
        // http://fancyapps.com/fancybox/#examples
        $(document).ready(function() {
            $(".googleiframe").fancybox({
                maxWidth    : 9999,
                maxHeight   : 9999,
                fitToView   : false,
                width       : '95%',
                height      : '95%',
                autoSize    : true,
                closeClick  : false,
                openEffect  : 'none',
                closeEffect : 'none'
            });
        });
    </script>
<!-- Lightbox fancybox 燈箱結束-->
~~~
  - 張貼處的 md 文件使用時
~~~
<a class="googleiframe" data-fancybox-type="iframe" href="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720&autoplay=1" title="這是操作免費檔案變動監視軟體 DirectoryMonitor + 同步軟體 FreeFileSync，達成有變動就同步效果的備忘錄影。">Iframe</a>
~~~
    - 關鍵是在原本的超連結 ``<a>`` 加入２～３個屬性跟屬性值：
``class="googleiframe"`` 跟 ``data-fancybox-type="iframe"``。
    - ``title`` 屬性非必要，有需要顯示什麼文字才需要寫。

###相關候選燈箱
- [fancyBox - Fancy jQuery Lightbox Alternative](http://fancyapps.com/fancybox/#examples)
  - 目前網站安裝的是這個
- [rlightbox – a jQuery UI mediabox](http://ryrych.pl/rlightbox2)：UI 還可以，但功能可能(?)比較少
- [Fresco - A Beautiful Responsive Lightbox](http://www.frescojs.com)：很漂亮XD
- [Colorbox - a jQuery lightbox](http://www.jacklmoore.com/colorbox)
  - MDwiki 好像有內建這個，但用不太出來XD
測試官方 Colorbox 的寫法都不生效。
  - 測試過另外重新安裝 ``Colorbox``，疑似因為跟內建的打架(?)。
最後，還是沒有效果但也沒有錯誤訊息。所以才換 ``fancyBox``。


###Other test
- [Bootstrap](https://kkbruce.tw/bs3/Javascript)

<script type="text/javascript">
	$(function () {
	  $('[data-toggle="popover"]').popover()
	})	
</script>

<a href="#" tabindex="0" class="btn btn-lg btn-danger" role="button" data-toggle="popover" data-trigger="focus" title="Dismissible popover" data-content="And here's some amazing content. It's very engaging. Right?">取消解除狀態 (ㆆᴗㆆ)﻿</a>

----

###全螢幕
- https://github.com/sindresorhus/screenfull.js

<script type="text/javascript">
    var elem = document.getElementById('test_googledrive');
    document.getElementById('toggle').addEventListener('click', () => {
	    if (screenfull.enabled) {
	    	screenfull.request(elem);
	    }
    });	
</script>

- https://github.com/sindresorhus/screenfull.js
  - Fullscreen an element

<button id="toggle" class="btn btn-lg btn-danger">Toggle 全螢幕</button>

###Web font
<div class="fonttest">測試中文顯示</div>

<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>