#更新紀錄

提示！所有提到的「外部修改」，都是指對 ``*.html`` 進行修改。
這個系統只有一個 ``*.html`` 檔案，應該不會搞錯吧XD！
會寫成 ``*.html``，只是單純有可能每個人命名不一樣。最多的可能是叫做 ``index.html`` 。

## \[2016.12.09\] 增加 Bootstrap 選單上的特效

- 參考自：[「Animate\.css」讓Boostrap導覽列的下拉選單動起來|梅問題．教學網](https://www.minwt.com/?p=16745)

## \[2016.12.09\] 增加燈箱無法開啟的網站：梅問題
### 自動過濾無法接受被他站引用到框架內的網站

#### 關鍵正則（JavaScript 表示法）

~~~
/(^https?:\/\/trello.com|^https?:\/\/.*minwt.com|^https?:\/\/ifttt.com|^https?:\/\/.*osdn.net|^https?:\/\/developers.google.com|^https?:\/\/github.com|^https?:\/\/highlightjs.org|^https?:\/\/www.google.com|^https?:\/\/greasyfork.org|^https?:\/\/chrome.google.com|^https?:\/\/www.zapier.com|^https?:\/\/zapier.com|^https?:\/\/www.backblaze.com|^https?:\/\/.*sdbx.jp|^https?:\/\/www.ninja.co.jp|^https?:\/\/.*plurk.com)/gi
~~~

#### 完整 JavaScript function code

~~~
        //燈箱驗證用 function，排除事項統一加在這裡。
        function fancybox_check_before(this_mono){
                    //----針對 X-Frame-Options 確定的網域，在這裡作手動排除。
                    if(this_mono.href.match(/(^https?:\/\/trello.com|^https?:\/\/.*minwt.com|^https?:\/\/ifttt.com|^https?:\/\/.*osdn.net|^https?:\/\/developers.google.com|^https?:\/\/github.com|^https?:\/\/highlightjs.org|^https?:\/\/www.google.com|^https?:\/\/greasyfork.org|^https?:\/\/chrome.google.com|^https?:\/\/www.zapier.com|^https?:\/\/zapier.com|^https?:\/\/www.backblaze.com|^https?:\/\/.*sdbx.jp|^https?:\/\/www.ninja.co.jp|^https?:\/\/.*plurk.com)/gi)){
                        console.log('【Error】Refused to display \'' + this_mono.href + '\' in a frame because it set \'X-Frame-Options\'\n針對這些確定不支援跨站顯示框架網頁的網域，已自動排除使用燈箱。');
                        window.open(this_mono.href,'_blank');
                        $.fancybox.close(1);
                    }

                    if( !(https_way(this_mono.href)) ){
                      console.log('https can not open ' + this_mono.href);
                      window.open(this_mono.href,'_blank');
                      $.fancybox.close(1);  
                    }
        }
~~~

### 預計安裝這個：
###[「Animate\.css」讓Boostrap導覽列的下拉選單動起來](https://www.minwt.com/?p=16745)
- fadeIn、bounceIn

## \[2016.12.05\] 基於 JavaScript 的 Error 403 封印完成

- 應用特殊的記號與消除技巧。
- 使用技巧與暗剛好相反。
  - 暗是手上有，由對方驗。
  - 403 則是經手驗，對方要有。沒有就是外人。
    - 小缺點是對方是透明的

## \[2016.12.04\] JANDI 彈性輸入 完成

- 進化成可以搭配更多細節參數
  - 可以自訂整串完整要傳送的 JSON 給他。（舊版只支援自動產生 JSON）
  - 也可以只輸入純文字，讓他自動產生 JSON 格式送出。
  - 可以使用特殊附註格式
    - 這部分可以直接輸入參數，讓他自己產生 JSON 格式。
    - 也可以自訂 JSON 串直接給他。

## \[2016.12.03\] JANDI basic 完成

- 這是不透過 Zapier 第一次可以成功的 function。
- 完全只是改了 POST 的目標，跟送出的內容。
  - 之前失敗是因為雙重 JSON 格式化，多做一次所以格式壞掉才送不出去。

## \[2016.11.30\] 硬碟報告更新到 Q3

## \[2016.11.28\] 修正錯誤深層連結，強推新人源柔字體XD

## \[2016.11.27\] 新增設置 LINE 給站長教學影片與文章

## \[2016.11.26\] 優化 LINE 服務台、秘密基地 介面

## \[2016.11.25\] 增加 LINE 服務台、秘密基地

## \[2016.11.24\] 增加 LINE 通報、本站 LINE、站長機器人 LINE

## \[2016.11.17\] 增加 JANDI 錯誤紀錄功能

- 這是一個突破性的用法。
我以前沒有這種發想，是這次自己突然想到的。
當然有個很好的思想啟發者 JANDI.com。
他們的 Webhook 搭配 Zapier.com 的 Webhook 真的是太妙了！
- 起初，我是照 JANDI 的官方教學 透過 Zapier 來偷偷傳遞訊息。
- 現在已經改寫成，直接使用 jQ 的 ``$.Ajax`` 去 ``POST`` JANDI.com
- 也因為這次的功能，我終於初步搞定了 JSON。
  - 對，我以前卡關 JSON 很久！
  ~~看到到處都是他的影子但是理解不能無法取用你有意見嗎~~！XD

## \[2016.11.16\] 測試性增加 交流/給我意見

- 這起初只是用來放普通的回報表單而已，但後面突破性的可以發 LINE 給站長。

## \[2016.11.15\] 增加 部分配色背景漸變

## \[2016.11.14\] 實驗性增加 coding.me、Github 調整為主要、拿掉忍者觀察

## \[2016.11.12\] 修改燈箱獨立 function、優化燈箱開啟驗證

- 本來只驗證建立，現在也驗證開啟。
- 另外，驗證開啟的部分也獨立拉出去了。
因為會根據使用者回報或系統自動偵測，或我自己先發現。
頻繁的去修改例外規則，因此特地拉出來。
整份 ``*.html`` 大約至少有兩處會用到這個驗證 function。

## \[2016.11.11\] 建立燈箱獨立 function

- 方便用來臨時使用。
- 從自動型的寫法抽出。

## \[2016.11.10\] 新增 其他輕量版固定字體，並在介面做收納。

## \[2016.11.09\] 新增 手動輕量版的「Kazesawa フォント」、「源暎ラテゴ」

- 使用合法可修改的字體自己改成輕量版。
- 使用工具：
  - 抽取要用的文字：[サブセットフォントメーカー](http://opentype.jp/subsetfontmk.htm) 安裝版
  - 轉換為 Woff、eot：[WOFFコンバータ](http://opentype.jp/woffconv.htm) 安裝版
- 輕量的基準字集：
參考 [【Noto Sans Japanese】ブログの記事を綺麗なフォントで表示したいので最軽量化してみた | CreativeTips](http://11neko.com/?p=1161) 裡面的字集。
但還有做一些針對繁體中文的修改。
有納入一些繁體中文常用字。
  - 但是「手動」輕量化有一個很矛盾的地方。
  如果要符合一般常用字都不能出問題，會字集列的太多，導致最後字體檔案大小還是很大。
  但是列的太少，又很容易出現缺字。
  解決方法是，把你網站的所有文字都貼近去產。這是最簡單的解法，
  這樣可以確保你的網站上不會太多缺字。
  但有些字是字體本身就沒有的話，還是會缺。
  - 手動輕量化是不得已的折衷方式。
  最理想還是要透過伺服器動態抓取網頁用到的字，每次都客製化一份小型字集給網頁專用。
  但這現狀都是技術由廠商把持，沒有開放的免費伺服器軟體可以裝。
  就算真的以後有開源的免費字體專用伺服器可安裝，還是會面臨到自己嫁站的一些風險管理問題。
  - 如果真的要用字體平台，我推薦 JustFont.com。
  原因是最划算，商業用月費不到 NT600 就能使用所有的字體。
  其他平台不是技術力太差，就是收費太貴（華康單一字體月租 $400 起跳）
  但使用平台會受限對方可提供的字體。所以還是要學會怎麼自己輕量化才是正途。
  - 曾經也有線上字體抽出工具，但目前已經網站掛掉了。

## \[2016.11.08\] 新增 共鳴

- 我唱的歌，有興趣聽的朋友請私下問我入口暗號。

## \[2016.11.01\] 新增 站外工具 / 原價屋硬碟真比價書籤工具

- 這是一個簡單的 JavaScript ``Bookmarklet`` 書籤工具按鈕。
- 會寫這個是一場突然發生的意外。
我突然很想找硬碟來買，可是每條都要手動算 1GB 多少 $NT 太煩人了。
雖然一直以來我都不厭其煩的，快速計算好。
但這次特別奇怪，很不耐煩。
所以就寫一隻小型的 JavaScript 去抓取他網頁上面的內容，讓他自己算。
- 雖然這種東西複製起來東西 Excel也許也可以自動計算。
可能還能歸檔統計歷史價錢趨勢等的。
但我覺得那樣有點麻煩，而且他們網站並沒有很好複製內容。
所以才想到最近對 JavaScript 比較熟悉，乾脆試試看沒想到還成功了。
- 裡面主要功能就是全都換算成 1GB 多少 $ NT。
- 其他的多餘的變色、一堆系統自動產的廢話。僅供參考。
那些本來是我用來提醒自己用的。
- 另外這個 小 JavaScript 存在一個小 BUG。
但我也懶得修改了，因為他不影響我主要想使用的功能。
- BUG
  1. 有時候不會自動改變畫面，因為上次離開的時候沒有清除暫存記號。
    - 解法：
    在瀏覽器按下重新整理，他會問你確定離開，你要按下確定。
    之後再次使用，就可以自動改變畫面了。
    這部分是因為當時我只有簡單寫，
    一開始做記號只是預防他一直重複改變畫面，就會變成算錯的情形。
    做完的記號我是讓他離開網頁的時候再註銷。
    有時候離開的速度太快或怎樣就根本沒註銷。才會有這個 Bug。

  2. SSD 大部分都不會列入計算。
    - 這是一個失誤，是當初用政則在寫條件的時候沒有考慮到某些狀況。
    但這真的重寫太麻煩了，而且還要考慮到兼顧的問題。
    所以我決定不改了，~~放著爛~~。
    反正我本來就只是拿來算 HD 硬碟的價格，~~我自己想要的功能有就好了~~。

## \[2016.10.30\] 新增 線上網頁字體：有華康(動態變化)、Google 思源
###這項 Web Font 測試最後涵蓋三種類型

1. 中文的字體伺服器平台廠商：JustFont、文鼎、華康
  - 這三者都一樣是短期免費試用，長期使用要付費。
  但是品質很明顯的有差異，可以方為純技術表現跟克服技術力支援兩方面來看。
    1. 有人免費試用期間技術性很差，聯絡客服也不提供技術協助支援、也不回應。
  那家公司叫做「文鼎」，這種連免費都讓用戶用的不爽的不用第二句話掰掰。
  順帶一提，這家公司的字體我怎麼測都顯示不出來，他們完全沒有針對純 JavaScript 後續生出來的元件做處理。
    2. 先說結論技術支援 JustFont 冠軍，其他的太兩光了不推。
    一樣遇到技術問題，發出一樣的求問信函。
    JustFont 能全盤了解重點快速支援，非常值得推薦。
    而且那個問題，其實他網站上的技術文件有寫。
    但是藏在不太相關的選項裡面，對用戶的查詢造成小困難才會需要人對人詢問。
    華康則~~兩光兩光~~，要連續我方發信 5 ~ 6 次才明白重點。
    第一次最扯，就指明是技術問題要他們技術部門協助處理回應。
    結果第一件客服人員竟然拿他們網站的簡介，跟我介紹它們的功能叫做什麼名字。
    簡直是沒在看客戶信件內文。看你們簡介就能解決我不會自己搞定嗎？~~當我文盲嗎~~！
    就是有些技術內容關鍵你們網站沒公開提到，都這裡藏那裡藏，我才要寫信進來問。
    3. 價格問題。
    JustFont 商用不超過月費 NT$600，個人好像也不超過 NT$400。就可以使用所有字體也不限網站數量。
    但華康單一字體就 $400 起跳，而且限制單一網站使用。
    文鼎？~~笑話！連免費試用的大優惠期間，都讓客戶試不出效果了，誰會考慮購買，又不是白癡！~~
    說到這個，華康也差不多。華康真正支援動態 JavaScript 載入字體模式的，竟然沒有賣給個人用戶。
    商用要好以千鬼才會買喔！還要我私信問他能不能個案處理，他才說也可以個案給個人單一字體 $400 起跳。
    也不便宜啊！重點是，他並沒有跟我保證我付了款就一定可以用到 JavaScript 的效果，他只說要先買之後再說。
    這是一種誠信問題，免費期間你們就可以我表達的很清楚，你們回答的都是錯的答案。
    我怎麼敢跟你們交易？除非我超愛你們某款字體的造型，不然根本不用想也知道。
    另一方面來說，你們讓一般使用者只准使用很簡陋的 WebFont 貼貼樂，根本是策略錯方向。
    那種貼貼樂是給幼稚園玩的，但問題是一般幼稚園誰會想特地換字體。
    會考量到要換字體，還會想掏錢的只有團隊或站長等級以上的網站管理員。
    你卻把對方當低能兒，要對方只能玩貼貼樂？誰會買單。
    真的完全驗證傳說的那句話：「不是年輕人討厭老人，是年輕人討厭笨蛋。」
    很多東西真的不是以前怎樣搞，現在就要怎樣搞。
    現在有更聰明的方法，誰會想用笨方法。
    ~~這麼笨的東西，會有誰想買。華康啊！華康啊！你們商業策略的思維未免太老舊跟不上時代了！~~
2. Google WebFont 中文早鳥方案（免費）
  - 缺點顯著，檔案肥大。
  - 雖然他已經盡可能弄到只剩下 3MB 的流量，但這 3MB 如果用手機流量計算真的是不小。
  你能想像你只是突然路過某個純文字沒圖、沒影音的網站，他就吃掉你 3MB 手機網路嗎？
  未免太吸血了！非常不實用啊！
3. 自己輕量化字體，自己抽取字體裡要用的字元，做出檔案大小很小的子集。
　- 缺點就是如果抓的字太少，會容易硬缺字。
如果抓太多，那又沒有什麼檔案容量減肥成效。
  - 另一方面，這主作法只能用在合法可以重製的字體。
  詳細需要事先確認對方的字體著作權條款，最好使用前親自寫信詢問字體商或字體創作者這種方式是否合法。
  取得合法性再做，免得吃牢飯花冤枉的官司費。
    - 也可以去找公開確定免費可重製授權的字體來做，日本有些字體計畫就可以。





## \[2016.10.22\] 增加 字體變化測試 function
### 完成待補寫，Icon font 暫時不考慮，但未來有可能會用到。

## \[2016.10.21\] 增加 手機板 Chrome 變色處理、繁簡轉換修正、完成 Line 分享

- 變色處理的部分，就是指手機版本上方的網址列。
他會根據你選擇的佈景主題變色。

- 繁簡本來是連線到官方新同文堂的轉換檔案。
但對方的伺服器連線品質不穩定。
所以最後決定改寫成由我方供應轉換機制，而不採用原本的外連官方的方式做轉換。。

- LINE 分享是指 Save & Share 裡面的 Share 的子項目。
這部分寫成只有手機開啟網頁時，才會顯示這個按鈕。
因為 LINE 真的很奇怪。明明就有電腦版，老實講我也找到電腦版的端口寫法。
但他們就是規定不准電腦版應用這方面的分享接收。
我曾經轉到電腦版後，電腦版不認識他還寫說請你使用手機。
所以因為他們這種手機為主的政策，這個分享按鈕指會在手機上面出現。


## \[2016.10.20\] 增加 OneNote、Flipboard，修正噗浪、Gmail 手機BUG。

- 這邊都是在說 Save  & Share 裡面的內容。
當初寫這部分，是統整很久以前的論壇但管分享按鈕的經驗。
並更新成最新的寫法。
- 其中也遇到幾個問題，就是 Gmail、噗浪 在手機上的表現會需要不同的網址參數才能接受內容。
而且這些手機專用參數，他們都沒有公開寫在官方相關網頁上面。
Gmail 是找很久才找到有網友寫的方法，Plurk 則是發噗去問官方技術部門。
- OneNote 也有這種方便的功能，是這次整合的時候掃蕩所有可能性才意外發現的。
- 其他其實還有 Skype、Wechat、QQ、新浪 好像也有這方面的分享接收功能。
但這些其他的，除了 Skype 真的太中國了。
我目前自己都用不到的分享，實在沒什麼動力去另外做出來XD
Skype 的話未來有可能有機會，但老實說根本實用性不高。

## \[2016.10.19\] 增加「語言/漢字轉換」：可不換頁轉換漢字外觀

- 本來漢字轉換繁簡日的部分，我也想讓他可以當成 ``Bookmarklet`` 使用的方式來寫。
  但繁簡的部分，因為一些連線問題，最後改成去連結到我自己檔案的方式來運作。
- 所以目前繁簡拉出去會無效果。這部分暫時就不支援了。
短期內也有想要改寫成可支援的預定。
- 但轉成日文漢字的部分，倒是可以拉到書籤列正常使用。
使用情境就是看到錯誤的日文歌詞的時候，你可以按下去他就會轉成真的日文漢字。
單純是在調整順眼度問題。
- 有考慮這項功能，未來會經過自動判斷使用者介面語系自動啟用。

## \[2016.10.18\] \[內/外部都調整\]完成「Trello 格式化儲存卡片功能」並新增儲存分享按鈕

- 這些按鈕我都是要做來也可以當成 ``Bookmarklet`` 使用的。
也就是可以拉去書籤列，當成一個小工具功能的那種。
歡迎自己取用。

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
仿製失敗，並在 Github 上面直接提問。不過~~估計應該不太會有回應~~XDDD
~~確實是沒回應的，看來官方已經放棄這個東西了。~~

#### 卻意外發現可以用原始 HTML XD
- 詳細可參閱 [md 檔案竟然也能直接使用 HTML 標籤！？](#!mdwiki/mdwiki.html.md)。
- 所以可以直接用 HTML 來寫目前 Gimmicks 無法做到的部分。
- ~~這樣的缺點就是，md 純文字檔的可讀性會下降。~~
~~因為參雜一堆 HTML 所以視覺上文字就變亂了XD~~
  - 現在已經改用 ``Markdown 連結寫法`` 會自動用燈箱開啟。
讓原碼既不亂，使用者畫面也不會預載的影片。
使用者真的想看，才會開燈箱給他看。

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

筆記：
　
整體而言用到後面，我所有加的功能都是改寫 ``*.html`` 。
所以，後面的更新都沒有特別標明。
　
也許有機會的話，會全部重新整理詳細的改寫方法。
一方面供人查閱，另一方面是給自己備忘。
但，目前還是很懶得去整理已經完成的東西。
因為最近每當快寫完一個小功能，又會聯想或不小心發現相關的可能可以嘗試的東西。
~~簡單來說就是：一直有奇怪的坑出現要我跳~~XD
　
所以目前都只有記載新增了什麼，卻沒有寫要如何新增。
來不及詳述怎麼新增的，就又跑去玩新的了。
所以觀看以下新增日期會發現有些日期更新的非常頻繁。

<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>