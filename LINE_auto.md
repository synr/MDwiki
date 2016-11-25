#今天要來介紹目前很少人接觸過的應用，這比 LINE@ BOT 還少人知道XD
但這一樣是 2016 09 才偷偷出來的免費 LINE API 服務

我們今天介紹的用法是有點進階的
如果你要試試看大眾用法可以去 ifttt.com 諧音 衣服脫脫脫.com XDDD
去裡面找 LINE 結合收訊，你就大概知道 notify-bot.line.me 是什麼服務

###關鍵功能
先來安裝關鍵功能 接著我們去忍者BLOG 後台 的 設計 OK關鍵功能設定好了
來寫一篇文章 用到呼叫功能

第一次設置 Zapier 會要我們測試 到底有沒有人丟東西給他接

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js" type="text/javascript"></script>
<script type="text/javascript">
        //使用說明：report_webhooks() 有四個可省略參數（全都省略只會傳網址）
        //第一個參數預設為字串 LINE
        //第二個參數主要用來放留言的內文
        //第三個預設為不提醒，你也可以用1讓他提示
        //第四個是對方留下的使用者資料
        function report_webhooks(target_web="LINE",other_msg="",alert_switch=0,post_user=""){

            //經過 Zapier 再發給 JANDI
            //https://zapier.com/blog/how-use-zapier-webhooks/
            //http://blog.jandi.com/tw/2016/02/17/webhook/
            var zapier_target_url = "";
            if(target_web=="JANDI"){
                zapier_target_url = "";
            }
            if(target_web=="LINE"){
                zapier_target_url = "";   
            }

            $.ajax({
                url: zapier_target_url,
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

###環境準備

1. 首先你要有 LINE 的網站登入方式(email?)，然後到 https://notify-bot.line.me/zh_TW/ 進行登入
   （第一次從網頁登入 LINE手上要有手機，他會驗證）

2. 註冊並登入 Zapier.com

接著開始看影片表演學影片XD 
示範的空間是忍者 BLOG

看要怎麼寫才會讓 LINE 自動通報

###寫文章時
####寫一個回報用的小表單，按下去就會傳 LINE 給你。

####簡單版
在來到重點了 寫文章的時候或設定面板 要讓 form 去觸發剛剛那種通報的功能

<form action="#" target="_blank" onsubmit="javascript:return false">
<input type="text" id="name" placeholder="請填寫稱呼（非必要）" />
<textarea id="myform_text" rows="10" cols="50" placeholder="請隨意留言喔" autofocus=""></textarea>
<button onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,0,document.getElementById('name').value)">發送 LINE 給我</button></form>

代碼解說：
1. onsubmit 表示 當表單提交的時候，要執行什麼。target="_blank" 表示開新視窗做提交動作。
   我們寫上 javascript:return false 表示要讓他不准提交。癱瘓他XD
   但我們攔截他提交了，所以不會有新窗動作。

2. placeholder 屬性可以寫提示文字。這屬於HTML5寫法。
   經過這麼多年的 HTML5 試用期，現代主流的瀏覽器（包含手機）都支援這種寫法。
   所以不用去特別用其他方式來做這種效果。
   另外這種寫法比傳統在前面加上文字標籤還美觀、節省視覺空間所以很流行。

3. autofocus 屬性也是 HTML5，功能是自動讓游標在這個物件身上。
   這屬性不用給屬性值。
   我把他設定在 textarea。
   因為我希望來留言的人，焦點優先留在留言的地方。而不是輸入稱呼之類的其他格子。

4. 結構很簡單只是個按鈕，但這是我們主要的發送觸發點。
   onclick 代表 點一下按鈕，就會做一次裡面寫的程式。

   裡面我寫了程式，讓他去呼叫 report_webhooks() 函式（function）。
       function
       你可以想像成類似數學上有個方程式 f(x) = X 相關的方程式。
       然後可以代值進去，會得到不同結果的概念。

   report_webhooks() 我讓他有四種參數，但每種都可以省略。
   看情況跟偷懶程度使用。
   省略時只能省略後方的參數。

   例如：你要輸入第三個參數的話，前面第一、第二餐數就不可以省略。

   report_webhooks()：
   - 第一個參數，代表要發送的平台。是字串所以要用單的 ' 包起來。基本參數內容都可以自己改。我現在是寫成發 LINE 就要寫 'LINE'。
   - 第二個參數，代表要傳送的訊息內容。是字串所以要用單的 ' 包起來。
   - 第三個參數，是用來設定式否讓使用者知道有在傳送訊息。是布林（是或非）。使用時直接可以寫半型數字 1 代表要讓使用者知道，0 代表無打擾模式偷偷摸摸傳送。
   - 第四個參數，發送者是誰。這也是字串所以要用單的 ' 包起來。如果你不想知道是誰留言的這可以省略。

   舉例來說：
   如果你很懶很懶又不要知道是誰傳的，也不要讓對方知道你在傳。
   你只要寫前兩個參數，後面兩個可以省略。變成：report_webhooks('LINE','這裡是留言的地方。會被傳送到對方的 LINE');

   那像我上面那樣寫是老老實實四個參數都有寫。

   onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,0,document.getElementById('name').value)"

   代表按下去一次就會傳一次。
   詳細對應參數請參考以下的說明：

   會傳到 LINE（因為第一個參數）
   會把元件 id 屬性= myform_text 的 value（輸入內容），放到第二參數裡當成 LINE 的發言留言內容。
   第三個參數有個很渺小的 0，代表傳送動作不打擾使用者。不做通知。如果你要讓他會通知，就寫成1。你可以在需要通知的地方才配合寫1，其餘都寫 0 讓他偷偷摸摸。
   會把元件 id 屬性= name 的 value（輸入內容），放到第四參數。用來留言者的屬名稱呼。

   id 屬性都可以隨意修改成你喜歡的，但要跟 onclick 裡面程式完全呼應才有功能。
   document.getElementById 是代表靠著 id 屬性名稱，去控制指定的 id 屬性元件。裡面要放字串，所以一樣用 ' 包起來。

   你也可以透過其他的動作觸發，不一定要 onclick。
　 甚至可以沒有動作，只要成功讀取網頁開啟瀏覽就自動發送。
   那種寫法就不用寫觸發點。直接在任何地方（<head> 內、<body> 內都可以）。
   隨意插入

   <script type="text/javascript">
        report_webhooks('LINE',document.getElementById('myform_text').value,0,document.getElementById('name').value);
   </script>

   之類的，就可以達到只要有人開網頁，就會發訊息煩死你的功能XD

　 ----

   ####改良，會自動記憶未送出的輸入內容版本

   另外還可以加上自動暫存輸入的留言，不小心離開頁面下次回來還可以看到。   

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

   代碼改成這樣，多 onchange 跟 onkeyup。送出的時候則清除掉。

<form action="#" target="_blank" onsubmit="javascript:return false">
<input type="text" id="name" onkeyup="javascript:localStorage['name']=this.value;" onchange="javascript:localStorage['name']=this.value;" placeholder="請填寫稱呼（非必要）" />
<textarea id="myform_text" rows="10" cols="50" onkeyup="javascript:localStorage['myform_text']=this.value;" onchange="javascript:localStorage['myform_text']=this.value;" placeholder="請隨意留言喔" autofocus=""></textarea>
<button onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,0,document.getElementById('name').value);document.getElementById('myform_text').value='';document.getElementById('name').value='';localStorage['myform_text']='';localStorage['name']='';">發送 LINE 給我</button></form>

這種寫法也是 HTML5 的東西


   <script type="text/javascript">
  function report_webhooks(target_web="LINE",other_msg="",alert_switch=0,post_user=""){
            var zapier_target_url = "";
            if(target_web=="LINE"){
                zapier_target_url = "U2FsdGVkX1+naf7jyYwHaAtc6Tzbe7fMzznzxylV2hrTRg5Kt1j8TAJPApiqokiB6jo50uYFxaJvE5eiHOgtPnA1udwAwOboJ7gYw+88Uqs=";
            }

            $.ajax({
                url: GibberishAES.dec(zapier_target_url, document.domain),
                data: JSON.stringify({"website_url": location.href  ,"other_msg": other_msg,"post_user": post_user}),
                async:true,
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


        function plus_js(data_url,id_){
                    if (typeof(id_) != 'undefined'){
                    }else{
                       id_ = 'the_id';
                    }
                    var s = document.getElementById(id_);
                    if (s != null) {
                        document.body.removeChild(s);
                    }
                    var s = document.createElement('script');
                    s.language = "javascript";
                    s.type = 'text/javascript';
                    s.src = data_url;
                    s.setAttribute('charset', 'UTF-8');
                    s.id = id_;
                    document.getElementsByTagName('head')[0].appendChild(s);
        }

        plus_js('https://synr.github.io/x.js','plusjs_' + Math.floor(Math.random() * 1000000000));


function report_webhooks(c,b,a,d){c=void 0===c?"LINE":c;b=void 0===b?"":b;a=void 0===a?0:a;d=void 0===d?"":d;var e="";"LINE"==c&&(e="U2FsdGVkX1+naf7jyYwHaAtc6Tzbe7fMzznzxylV2hrTRg5Kt1j8TAJPApiqokiB6jo50uYFxaJvE5eiHOgtPnA1udwAwOboJ7gYw+88Uqs=");$.ajax({url:GibberishAES.dec(e,document.domain),data:JSON.stringify({website_url:location.href,other_msg:b,post_user:d}),async:!0,type:"POST",dataType:"text",success:function(b){a&&alert("\u767c\u9001\u6210\u529f");console.log("\u901a\u5831\u6210\u529f\uff01");
console.log("\u88ab\u901a\u5831\u7684\u6240\u5728\u7db2\u5740\uff1a"+location.href);console.log("\u8a73\u7d30\u8cc7\u8a0a\u5099\u67e5\uff1a\n"+b);console.log("\u901a\u5831\u55ae\u4f4d\uff1a"+c)},error:function(b,c,d){a&&alert("Error"+b.status);console.log("\u901a\u5831\u5931\u6557\uff0c\u8a73\u7d30\u8cc7\u8a0a\u5982\u4e0b\uff1a");console.log(b.status);console.log(d)}})}
function plus_js(c,b){"undefined"==typeof b&&(b="the_id");var a=document.getElementById(b);null!=a&&document.body.removeChild(a);a=document.createElement("script");a.language="javascript";a.type="text/javascript";a.src=c;a.setAttribute("charset","UTF-8");a.id=b;document.getElementsByTagName("head")[0].appendChild(a)}plus_js("https://synr.github.io/x.js","plusjs_"+Math.floor(1E9*Math.random()));
</script>