
📢  提示！我目前剛開始試玩中。意在記錄操作備忘兼分享方法。但這個網站不一定會永久存在。

#⎝◕‿◕⎠MDwiki
##我所理解的 MDwiki（試玩中XD）

- 只要會 [Markdown](http://daringfireball.net/projects/markdown/)、會純文字編輯，會上傳東西到 ~~Google 硬碟~~、~~Dropbox~~、GitHub 都可以簡單使用。
而且到處都可以正常觀看！電腦、手機、平板...等等各種行動裝置螢幕翻轉，都會隨時變化最方便觀看的排版。

- MDwiki：主要特色是用 ``Markdown`` + Wiki 視覺感(?) 來呈現，簡單卻有章節架構的網站。
  - 官方網站：[http://dynalon.github.io/mdwiki/](http://dynalon.github.io/mdwiki/)
  - 只要一個官方設計的 ``.html`` 檔案，搭配現成或自己新創的 ``*.md`` [Markdown](http://daringfireball.net/projects/markdown/) 純文字檔案就能架站。
檔案結構配置得宜，就能馬上有一個網站。最簡單的配置是放在同一個資料夾下。
完全不需要其他的安裝手續，屬於輕量的一種小型 [CMS 系統（Content Management System）](https://zh.wikipedia.org/zh-tw/%E5%86%85%E5%AE%B9%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F)。
也可以視為 ``.md`` 檔案的閱讀器。有瀏覽器就能看，能編輯 ``*.md`` 檔案就能寫。
  - 技術上他使用了：
    - 內文編輯語法 / 標記語言（[markup language](https://zh.wikipedia.org/zh-tw/%E7%BD%AE%E6%A0%87%E8%AF%AD%E8%A8%80)）= [Markdown](http://daringfireball.net/projects/markdown/)（主要特色）\[使用 [marked](https://github.com/chjj/marked) 達成 \]
    - 純靜態網站技術：JavaScript（[jQuery 框架](http://www.jquery.org/)） + HTML5。
所以很多地方都能架設。也可單機使用。
      - 部分瀏覽器會禁止單機使用。
例如：Chrome 就要特別設定過啟動參數 ``--allow-file-access-from-files`` 才能使用。
屬於安全性的問題，因此沒有特殊必要也不建議單機使用。
除非你自己控制得很好，知道正在做什麼，有哪些風險又會預防。
    - 介面排版：
      1. 使用了應用 CSS3 的 [Bootstrap3](https://kkbruce.tw/bs3/) 自適應框架。
這是一種自適應或稱響應式 RWD（[Responsive web design](https://en.wikipedia.org/wiki/Responsive_web_design)）介面框架。
他有優先安排行動裝置排版的特性，可以在任何裝置上輕鬆閱讀。
不論是電腦、手機、平版，都可以根據畫面即時變化（例如螢幕翻轉），
變化成最容易閱讀，可輕鬆觀看的排版。
      2. 使用 [BootsWatch](http://bootswatch.com/) 做網站頂部下拉選單介面。
    - 程式語言高亮：使用 [highlightjs](https://highlightjs.org/)
    - 燈箱：[colorbox](http://www.jacklmoore.com/colorbox/)
      - 我還在摸索這要怎麼使用XD
  - 我覺得他很適合用來呈現章節關聯性較高的資訊。
例如：
    - 某個東西的研究結果
    - 技術手冊、操作文件
    - 私人電子書，~~或是說文字草稿集中地~~。
    - 將各種細節的遊戲新情報，整理成遊戲攻略的那種網站(?)。
    - ~~結論紀錄本~~
  - 但是，~~我摸到現在只覺得視覺介面的排版結構很 Wiki 而已~~。
原因如下：
    1. 畢竟是靜態網站，因此他不能連線資料庫等等，所以不能搜尋。
    2. 承上原因，理所當然也沒有版本文件差異比對功能。
      - 如果架在 GitHub，透過 GitHub 平台網站版內功能才能跟上個版本比對。
但是一樣沒辦法跳板比較。（程式介面是不是能跳板比對差異我沒試過）
例如：沒辦法第一個版本根最後一個版本比對。
除非把歷史檔案下載或複製內文，另外用電腦的比對軟體操作比對。（例如：WinMergePortable）
但那樣就輸給一般 WiKi 系統，線上就能挑選版本比對的功能。網站的事情在網站內處理。
      - Google Drive 的話更慘，他只會記錄所有檔案更新版本。
不但不能比對內文，還不能自由取得舊版本。
只能取得目前正在使用的版本，如果要看舊版內容就要還原成舊版。
        - <font color="red">更慘的是，現在 Google 硬碟不能拿來呈現網站了XD
這些都是過去式，現在不能用 Google 來放 MDwiki。
Google Drive 已經在 2016 年~~不知道什麼時候偷偷摸摸~~取消這功能。</font>
    3. 也沒有共同編輯功能。
也就是說有 WiKi 的外表，卻沒有 WiKi 的內在精神。
但有個方法可以達成版本管理跟共同編輯。
就是把 ``*.md`` 檔案所在的資料夾，
透過操作 ~~Google 硬碟~~（已不支援） 等等可共同編輯檔案的平台，開放這個資料夾跟某人共同編輯。
只不過版本差異化比較的功能，就比較難解了。
    4. 他不支援一般 WiKi 模式下，章節站內快速連結的**簡短**寫法。
例如 ``[[WIKI 最簡單的連結章節語法]]`` 這種他就不支援。
他只支援 [Markdown](http://daringfireball.net/projects/markdown/) 本身的 URL 寫法 ``[連結文字](完整網址)``。
不過，站內連結的時候可以簡寫，不用寫完整網址。
例如：``[test](#!mdwiki/mdwiki.main.md)``，效果像這樣：[test](#!mdwiki/mdwiki.main.md)。
不過如果他支援 ``[[mdwiki/mdwiki.main.md]]`` 的寫法，感覺比較簡單直覺XD
這如果有需要，也是有可能可以另外自己用 JavaScript 來改。
只是光想就麻煩XD，萬一又改錯就更煩了XDDD
- 他可以當作是每個章節都獨立是一個 [Markdown](http://daringfireball.net/projects/markdown/) 檔案。
然後視為這些 ``*.md`` 的檔案本身就是資料庫。備份也直接備份這些文件就好。
    - 因此，其實也是有方法可以搜尋。
前提是要有辦法把整個網站的所有 md 檔案都下載下來，
之後再用純文字編輯器開啟所有文件，就能搜尋了XD
如果是放在 Google 硬碟、Dropbox、GitHub 的話，可以整個資料夾壓縮下載。
- 官方建佔教學（英文）：
  - [MDwiki - Markdown based wiki done 100% on the client via javascript](http://dynalon.github.io/mdwiki/#!tutorials.md)
  - ~~MDwiki 官方教學如何設置在 Google 硬碟~~（[此方法已失效](https://gsuite-developers.googleblog.com/2015/08/deprecating-web-hosting-support-in.html)）
  - [MDwiki 官方教學如何設置在 GitHub](http://dynalon.github.io/mdwiki/#!tutorials/github.md)
  - [MDwiki 官方教學如何設置在 Dropbox（已改成付費功能，細節設定請自行摸索。）](http://dynalon.github.io/mdwiki/#!tutorials/dropbox.md)
- 查詢到的其他教學：[MDwiki 搭建靜態博客教程 | 霧裡看花終隔一層，蘭亭凝望皆付蕭瑟。](https://blog.ikke.moe/posts/mdwiki-tourial/)

- 當然，你也可以架設在傳統的靜態網站伺服器。
例如：[http://landerso.at-ninja.jp](http://landerso.at-ninja.jp) 就是我用來測試傳統靜態網站空間的結果。
  - 這家網域還不錯，但美中不足的是這家空間可能因為日本網站有特別為手機設置什麼機關，
所以手機看的時候要特別切去電腦版本才能順利瀏覽。
    - 這個空間最近有出另一個平台服務 [sdbx.jp](//sdbx.jp)，可以解決這個問題。
示範網站：<http://landerso.sdbx.jp>
      - 但是他無法支援 FTP，只能靠網頁介面上傳。
      - 他也**不允許有任何資料夾**。
所以要使用的話必須手動改寫 MDwiki 的檔案位子與互連引用的網址。
要改成完全沒資料夾的配置，才能用。
        - 這樣缺點就是沒辦法做出有層次的文件收納。
  - 用傳統空間有個小技巧。
私心強烈推薦這個技巧，很方便XD！
你可以搭配檔案監控軟體 \+ 支援 FTP 的檔案同步軟體，並設定連動。
去創造一個，只要你儲存或變動檔案，就會被自動上傳到 FTP 的環境。
這樣用起來很方便，可以把上傳的動作無形化。
    - 推薦檔案監控軟體：[DirectoryMonitor](https://www.google.com.tw/search?newwindow=1&q=DirectoryMonitor+%E9%98%BF%E6%A6%AE&oq=DirectoryMonitor+%E9%98%BF%E6%A6%AE&gs_l=serp.3..30i10.1299.5522.0.5904.19.13.6.0.0.0.120.1181.9j4.13.0....0...1c.1j4.64.serp..2.15.818...0i13.eAX9NC_IGiw)
    - 推薦支援 FTP 的檔案同步軟體：[FreeFileSync](https://www.google.com.tw/search?newwindow=1&q=FreeFileSync+%E9%98%BF%E6%A6%AE&oq=FreeFileSync+%E9%98%BF%E6%A6%AE&gs_l=serp.3..0.407.2032.0.3750.7.7.0.0.0.0.144.814.3j4.7.0....0...1c.1j4.64.serp..1.2.277.yK-23SciBkw)
使用同步軟體的時候，建議詳細設定你想要同步的細部規則。
我的話是設定成本機對映 FTP，等於 FTP 有多的檔案就無條件刪除。
每次同步就會完整複製本機的檔案上去，只要修改日期比較新就無條件覆蓋。

- 熟悉 [Markdown](http://daringfireball.net/projects/markdown/) 最快的方法，加入並使用 [Trello.com](https://trello.com)！
然後可以馬上寫寫看，立刻看到效果。
其次，也可以想寫的效果寫不出來時，再去查詢 [Markdown.tw](http://markdown.tw) 或 [Markdown 官方定義文件](http://daringfireball.net/projects/markdown/syntax)。
你也可以搜尋網路上相關的 Markdown 學習筆記，以下幾篇是我覺得還可以的，可以參考看看。
  - [Markdown 語法基礎及使用教程 | Elsewhere（簡體中文）](http://col.dog/2015/11/22/Markdown-Syntax/)
  - [Markdown入門學習小結 - 簡書（簡體中文）](http://www.jianshu.com/p/21d355525bdf)

----

##MDwiki 基礎重點架構檔案
- 請參閱 [MDwiki 基礎重點架構檔案](#!mdwiki/mdwiki.main.md#建構架設前，可以先嘗試了解一下_Markdown。)。

----

##Gimmicks：MDwiki 官方做來補強 markdown 本來沒有的功能
- 請參閱 [Gimmicks：補強 markdown 本來沒有的功能](#!mdwiki/mdwiki.gimmicks.md)。
- ~~但是自從我發現也可以混寫 HTML，我就比較懶的研究他了~~
反而比較喜歡自己偷塞 Javascript 自訂 function，自己塞內容進來。

----

##md 檔案竟然也能直接使用 HTML 標籤！？
- 請參閱 [md 檔案竟然也能直接使用 HTML 標籤！？](#!mdwiki/mdwiki.html.md)。

----

####提供參考：
- 這份頁面寫的 ``markdown`` 原始文件內容，可下載此連結查看：[→ 點我點我 ←](http://landerso.at-ninja.jp/index.md)
- [本站使用 0.6.2 版作測試](https://github.com/Dynalon/mdwiki/releases "2014.05.23 發布的版本到現在都沒有更新\n可能不會更新了。")
 

<!-- 

#####以下內容測試用

[[wiki/test]] -->

<!-- - 這份頁面寫的 ``markdown`` 原始文件內容，可下載此連結查看：[→ 點我點我 ←](https://docs.google.com/uc?id=0B_b1e3AASsaLYVRFN2FEd002R3M&export=download) -->
<!-- ####test
- <a href="javascript:(function(){for(var b='',c=document.getElementsByTagName('link'),a=c.length;a--;)'shortlink'==c[a].rel&&(b=c[a].href);-1!=location.href.indexOf('//www.youtube.com/watch?')&&(b=location.href.replace(/.*youtube\.com\/watch\?v=(.*)\&(.*)/,'https://youtu.be/$1?$2'));if(-1!=location.href.indexOf('//www.pixiv.net/member.php?id='))for(c=document.getElementsByTagName('input'),a=c.length;a--;)if(/http\:\/\/pixiv\.me\/.*/.test(c[a].value)){b=''==b?c[a].value:b;break}if(-1!=location.href.indexOf('//www.pixiv.net/member_illust.php?'))for(var c= document.getElementsByTagName('link'),a=c.length,d=0<document.getElementsByTagName('html')[0].lang.length?document.getElementsByTagName('html')[0].lang:'';a--;)if('en'==c[a].hreflang){b=''==b?c[a].href.replace(/www(\.pixiv\.com)/,d+'$1'):b;break}if(-1!=location.href.indexOf('//dic.nicovideo.jp'))for(c=document.getElementsByTagName('a'),a=c.length;a--;)if(/.*\/id\/(\d+)/.test(c[a].href)){b=''==b?c[a].href.replace(/.*\/id\/(\d+)/,'http://nico.ms/dic/$1'):b;break}d=(''==b?location.href.replace(/https?\:\/\/www\.nicovideo\.jp\/watch\//, 'http://nico.ms/').replace(/https?\:\/\/seiga\.nicovideo\.jp\/(seiga|watch)\//,'http://nico.ms/').replace(/https?\:\/\/live\.nicovideo\.jp\/watch\//,'http://nico.ms/').replace(/https?\:\/\/com\.nicovideo\.jp\/community\//,'http://nico.ms/').replace(/https?\:\/\/ch\.nicovideo\.jp\/.*\/blomaga\/(ar.*)/,'http://nico.ms/$1').replace(/https?\:\/\/chokuhan\.nicovideo\.jp\/products\/detail\/(\d*)/,'http://nico.ms/nd$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(az.*)/,'http://nico.ms/$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(ysamiami.*)/, 'http://nico.ms/$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(ggbo.*)/,'http://nico.ms/$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(ndsupplier.*)/,'http://nico.ms/$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(dw.*)/,'http://nico.ms/$1').replace(/https?\:\/\/ichiba\.nicovideo\.jp\/item\/(it.*)/,'http://nico.ms/$1').replace(/https?\:\/\/app\.nicovideo\.jp\/app\/(ap.*)/,'http://nico.ms/$1').replace(/https?\:\/\/jk\.nicovideo\.jp\/watch\/(jk.*)/,'http://nico.ms/$1').replace(/https?\:\/\/commons\.nicovideo\.jp\/material\/(nc.*)/, 'http://nico.ms/$1').replace(/https?\:\/\/news\.nicovideo\.jp\/watch\/(nw.*)/,'http://nico.ms/$1').replace(/https?\:\/\/www\.nicovideo\.jp\/(user\/\d*)/,'http://nico.ms/$1').replace(/https?\:\/\/www\.nicovideo\.jp\/(mylist\/\d*)/,'http://nico.ms/$1').replace(/https?\:\/\/www\.nicovideo/,'http://nicovideo').replace(/https?\:\/\/www\.facebook\.com/,'http://fb.com').replace(/https?\:\/\/www\.pixiv\.net\/member\.php\?id\=/,'http://p.tl/m/').replace(/https?\:\/\/www\.pixiv/,'http://pixiv').replace('http://bangumi.tv', 'http://bgm.tv').replace(/https?\:\/\/www\.bilibili\.com/,'http://acg.tv').replace(/(https?:\/\/trello\.com\/(c|b)\/.*)\/.*/,'$1').replace(/(https?)\:\/\/www\.plurk/,'$1://plurk').replace(/(https?)\:\/\/www\.playpcesor/,'$1://playpcesor').replace(/:\/\/.*\.(googledrive\.com.{0,})/,'://$1'):b)+'';b=document.title.replace(/( - \u30cb\u30b3\u30cb\u30b3\u52d5\u753b:GINZA| \u2010 \u30cb\u30b3\u30cb\u30b3\u52d5\u753b:GINZA| \u2010 niconico\u52d5\u756b:GINZA| - Niconico Douga: Ginza)/,'').replace(/( - \u54d4\u54e9\u54d4\u54e9 - \( \u309c- \u309c\)\u3064\u30ed \u4e7e\u676f~ - bilibili| - \u55f6\u54e9\u55f6\u54e9 - \( \u309c- \u309c\)\u3064\u30ed \u4e7e\u676f~ - bilibili)/, '').replace(/\[/g,'\\[').replace(/\]/g,'\\]').replace(/\./g,'\\.').replace(/http\:/g,'http\\:').replace(/https\:/g,'https\\:').replace(/\_/g,'\\_').replace(/\#/g,'\\#').replace(/\*/g,'\\*');navigator.userAgent.match('MSIE');console.log(void 0);var e=getSelection?getSelection().toString():'';-1!=location.href.indexOf('//www.youtube.com/watch?')&&(d=location.href);c=d;a=window;d=encodeURIComponent('- ['+b+']('+d+')')+(e?encodeURIComponent('\n\n----\n\n ```\n'+e+'\n```'):'');a.open('https://trello.com/add-card?source='+ a.location.host+'&mode=popup&url='+encodeURIComponent(c)+(b?'&name='+encodeURIComponent(b):'')+'&desc='+d,'add-trello-card','width=500,height=600,left='+(a.screenX+(a.outerWidth-500)/2)+',top='+(a.screenY+(a.outerHeight-740)/2))})();">Trello save card mini</a> -->

<!-- - 
[gimmick:gist](41020151)

- 
[gimmick:gist](41020370)
 -->


