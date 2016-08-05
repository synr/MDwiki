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
<iframe style="width : 100%;" frameborder="0" allowfullscreen src="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720" width="640" height="480"></iframe>
</center>

----

###測試結合燈箱效果

<a class="various" data-fancybox-type="iframe" href="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720">Iframe</a>
<a class="fancybox fancybox.iframe" href="https://drive.google.com/file/d/0B_b1e3AASsaLamM2YWF1Q2cwODQ/preview?vq=hd720">Iframe</a>