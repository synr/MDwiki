#更新紀錄

提示！所有提到的「外部修改」，都是指對 ``*.html`` 進行修改。
這個系統只有一個 ``*.html`` 檔案，應該不會搞錯吧XD！
會寫成 ``*.html``，只是單純有可能每個人命名不一樣。最多的可能是叫做 ``index.html`` 。

##\[2016.08.08\] 加入外的「fancybox」燈箱
###並實驗性在燈箱內加入全螢幕按鈕。
####容我說一下~~廢話~~
- ~~標題都把話說完了~~
- 其實這在 2016.08.05 之後每天都有小改，途中有遇到很多意外狀況也~~各個擊破~~。
到現在才寫更新紀錄單純是因為太頻繁的修改代碼，需要寫的更新說明太大量，導致各種惰性直接不想寫說明了XD
~~一天修改存檔超過20幾次，很懶得每次都寫說明啊~~ XDDDD
但到現在個時刻，大概遇到的突發問題都排除了。
應該是穩定不會在需要大改什麼，所以才來寫XD
至於為什麼要寫，就是備忘啊！！！
我怕以後很久以後回來，會忘記要怎麼從零開始設置XD

####進入正題
#####加入「[fancybox](http://fancyapps.com/fancybox/#examples)」燈箱（Lightbox）
- 因為 MDwiki 本身有的 colorbox 燈箱我不會用，用半天都沒效果。
所以直接另外裝另一個我測成功的燈箱來玩XD
- 本來只在測試區裡面直接用 HTML 寫法測試。
但是想到以後寫文章，~~都要寫一堆 HTML 代碼來弄的內文醜醜的就很煩~~。
所以有點想要 ``增加 Gimmicks`` 或者直接寫 JavaScript 進行條件觸發修改 HTML DOM 本體。
但如之前更新提到的，Gimmicks 要加入新規則都一直仿不成功，所以這次直接跳過嘗試改他XD（诶？）



<!--

..........結果還是沒有寫完！！！！
改天再來寫XD

https://github.com/sindresorhus/screenfull.js

https://mengzhuo.org/regex/
~~~
/(?:^https?:\/\/trello.com|^https?:\/\/github.com|^https?:\/\/highlightjs.org|^https?:\/\/www.google.com|^https?:\/\/greasyfork.org|^https?:\/\/chrome.google.com)/gm
~~~

```
https://github.com/chjj/marked
https://trello.com
http://trello.com
https://highlightjs.org/
https://www.google.com
https://greasyfork.org/zh-TW/scripts/14391-zenzawatch
https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo
```

~~~
var req = new XMLHttpRequest();
req.open('GET', 'https://trello.com', false);
req.send(null);
var headers = req.getAllResponseHeaders().toLowerCase();
console.log(headers);
~~~

~~~
https://www.bootstrapcdn.com/bootswatch/
~~~
-->

----

##\[2016.08.05\] 更新 MDwiki 重點架構檔案
- 將 [MDwiki 重點架構檔案](#!mdwiki/mdwiki.main.md) 增加更多詳細敘述，但還沒補完。
~~主要是加入 ``config.json`` 的敘述。~~
搞半天還是沒寫到他XDDD，以後再補。

----

##\[2016.08.05\] 增加 md 檔案竟然也能直接使用 HTML 標籤！？頁面
- 有測試 HTML 的 ``iframe`` 標籤。
- 然後聯想到改用燈箱（Lightbox）的方式展示影片，裡面也有另裝 ``fancybox2`` 成功的測試效果。
- 預計要再寫個小 JavaScript，去自動把 Markdown 標準 URL，自動判斷連結目標來在燈箱呈現。
並且竟可能把圖片也用燈箱呈現。（預計先針對有連結目標的圖片）
  - 可參考技術文件 [DOM Element setAttribute() Method](http://www.w3schools.com/jsref/met_element_setattribute.asp)。
  - 如果沒有卡關，預計判斷成功後直接操作 ``<a>`` tag 的 HTML DOM 增加燈箱用的項目屬性。
- 其他詳細可參閱 [md 檔案竟然也能直接使用 HTML 標籤！？](#!mdwiki/mdwiki.html.md)。

----

##\[2016.08.04\] 增加 Gimmicks for Google Drive 失敗
仿製失敗，並在 Github 上面直接提問。不過估計應該不太會有回應XDDD

#### 卻意外發現可以用原始 HTML XD
- 詳細可參閱 [md 檔案竟然也能直接使用 HTML 標籤！？](#!mdwiki/mdwiki.html.md)。
- 所以可以直接用 HTML 來寫目前 Gimmicks 無法做到的部分。
- 這樣的缺點就是，md 純文字檔的可讀性會下降。
因為參雜一堆 HTML 所以視覺上文字就變亂了XD

----

##\[2016.08.03\] Gimmicks 改寫 Alert 提示觸發擴充關鍵字
###說明
- 逛到日站有教怎麼修改，所以也改了。
- 主要關鍵：[MDwikiはじめました | 3D技術研究所Blog](http://3dtech.jp/blog/?p=101) 的教學

提示!看得懂日文的，可以直接去那裡看，我這裡沒有敘述的他那裡有XD

###簡單講解操作方法
- 修改文件：``.html``
- 增加觸發關鍵字的步驟：
  - 尋找 ``var b=["note","beachte"``，之後大概看一下架構開始改。
然後自由編輯，可自行加入其他你常用或想用想的關鍵字。
這些關鍵字只要出現在文章區塊，就會像上面那樣，讓底色出現變化達成明顯提醒效果。
例如改成這樣
~~~
var b=["note","beachte","メモ"],c=["achtung","attention","warnung","warning","atención","guarda","advertimiento","注意","警告"],d=["hint","tipp","tip","hinweis","ヒント"]
~~~
只留日文跟英文的時候是這樣
~~~
var b=["note","メモ"],c=["attention","注意"],C=["warning","警告"],d=["hint","ヒント"]
~~~
加上中文
~~~
var b=["note","メモ","筆記"],c=["attention","注意","注意"],C=["warning","警告","警告"],d=["hint","ヒント","提示"]
~~~
- 增加觸發符號的步驟：
  - 尋找 ``RegExp(h+"(:|!)``
  - 改法：
比方說我要加入全形的驚嘆號跟冒號，就改成這樣：
~~~
RegExp(h+"(:|!|！|：)
~~~
- 效果測試：

警告！

注意：這只是測試

筆記：哈哈哈

提示：不告訴你

----

##\[2016.08.03\] 透過 CSS 增加對圖片自動縮放控制 
###說明
- 手機隨便轉，電腦視窗隨便拉動都 OK。
超過畫面的圖，會自動縮小到視窗大小。
- 主要關鍵：CSS 的 ``max-width`` 屬性。

###詳細操作
- 修改方法：直接開啟 ``.html``，
然後 直接在第一個 ``<style type="text/css">`` 下面，加入這段。
~~~
    div img {
        /* IE7、FF等其他非 IE 瀏覽器下最大寬度為 500px , IE6 以下不支援 max-width 屬性 */
        max-width:100%;
        /* 所有瀏覽器中圖片的大小為 500px */
        /* width:100%; */ /* 這個不要設，因為這會讓太小的圖也自動變大 */
        /* 當圖片大小大於 500px，自動縮小為 500px */
        width:expression(document.body.clientWidth>100%?"100%":"auto");
        overflow:hidden;
    }
~~~
  - = 放在 ``<style type="text/css">`` ～ ``/* hide the main content while we assemble everything */`` 之間。
  - 參考：http://fanchie.blogspot.tw/2008/02/css-css.html
  - 提示：除了 ``width`` 之外的 500px 都用 100% 取代即可
不然會連超小圖也被放大很醜

----

##\[2016.08.03\] 解決超連結不會另開新視窗的問題
###說明
- 超連結竟然全都沒有另開視窗的寫法，崩潰QQ
- 想改成：
  1. 最差至少要全都無差別另開。
  2. 最好就是要判斷非本站才另開。（直接完成２）
- 原理：
透過 JavaScript 去抓所有的超連結，然後判斷是不是有包含網站網域。
沒有包含就可以讓他開新視窗。
- 主要關鍵：直接使用各種參考連結的寫法（擇一） \+ 讓 ``<div>`` 用 ``onClick`` 呼叫才能。
- 詳細：
卡關後觀察到 MDwiki 特性是靠 JavaScript 創造。
所以會有生成的先後序的問題，導致直接套用各種參考連結寫的方法都無效。
一般方法頂多都是用 ``<body>`` 設定 ``onLoad`` 事件去觸發。
但 MDwiki 建立物件都是在那之後，理所當然會沒有用XD
因此直接使用各種參考連結的寫法（擇一） \+ 讓 ``<div>`` 用 ``onClick`` 呼叫才能。
好處是 ``onClick`` 事件在手機上也能觸發，可以完美無痛的使用。
主要喜歡參考連結中 http://www.vixual.net/blog/archives/202 的寫法。
他主要透過原始的 JavaScript 利用正則 ``RegExp`` 去操作。
所以也用他的方法深入改寫。
- 結論：這是通用版本，可以讓所有非本站的連結成叧新視窗的效果。
- 參考過程
  - http://www.wfublog.com/2014/09/html-a-tag-hyperlink-skill.html
  - http://stackoverflow.com/questions/5885465/jquery-to-add-blank-to-external-link
  - https://css-tricks.com/snippets/jquery/open-external-links-in-new-window/ ++
  - http://www.vixual.net/blog/archives/202 ++ 成功用這改出
  - http://jsgears.com/thread-402-1-1.html
  - http://stackoverflow.com/questions/804256/how-do-i-add-target-blank-to-a-link-within-a-specified-div
  
###詳細操作
- 修改方法：
  - 修改檔案：直接開啟 ``.html``，
  -  修改位子：搜尋 ``<!-- END dist/MDwiki.min.js -->`` 或 ``</head>``。
  將以下代碼放在 ``<!-- END dist/MDwiki.min.js -->``～``</head>`` 之間。
  - 修改代碼（以下兩種擇一設置就有效，推薦要死要活版XD）
    - 改的我要死要活得 Google Drive Host 醜八怪連結縮短（+單機可用版）
這個版本同時解決 Google Drive 空間網址超亂會連錯頁問題。
~~~
<!-- 外部超連結另開視窗 Google Drive 複雜版 function + 單機設置 start -->
<!-- 主要參考:http://www.vixual.net/blog/archives/202並搭配元件 onClick觸發 -->
<script type="text/javascript">
    function parseLink(){
        var tagA = document.getElementsByTagName( "a" );

        isgoogle = new RegExp( "^https?:\/\/.*.googledrive.com.*\/host\/(.*)\/(#.*)$", "i");
        var thispage_googleid = location.href.replace(isgoogle,'$1');
        
        re = new RegExp( "^(https?:\/\/" + document.domain + ")|(javascript:)", "gim");
        
        for( var i=0; i < tagA.length; i++ ){
            //不是本網域或指令的LINK，就要+開新窗。
            if( !tagA[i].href.match( re ) ){
                //本來沒有開新窗屬性的，就給他+。已經有了就不用了。
                //增加過濾單機路徑
                if ((tagA[i].target != "_blank") && (tagA[i].href.indexOf('file:\/\/\/')==-1))  {
                    //thispage_googleid 如果不是 google，就會保留完整網址。
                    //if(thispage_googleid==location.href){
                    //    console.log('這不是北七複雜的 Google Drive');
                    //}
                    //console.log('thispage_googleid = ' + thispage_googleid);
                    if(!(thispage_googleid==location.href)){
                        //有取得 google drive id
                        if(tagA[i].href.indexOf(thispage_googleid)==-1){
                            //上層 if 判斷是 google，這層判斷 google id 不同就要當外站處理，另開視窗。
                            tagA[i].target = "_blank";
                            console.log(tagA[i]);   
                        }
                    }else{
                        tagA[i].target = "_blank";
                        console.log(tagA[i]);                        
                    }
                }
            }
            googledrive_url(tagA[i]);  //只是利用同一個迴圈做事
            //單機，條件1代表正在單機，條件2代表現在這個URL不是本機路徑，就可以+新窗。
            if (((document.domain=="") && (tagA[i].href.indexOf('file:\/\/\/')==-1)) && (tagA[i].target != "_blank") ) {
                tagA[i].target = "_blank";
                console.log('單機 = ' + tagA[i]); 
            }
        }
    }
    function googledrive_url(link_url_array){
        var taga_before = link_url_array.href;
        link_url_array.href = link_url_array.href.replace(/^https?:\/\/.*.googledrive.com.*\/host\/(.*\/.*$)/i,'https://googledrive.com/host/'+'$1');
        //location.href.replace(/(^https?:\/\/.*.googledrive.com.*\/host\/)(.*\/#.*)$/i,'https://googledrive.com/host/'+'$2');
        //取得最漂亮的 google drive link（不使用組合，玩取代才能無差別），如果不是的 URL 也會保持原樣。
        //下面就是判斷是不是保持原樣。有被改過的表示就是 google drive host。
        if ( (taga_before != link_url_array.href) && (taga_before != '') ){
            console.log('Google drive change = ' + taga_before + '  to  ' + link_url_array);
        }        
    }
</script>
<!-- 外部超連結另開視窗 Google Drive 複雜版 function + 單機設置  end -->
~~~
      - 這個版本是因為 Google Drive Host 連結實在太醜就算了，
        後來還會定期自爆，造成假性破連結。
        最後我是採用寫回真實短址的方式來達成。
        概念類似把下面的基礎版，再加上自動把長網址改短的效果。
        這招如果再改寫一下，可以達成類似不管你寫什麼樣的長址，最後秀出來都自動是短的XD
    - 最基礎的簡單版：所有的現代瀏覽器都有效。手機畫面也可以正常觸發。
~~~
<!-- 外部超連結另開視窗 function 設置 start -->
<!-- 主要參考:http://www.vixual.net/blog/archives/202並搭配元件 onClick觸發 -->
<script type="text/javascript">
    function parseLink(){
        var tagA = document.getElementsByTagName( "a" );
        re = new RegExp( "^(https?:\/\/" + document.domain + ")|(javascript:)", "gim");
        for( var i=0; i < tagA.length; i++ ){
            if( !tagA[i].href.match( re ) ){
                if(tagA[i].target != "_blank"){
                    tagA[i].target = "_blank";
                    console.log(tagA[i]);
                 }
            }
        }
    }
</script>
<!-- 外部超連結另開視窗  function 設置  end -->
~~~
  2. 接著，利用尋找與取代功能：
搜尋 ``<div id="md-all">``
取代成
~~~
<div id="md-all" onclick="javascript:parseLink();">
~~~
  3. 利用尋找與取代功能：
搜尋 ``<body>`` 取代成 ``<body onload="javascript:parseLink();">``。
  4. 完成上述就 OK 了XD