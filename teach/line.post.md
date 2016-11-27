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

###先看看影片建立流程概念
####設置「直接發 LINE 給站長」過程參考影片
- [操作效果示範影片](https://drive.google.com/file/d/0B3rgktr7zpP9QXlLbmJXM3NyRE0/preview)
- 你可以先看一次影片再回來看文章，比較容易明白整個流程。
請記得播放時可以調整加速到 x2 比較省時間。
影片播放暗號皆為：``https://notify-bot.line.me``
這也是這次主要通知 LINE 的功能平台，他是一隻 LINE 官方出的 BOT。
專門當報馬仔，只會 LINE 1 對 1 說話或是在群組聊天說話。
- 要播放相關完整設置教學影片，隨時點選上方的影片去做選擇，並輸入暗號。
或點下面這些也可以。
  - <a href="javascript:himitsu_ui('U2FsdGVkX18Urm63wL0/ZsWSRGmGnOBffUq/4w/vwR5gABli1fbs/CKwaEPJbvOm/dga/2m2XAYt908QzirS5ZeTnHOiYL1EFBsNvbrq2+KdPF1Q7DgswtJwbcJzGJD0','box');">安裝直接發 LINE 給站長 啟程</a>
  - <a href="javascript:himitsu_ui('U2FsdGVkX18U9t5LVTbRILASTkWzqP9+Y4hFEtEMLsofjUXAvx4EeoBzWBlMC8lnRgxMRgFvKfm8IZYmIrOxhwXfRpm/gmBYmpEe4q/CtJ9gYVBzX1RtGz4QQYg2B9kE','box');">安裝直接發 LINE 給站長 前置</a>（這錄影有發生常見錯誤，請當負面教材XD。下部影片會解決。）
  - <a href="javascript:himitsu_ui('U2FsdGVkX19Tl7ubPjiUVSflyuFj6mARZSa4rnb3hH2nvV/iwYMEMSe4QLUlUCvIqhWVoGitCsdpKKka0WRASPzraep8/eVbNyrkRea7z6UI9DNoT5tnbdo7sHlXKncv','box');">安裝直接發 LINE 給站長 主要</a>
  - <a href="javascript:himitsu_ui('U2FsdGVkX1/QDo8a2/3dPRdwYQBXhlTdL/ZAJfe1b+xNmmbcaV2HmVG/yaVQmR6mCljmAi+Alq59EbKzOtSjoW9hvncQfTHP1BqTJr6ovkPRBOIf88KyLxCNlGy75NyJ','box');">安裝直接發 LINE 給站長 完</a>

----

##本次安裝 LINE 給站長 的必備項目

1. 連結的必要平台網站帳號
你要要有以下網站的帳號，請新創並登入。
  - LINE：<https://notify-bot.line.me>
  用你想接收訊息的 LINE 帳號登入 <https://notify-bot.line.me>
  只能用綁定電子郵件的帳號做登入，沒有綁定請去綁。
  第一次在某瀏覽器登入時，他會需要你行動裝置的 LINE APP 做驗證。
  所以請準備好你的手機或其他裝置在身邊，再去進行網站登入。
  - Zapier.com 請快速註冊好，驗證信箱並登入。
  這比較容易，就去註冊一個吧！
  新註冊會員他會有兩週是用付費功能，可以玩玩看。
  最顯而易見的是可創+啟用規則數可以無限多。
  平常免費帳號，只能有 5 個 Zap 同時啟用。
  這網站平台稱 1 個 Zap = 一個設定好的特殊規則。
  免費帳號平常可以設計多個，但同時間只能挑五個啟用。
2. 你的網站或你要放來測試的地方。
只要滿足可以自訂 JavaScript 有效果的環境就可以。
例如：忍者 Blog 不管是後台改樣板，還是寫文章、設定頁面。
內容都可以自由寫 javascript，所以可以使用。

----

##設置主要功能
###放在頭

- http://你的忍者BLOG網址/hoge/SetCommonTag/

~~~
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js" type="text/javascript"></script>
<!--<script src="http://file.landerso.anime-voice.com/x.js"   type="text/javascript"></script>-->
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
                zapier_target_url = "U2FsdGVkX1+naf7jyYwHaAtc6Tzbe7fMzznzxylV2hrTRg5Kt1j8TAJPApiqokiB6jo50uYFxaJvE5eiHOgtPnA1udwAwOboJ7gYw+88Uqs=";
            }

            $.ajax({
                url: GibberishAES.dec(zapier_target_url, document.domain),
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
~~~

- 其中 ``zapier_target_url = "U2FsdGVkX1+naf7jyYwHaAtc6Tzbe7fMzznzxylV2hrTRg5Kt1j8TAJPApiqokiB6jo50uYFxaJvE5eiHOgtPnA1udwAwOboJ7gYw+88Uqs=";``
的內容你要自己生。

###設置表單使用介面

- http://你的忍者BLOG網址/hoge/BlogPage/

~~~
<script type="text/javascript">    window.onload = function () {
            if (!((localStorage['myform_text'] === undefined)||(localStorage['myform_text'] == null)||(localStorage['myform_text'] == ''))) {
                document.getElementById('myform_text').value = localStorage['myform_text'];
            }
            if (!((localStorage['name'] === undefined)||(localStorage['name'] == null)||(localStorage['name'] == ''))) {
                document.getElementById('name').value = localStorage['name'];
            }
    }
   </script>
<form action="#" target="_blank" onsubmit="javascript:return false"><input type="text" id="name" onkeyup="javascript:localStorage['name']=this.value;" onchange="javascript:localStorage['name']=this.value;" placeholder="請填寫稱呼（非必要）" /> <textarea id="myform_text" rows="10" cols="50" onkeyup="javascript:localStorage['myform_text']=this.value;" onchange="javascript:localStorage['myform_text']=this.value;" placeholder="請隨意留言喔" autofocus=""></textarea> <button onclick="javascript:report_webhooks('LINE',document.getElementById('myform_text').value,0,document.getElementById('name').value);document.getElementById('myform_text').value='';document.getElementById('name').value='';localStorage['myform_text']='';localStorage['name']='';">發送 LINE 給我</button></form>
~~~