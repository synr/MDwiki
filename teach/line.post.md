#教你如何在網站上放置直接 LINE 給站長
##概念
- 可以單方面接受任何人要發給你的訊息。
你可以理解城把 LINE 當成 電子郵件收別人的信。或者，理解成留言版。
- 用途的概念方面，讓大家自由發揮，就不講太多了。
除了這篇教學教的一般~~單向放話~~聯絡用，還可以做特殊的事務通報。
  - 像是設機關在網站 Error 的時候自動回傳相關的使用者資訊。
以便網站管理員後續調查。勘查 BUG 在哪。提供基本的參考。
但這方面的設置不在本篇討論範圍，因為觸發點的設計太靈活。
主要重點是設置在回報錯誤的那個觸發點的 JavaScript。

----

##先看看影片建立流程概念
###發 LINE 給站長 安裝後的效果示範
- 先來看看安裝好的效果是長怎樣：
[示範最後效果操作影片](https://drive.google.com/file/d/0B3rgktr7zpP9QXlLbmJXM3NyRE0/preview)

###設置「直接發 LINE 給站長」過程參考影片
- 你可以先看一次影片再回來看文章，比較容易明白整個流程。
請記得播放時可以調整加速到 x2 比較省時間。
影片播放暗號皆為：``https://notify-bot.line.me``
這也是這次主要通知 LINE 的功能平台，他是一隻 LINE 官方出的 BOT。
專門當報馬仔，只會 LINE 1 對 1 說話或是在群組聊天說話。
- 要播放相關完整設置教學影片，隨時點選網站最上方選單中的影片去做選播，並輸入暗號。
或點下面這些也可以。
  - <a href="javascript:himitsu_ui('U2FsdGVkX18Urm63wL0/ZsWSRGmGnOBffUq/4w/vwR5gABli1fbs/CKwaEPJbvOm/dga/2m2XAYt908QzirS5ZeTnHOiYL1EFBsNvbrq2+KdPF1Q7DgswtJwbcJzGJD0','box');">安裝直接發 LINE 給站長 啟程</a>
  - <a href="javascript:himitsu_ui('U2FsdGVkX18U9t5LVTbRILASTkWzqP9+Y4hFEtEMLsofjUXAvx4EeoBzWBlMC8lnRgxMRgFvKfm8IZYmIrOxhwXfRpm/gmBYmpEe4q/CtJ9gYVBzX1RtGz4QQYg2B9kE','box');">安裝直接發 LINE 給站長 前置</a>（這錄影有發生常見錯誤，請當負面教材XD。下部影片會解決。）
  - <a href="javascript:himitsu_ui('U2FsdGVkX19Tl7ubPjiUVSflyuFj6mARZSa4rnb3hH2nvV/iwYMEMSe4QLUlUCvIqhWVoGitCsdpKKka0WRASPzraep8/eVbNyrkRea7z6UI9DNoT5tnbdo7sHlXKncv','box');">安裝直接發 LINE 給站長 主要</a>
  - <a href="javascript:himitsu_ui('U2FsdGVkX1/QDo8a2/3dPRdwYQBXhlTdL/ZAJfe1b+xNmmbcaV2HmVG/yaVQmR6mCljmAi+Alq59EbKzOtSjoW9hvncQfTHP1BqTJr6ovkPRBOIf88KyLxCNlGy75NyJ','box');">安裝直接發 LINE 給站長 完</a>

###你也可以大致瀏覽一下 LINE Notify-bot 的官方技術說明文件
####推薦大概看一下裡面插圖，有大概的概念（~~看插圖就好嗎~~ XD
- 日文：https://notify-bot.line.me/doc/ja/
- 英文：https://notify-bot.line.me/doc/en/

----

##本次安裝 LINE 給站長 的必備項目

1. 連結的必要平台網站帳號
你要有以下網站的帳號，請新創並登入。
  1. LINE：<https://notify-bot.line.me>
  用你想接收訊息的 LINE 帳號登入 <https://notify-bot.line.me>
  只能用綁定電子郵件的帳號做登入，沒有綁定請去綁。
  注意！第一次在某瀏覽器登入時，他會需要你行動裝置的 LINE APP 做驗證。
  所以請準備好你的手機或其他裝置在身邊，再去進行網站登入。
  2. [Zapier.com](http://zapier.com) 請快速註冊好，驗證信箱並登入。
  這比較容易，就去註冊一個吧！
  新註冊會員他會有兩週的時間免費試用付費功能，可以玩玩看。
  最顯而易見的是可創+啟用規則數可以無限多。
  平常免費帳號，只能有 5 個 Zap 同時啟用。
  這網站平台稱 1 個 Zap = 一個設定好的特殊規則。
  免費帳號平常可以設計多個，但同時間只能挑五個啟用。
2. 準備一個可以跑基本靜態網頁的地方。
你的網站或你要放來測試的地方。
只要滿足可以自訂 JavaScript 有效果的環境就可以。
例如：[忍者 Blog](http://www.ninja.co.jp/blog/) 不管是後台改樣板，還是寫文章、設定頁面。
內容都可以自由寫 javascript，所以可以使用。
3. ~~清楚的腦袋跟可以睜大的眼睛~~XD

----

##設置主要功能

提示！
關於 上方提過的必備項目網站操作方法，這篇不會提到。
這篇主要用來補充貼出影片中無法給的 code，以及如何修改成你能用的寫法。
　
基本上只要模仿影片的操作設定試試看，應該就能成功。
頂多 Zapier 在設定發送訊息的範本，因為自由度很高所以有很多選項可以用。
那邊可能會補充說明一下而已。
　
如有疑問請聯絡我，並跟我說是第幾個影片的幾分幾秒～幾分幾秒你不會設定。
我再私下跟你說怎麼設定。
視情況補寫在這篇公開的說明裡面。

Note：
以下文字說明使用 [忍者 Blog](http://www.ninja.co.jp/blog/) 的環境設定來講解。
你也可以舉一反三用在其他網頁空間都可以的。
基本上所有網頁空間都可以裝，除非你所在的環境是無法~~偷偷~~使用自己寫的 JavaScript。

###必要引用的外部 JS 檔案

- jQuery：如果你網站已經有請 jQuery 進來了，就不用裝。

~~~
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js" type="text/javascript"></script>
~~~

###將以下主要功能跟上面 jQuery（已經有裝過的跳過），塞入網頁。

- 請你透過任何手段，想辦法將這些 Code 出現在網頁裡。
但是一般開啟網站時，不能讓瀏覽者看到。
也就是說要讓他寫到你的網頁原始碼才算成功。
- 放置地點建議盡量可以放在 ``<head>`` ～ ``</head>`` 之間。
真的沒辦法也可以放在  ``<body>`` ～ ``</body>`` 之間。
- 以 [忍者 Blog](http://www.ninja.co.jp/blog) 來舉例：有三種方法，擇一使用即可。（推薦第一種）
  1. 你可以到後台，去設定タグ（Tag）
你就會連到類似 ``http://你的忍者BLOG網址/hoge/SetCommonTag/`` 的網址。
然後選擇 ``<head>`` 之後在裡面適當地方插入 jQuery 跟下面這堆 code。
之後再照下方說明或同時對照參考我的設置錄影，來修改成你的寫法。
  2. 你可以去後台，然後去修改設計樣板。
那裡一樣可以找到 ``<head>`` ～ ``</head>`` 之間進行插入。
只是跟 1 的方法比起來會看起來比較混亂。
1 的方法管理介面比較乾淨。
但，兩者效果一樣。
  3. 發布新文章或新頁面的時候，切換成可以編輯 HTML 的模式寫在裡面。
這方法的優點跟缺點是同一個：變成某篇文章或頁面才有這個功能而不是全網站。
優點來看就是節省資源：不用任何頁面都載入這些東西。
但同時也是缺點：只限於有寫的文章或頁面才能使用發 LINE 的功能（JavaScript function）。

```
<script type="text/javascript">
        //使用說明：report_webhooks() 有四個可省略參數（全都省略只會傳網址）
        //第一個參數預設為字串 LINE
        //第二個參數主要用來放留言的內文
        //第三個預設為不提醒，你也可以用1讓他提示
        //第四個是對方留下的使用者資料
        function report_webhooks(target_web="LINE",other_msg="",alert_switch=0,post_user=""){

            //經過 Zapier 再發給 LINE
            //下面兩個網址是參考資料
            //https://zapier.com/blog/how-use-zapier-webhooks/
            //http://blog.jandi.com/tw/2016/02/17/webhook/
            var zapier_target_url = "";
            if(target_web=="LINE"){
                zapier_target_url = "xxxx";
            }

            $.ajax({
                url: <解密>(zapier_target_url, <密碼>),
                data: JSON.stringify({"website_url": location.href  ,"other_msg": other_msg,"post_user": post_user}),
                type:"POST",
                dataType:'text',

                success: function(msg){
                    if(alert_switch){alert('發送成功')};
                    console.log('通報成功！');
                    console.log('被通報的所在網址：' + location.href);
                    console.log('詳細資訊備查：\n' + msg); 
                    console.log('通報單位：' + target_web);
                },

                 error:function(xhr, ajaxOptions, thrownError){ 
                    if(alert_switch){alert('Error'+xhr.status)};
                    console.log("通報失敗，詳細資訊如下：")
                    console.log(xhr.status); 
                    console.log(thrownError); 
                 }
            });
        }
</script>
```

- 其中 ``zapier_target_url = "xxxx";`` 的內容，你可以參考影片上的示範。
可以直接寫成公開的改成 。（基本款）
- 也可以像我寫成加密後的寫法。
但這加密**只防君子，不防小人**。（**很重要**）
知道怎麼理解 JavaScript 的人查一查就知道密碼是什麼了。
因為他的解密方式跟密碼根本是公開的XDDD
即使可以拐個彎，用一些環境變數當密碼的其中一環，例如：``document.domain``
這樣只是讓看到 code 的人不知道哪個網站。
~~但他如果正在開你網站，看你的原始碼才看到。~~
~~已經開你網站了，怎麼可能不知道你網站網址多少~~XD
這種加密方法只適合用來問答的時候，就像你看我的教學影片有個入口。
密碼不能留在任何地方，要靠使用者輸入的才有意義XD
  - 如果要加密的話，你也需要自己生出加密後的加密字串再貼過來。
真的有需要的話操作方法請私下問我。
  - 你可以透過本站右下角的客服功能，或最上方選項中的「交流」
選擇你喜歡的聯絡方式找到我，再跟我說話。
因為你問這個，所以我應該是需要回覆你，因此也請你留下你的聯絡方法。
- 如果你沒有要加密，你直接把
  1. 上述 code 的 ``zapier_target_url = "xxxx"``，裡面的 ``xxxx`` 改成 Zapier Webhooks 接口網址。
  2. ``url: <解密>(zapier_target_url, <密碼>),`` 改成 ``url: zapier_target_url,``（注意！最後有逗號不要漏掉）

----

##設置表單操作介面選項

1. 選一個你要寫的地方，以 [忍者 Blog](http://www.ninja.co.jp/blog/) 來說，你可以發一篇文章或一個頁面。
大概是這種網址 ``http://你的忍者BLOG網址/hoge/BlogPage/``
2. 直接複製下面的 code 然後 **在「HTML」編輯模式下**  貼上去
~~~
<script type="text/javascript">
    window.onload = function () {
            if (!((localStorage['myform_text'] === undefined)||(localStorage['myform_text'] == null)||(localStorage['myform_text'] == ''))) {
                document.getElementById('myform_text').value = localStorage['myform_text'];
            }
            if (!((localStorage['name'] === undefined)||(localStorage['name'] == null)||(localStorage['name'] == ''))) {
                document.getElementById('name').value = localStorage['name'];
            }
    }
</script>
<form action="#" target="_blank" onsubmit="javascript:return false">
	<input type="text" style="width:100%" id="name" onkeyup="javascript:localStorage['name']=this.value;" onchange="javascript:localStorage['name']=this.value;" placeholder="請填寫稱呼（非必要）"><br />
	<textarea style="width:100%" id="myform_text" rows="10" cols="50" onkeyup="javascript:localStorage['myform_text']=this.value;" onchange="javascript:localStorage['myform_text']=this.value;" placeholder="請隨意留言喔" autofocus=""></textarea><br />
	<button style="width:100%" onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,1,document.getElementById('name').value);document.getElementById('myform_text').value='';document.getElementById('name').value='';localStorage['myform_text']='';localStorage['name']='';">發送 LINE 給我</button>
</form>
~~~
  - 代碼說明：
    - 看得到的中文都可以自己改，這 OK 吧？XD
    - ``placeholder`` 是 HTML5 的屬性。
    是輸入欄位在還沒輸入文字前的提示字樣。
    - 下面這段 code 的功能是記憶使用者未發送的訊息，防手殘。效果可以詳見影片。
大概就是打字瀏覽器就會記住，直到你關閉瀏覽器為止。
除非你按下發送，他才會清掉。
途中重新整理網頁，離開再回來都會有。
建議懂邏輯再改，基本功能都寫好了應該是沒什麼需要改的。
除非你想換變數名稱XD
如果有換的話，記得 ``<form>`` 那段的也要跟著換不然對不起來就沒效果了。
~~~
<script type="text/javascript">
 window.onload = function () {
         if (!((localStorage['myform_text'] === undefined)||(localStorage['myform_text'] == null)||(localStorage['myform_text'] == ''))) {
             document.getElementById('myform_text').value = localStorage['myform_text'];
         }
         if (!((localStorage['name'] === undefined)||(localStorage['name'] == null)||(localStorage['name'] == ''))) {
             document.getElementById('name').value = localStorage['name'];
         }
 }
</script>
~~~
3. 關於這部分的 code，除了必要功能外，有很多關於外觀設定。
你可以研究看看關於 ``style`` 屬性的相關 ``CSS 或 CSS3`` 的寫法來改變成你想要的介面外觀。
你也可以把按鈕 ``<botton>`` 換成 有超連結的圖片當按鈕。
但如果那樣換的話，你要自己小心圖片大小、對齊、行高……等等的 CSS 樣式設定。

----

##小結論
###看到這邊頭昏腦脹了嗎！？
####重點只有兩個

1. ``<head>`` 的部分貼上「**設置主要功能**」裡面的 code，再修改成你的版本。
主要請你要設置你自己的 Zapier 接收網址。
2. ``<body>`` 或一般發布文章的地方，在你想創表單介面的地方。
貼上「**設置表單操作介面選項**」裡面的 code。
也是可以修改，但修改這邊主要是影響視覺效果。
要更改發送目標的話，請去研究「**設置主要功能**」裡面的 code。

----

- 所以 code 全都可以改。
只要重點的部分不要改壞掉都會有功能。
- 要有防手殘的自動記憶輸入內容功能，不一定要寫在 ``window.onload = function ()`` 裡面。
有些情況可能要請各位站長自己變化。
例如我下面裝的，就是沒有寫在那裡面。
只有單純安裝更裡面的重點：
~~~
<script type="text/javascript">
          if (!((localStorage['myform_text'] === undefined)||(localStorage['myform_text'] == null)||(localStorage['myform_text'] == ''))) {
             document.getElementById('myform_text').value = localStorage['myform_text'];
         }
         if (!((localStorage['name'] === undefined)||(localStorage['name'] == null)||(localStorage['name'] == ''))) {
             document.getElementById('name').value = localStorage['name'];
         }
</script>
~~~
因為我的網站跟他的 onload 有點衝突到，我本來有設定別的指令。
所以我就拿掉 ``window.onload = function ()``，只使用裡面的功能。
兩種寫法都是可以用的。如果你的網站也會衝突，看你要不要合併或者像我這樣只拿裡面來用。

----

##我也來裝！你看！
###我直接把上面的那兩段在下面貼上，就變這樣。
#####~~好啦，我有偷偷拿掉 autofocus，因為我這頁太長，寫那個會自動跳到後半XD~~
#####~~但我覺得如果不長的頁面用那個滿不錯的~~

<form action="#" target="_blank" onsubmit="javascript:return false">
 <input style="width:100%" type="text" id="name" onkeyup="javascript:localStorage['name']=this.value;" onchange="javascript:localStorage['name']=this.value;" placeholder="請填寫稱呼（非必要）" /><br />
 <textarea style="width:100%" id="myform_text" rows="10" cols="50" onkeyup="javascript:localStorage['myform_text']=this.value;" onchange="javascript:localStorage['myform_text']=this.value;" placeholder="請隨意留言喔"></textarea><br />
 <button style="width:100%" onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,1,document.getElementById('name').value);document.getElementById('myform_text').value='';document.getElementById('name').value='';localStorage['myform_text']='';localStorage['name']='';">發送 LINE 給我</button>
</form>
<script type="text/javascript">
         if (!((localStorage['myform_text'] === undefined)||(localStorage['myform_text'] == null)||(localStorage['myform_text'] == ''))) {
             document.getElementById('myform_text').value = localStorage['myform_text'];
         }
         if (!((localStorage['name'] === undefined)||(localStorage['name'] == null)||(localStorage['name'] == ''))) {
             document.getElementById('name').value = localStorage['name'];
         }
</script>

----

##聲明

- **這功能單純因為興趣而寫。100% 是我自己從無到有寫出來。**
- 中間參考了以前的其他經驗加上閱讀 LINE 官方的 API，才有這樣的組合用法。
  - 過往經驗所讀過的相關資料中，主要影響這次應用、幫助最大的是這個網頁：
[Webhook 的魔力？取決於你對未來工作的想像力 - JANDI Taiwan](http://blog.jandi.com/tw/2016/02/17/webhook/)
  - 其次才是其他的官方平台 API 文件說明書。
    - [Zapier Webhooks 官方說明（英文）](https://zapier.com/blog/how-use-zapier-webhooks/)
    - LINE Notify-bot 官方技術文件：
      - 日文：https://notify-bot.line.me/doc/ja/
      - 英文：https://notify-bot.line.me/doc/en/
- 目前還很少人這樣用，以個人而言我沒有看過除了我以外的站長這樣使用 XD
- 這雖然只有單向傳遞文字訊息，但也滿方便的！可以快速知道有人找你。
如果對方有留聯絡資訊，或者你的網站會不定期開個頁面公開回應。
那用途也不會太少，有一定程度的方便度。
- 實際上要深入研究的話，官方文件的設計上也是可以傳圖片的。
  但我實測發現，你必須要自己有個上傳圖片的地點。
  他只接受圖片的網址。
  而且一次發訊息只能帶一張圖片。
  貼圖也是一樣，只能選一張內建的貼圖貼出來。
  所以影片內與這篇文章所教的效果都只是最初級的簡單版。
  你想深入修改增加功能，可以去研究官方的 API 使用說明書。
- 當然這種玩法不只 LINE 可以玩。
[JANDI.com](http://jandi.com) 也可以這樣串訊息進去。
實際上我就是讓 [Zapier.com](http://zapier.com)
當然其他的平台只要有開放 API 接收訊息傳遞的功能，也一樣可以這樣玩。
但你必須研究一下對方的寫法、接法還有相關參數跟限制。
我之所以要透過 [Zapier.com](http://zapier.com) 來傳遞主要是利用他來整理輸出的資料格式跟附加 head 資訊。
如果獨立自己去加 head 會有點麻煩。需要透過伺服器之類的。
  - 當然你也可以寫一個傳統會寄電子郵件的表單，然後郵件目標寫 [Trello](http://trello.com) 的或是 [IFTTT.com](http://ifttt.com) 的信箱。
  如果是寫 [IFTTT.com](http://ifttt.com) 的信箱，你還可以看你要傳到哪個平台又要怎麼連動。全都看你個人人的想法去玩玩看。
  玩這種自動同步、推播、資料傳遞很像連連看。
  你想得到的組合，可以去相關的工具平台試試看有沒辦法讓他們串聯，自動通報。

----

📖 Note：
　 這種可以用來自動傳遞訊息的我很愛用，
　 如果未來有更多新增的功能變化，（我猜可能有）
　 我可能會不定期更新此篇。
　　
　 如果！
　 你們有人發現他其他的用途，或新功能或新用法，也歡迎隨時留言給我 XD！
　
　 2016/11/28 更新改掉部分錯字
　 2016/11/27 初稿

<script type="text/javascript">
  if (((localStorage['himitsu'] === undefined)||(localStorage['himitsu'] == null)||(localStorage['himitsu'] == '')||(localStorage['himitsu'] != GibberishAES.dec("U2FsdGVkX1+Rzd4lKJWtY9yqsBzjxKypYKVgAH5X+dQ=","20161128")))) {
	    document.location = document.location.href.replace(/\#\!(.*.md)/gi,'#');
     	//history.back();       	  	
  }
	localStorage.removeItem('himitsu');

  window.setTimeout(reset_javascript_command_url,1000);   //window.setInterval(new_a_tag_javascript, 3000); //循環
</script>