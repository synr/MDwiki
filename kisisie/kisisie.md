#為加密式惡意行為，事先設防降低受害風險 (反勒索病毒)
##前言

Attention! 以下幾個方式，只列出我個人**目前**也有使用的方法。
本內容只考慮 Win7 以上系統，重點在被加密前防止他進行加密的可能。
不擅長看長文的，建議至少閱讀第二條水平線之後的設定。

Hint: 也就是建議至少閱讀「歹徒進來你家怎麼辦！？快躲好別給他殺！」那段以後的內容。(◕‿◕)

Note: 這篇[本來寫在 Trello](https://trello.com/c/PV4kfjSD)，試著移過來呈現看看XD

- 當然也有其他方法可能有類似效果，但我只整理我個人親自有使用的供參考。
- ``本內容只考慮 Win7 以上系統，重點在被加密前防止他進行加密的可能。``
第一段（第二條水平線以上的）以迴避感染為優先，
其他則為感染後，妨礙病毒完整病發的各種止血阻止加密的防禦方法。
很大的篇幅在妨礙寫入或讀取，
也有部分是妨礙病毒本身發作的其中一種管道。
``這些防禦方法一樣是要在感染前就設定好才有用！``
- 除非是已知的病毒，否則單純會強制加密再刪除原檔的行為，
大部分的防毒都無法判斷為惡意行為並禁止他這麼做。
換句話說，他的行為跟一般使用者很類似。
導致防毒無法從行為判斷並禁止他。
而強制加密的原理很簡單，
他會搜尋整台電腦所有可以讀取又可以寫入的區域，
並針對這些可以存取的區域，進行大範圍的加密。
不論檔案大小，都只加密局部就能造成檔案被破壞，
所以加密速度非常快。
``因此本篇重點都在歸納事前要如何布局，``
``讓大部分檔案資料都常態禁止寫入``，避免中獎後所有非系統檔案都被加密。
- 本內容不特別深入探討創傷後的補救建議或操作。
因為事後補救就是一個簡單的原則而已：**事先** ``勤．斷網多重異地備份``
至於用什麼工具備份，怎樣的備份頻率都隨個人喜好。
有人用 ``Ghost`` 一次整個硬碟複製起來或做成映像檔。
但執行備份時~~曠日廢時~~，最後可能久久備份一次而已。
有人排程針對各種檔案做差異或增量檔案遠端備份，
比較容易隨時備份到最新版本檔案，
尤其有資料快照（Snapshot） 功能的軟體更好用。
有人備份在隨身碟、隨身硬碟，
有硬體防寫物理開關的隨身碟當然更好。
有人花比較高成本的方式，直接使用 NAS 相關硬體解決。
備份之外呢？還可以還原、真．墳場復活（還原被刪除的檔案）。
有人犧牲硬碟一半的容量使用付費的完整影子系統，隨時儲存還原點。
有人花錢買硬體還原卡，或軟體還原卡保護資料區的還原點。
有人直接當硬碟壞軌的方式處理，找硬碟救援公司企圖復活已刪除資料。
當然還是一樣``建議要定期完整備份``，
但是這是屬於最消極的事後補救、墳場復活、死者甦醒的做法，
而``這張卡紀錄的是讓系統迴避，盡量不遇到歹徒``的方法，
``萬一遇到歹徒闖到你家(已感染)``，
``也要讓他殺不到人(無法寫入加密)，找不到人殺(無法讀取檔案)``。
  - 台灣錸德有出過硬體防寫物理開關的隨身碟產品，只是很冷門而已。
這種設計跟早期磁片有物理開關，控制磁片硬體防寫是相同的概念。
（對，沒錯他就是以前做空白光碟片的那個公司：錸德）
    - 產品關鍵字：``錸德RiDATA ID15`` ：分別有 8、16、32、64 GB
（~~為什麼我買的時候最大只有 32GB！可惡！也才差一年XD~~）
是硬體防寫物理性開關的隨身碟，[這裡有比價](https://www.findprice.com.tw/datalist.aspx?s=g&q=%E9%8C%B8%E5%BE%B7RiDATA+ID15)。
原則上換算成每 1GB 差不多 10 ~ 16 台幣。
總容量越大的，換算後可以得知每 1GB 的對應價格越便宜。
我個人 2015 入手後有用過，確實可以硬體防寫。
在 Windows 以外的系統一樣防寫，似乎連格式化都無法辦到。
只不過他的防寫物理開關，做的很難切換可寫 / 不可寫。
需要用針或是牙籤輔助，才能將物理開關切換成另一個狀態。
但這種硬體防寫的設計，比較不怕病毒透過軟體方式突破寫入。
連系統外都無法格式化了XD
    - 其實，第一次接觸這種物理開關硬體防寫的隨身碟是 2005 左右。
MSI 的一款 只有 256 MB 的 MP3 隨身碟。
只是沒想到過了十年後，市面上可以硬體防寫的隨身碟竟然這麼少。
至少我目前只找得到錸德，而且只有這個型號跟這款設計。
所以才提這支隨身碟，~~並不是有什麼利益關係~~XDD
硬體防寫可以更有效減少 USB 感染的機率，卻沒什麼人要出XD
    - 2016 / 06 / 19 左右抓到最低的價是這樣：64GB 約 $600
換算完 600 ÷ 64 = 每 1GB 花費 9.375 台幣
（這個時間點硬碟最低價，差不多是隨身碟的 10%。快要1GB=1台幣）
[![.](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/1103x770/26c041c9c999e47b8da7c66f5977a100/1466245579440.jpg "點圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/1103x770/26c041c9c999e47b8da7c66f5977a100/1466245579440.jpg)
這種東西只會跌不會漲，只是他跌價速度非常緩慢。
  - 2016/07/20  ``DataTraveler 2000`` 加密隨身碟
逛到金士頓（Kingston）高級隨身碟（沒萊德平價，因為他功能太多XD）
[有著密碼鎖的隨身碟，Kingston DataTraveler 2000 試用](http://www.techbang.com/posts/41570-has-a-combination-lock-flash-drive-kingston-datatraveler-2000-trial)
也有防寫模式，
更威的是他整支都會加密。
但，光看他的規則覺得滿危險的，
猜錯密碼 10 次自動格式化XD。
    - 詳細相關規則：
      - 唯讀模式。
      - 連續 10 次登入失敗，會自動鎖定、刪除原本設定的 Pin 碼、重新格式化磁碟。
      - 解鎖沒有立即插入電腦，25 秒後會自動上鎖。
      - 強行拔除會自動上鎖。
      - 逾時鎖定是在連接到電腦後，閒置時間達 1～99 分設定值之後自動上鎖，可降低離開電腦被他人窺探的機率。
      - 電腦端退出裝置，沒有立即拔除超過 5 秒會自動上鎖並進入充電模式。
      - 沒解鎖就插電腦，會進入充電模式，電腦不會偵測到 DataTraveler 2000。

----

##使用者先養成良好習慣
- 瀏覽器請常態使用檔廣告的擴充功能，降低風險。
- 可疑的、陌生的網址不要直接前往，先丟去可以掃描的網站掃描安全性。
例如：[VirusTotal](https://www.virustotal.com) 裡面的 URL 功能就可以掃描網址。
- 執行不明程式前，先上傳雲端分析程式安全性。
推薦上傳 [VirusTotal](https://www.virustotal.com) ，
他裡面可以有很多家防毒幫你檢測。
- 聳動又可疑誇張的標題或在社群網站(FB...等)突然看到什麼色情連結，請不要直接進入。通常都有問題才會用那種標題吸引人點下去。
真的要點，請確認你的資料都備份好了。
```有「看一次」電腦就會中毒的覺悟```，再去點XDD
點之前一樣請先丟給 [VirusTotal](https://www.virustotal.com) 等網站事先進行分析。
但是這種東西，只是滿足好奇心你根本可以不用進去冒險的。
建議遇到那種都不要上當。
- 不外乎，電子郵件的可疑標題也是，可疑附件也是不要亂開不要亂點。

----

##不要去危險的地方遇到歹徒，門窗關上別讓歹徒進你家遇到你。
####還沒被感染前，降低可能遇上感染的風險。
#### 首先一些風險極大後門很多的傢伙，強烈建議不要使用。
- 完全棄用這些傢伙：
  - IE，最好是從系統安裝程式那裏移除或關閉，一輩子不再用他。
[![別用 IE 把它關掉或移除](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/420x398/046d9afb998c81e08f9c6dd70b2b9a96/1466234921406.jpg "別用 IE 把它關掉或移除")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/420x398/046d9afb998c81e08f9c6dd70b2b9a96/1466234921406.jpg)
可參考 [將 IE8 從 Windows 7 當中移除](http://www.techbang.com/posts/5719-topics-w7-uninstall-in-windows-7-ie8)
  - 其次是 Flash 也建議完全從系統中移除。
就算有時候要使用他，用 Chrome 內建的就夠了。
不要在系統裡面安裝 Flash 造成資安風險。
    - 如果有網站一定要用 Flash 播放，請搜尋 HTML5 的替代方法。
例如：ニコニコ動画官方只提供 Flash 播放。
但是有網友自己製作 HTML5 版本的播放器，就推薦用 HTML5 播放。
反正最好就是放棄所有 Flash！！！
像``ニコニコ動画``就可以改用這個來播放：
https://trello.com/c/1lAqsfi8/3-html5-flash
  - 其餘不必要的網頁插件/外掛是程式也都是高風險族群，
這些外掛式的程式基本上都存在很高風險的漏洞，
而且也都是過時的產品。
沒必要的話能不用就不要用，不要用就不要裝。
要用再裝，用完移除。
但這裡的立場是**強烈建議連用都不要用了**。
舉例來說有：APPLE 的 ``QuickTime``、微軟的銀光 ``Silverlight``
老實說，你根本很少在網站上面看到這些東西的必要應用。
這都是早期的一些過時的作法。
現代這些做法，大部分都能用更安全的 HTML5 取代。
當然還是有些設計是例外的，例如某些繪圖聊天的網頁程式。
但還有一個稍微比較多人裝的叫做 ``JAVA``。
這傢伙也是很容易被病毒利用，後門被發現機率有點高的軟體。
沒必要的話，真心、強烈建議移除他。
有必要的時候只裝一下下，用完就馬上砍掉才是上策。
當然要裝就要裝最新版本，漏洞才少。
    - 這時候建議用使用頻率做安裝取捨上的參考。
最佳方案是要用再裝，``用完立刻移除乾淨``。
不用就一輩子不要去考慮安裝他，謝謝。
  - 萬不得已，工作上或很重要的事情，需要用到上面提到的這幾個傢伙。
請一定要使用``最新版本，有多新用多新``。
``最好工作結束後，立刻移除乾淨``，不留任何閒置空窗的機會。
養成要使用再安裝，用完就移除的習慣。
更龜毛一點的話還可以，安裝後使用的時候不要連上網。
當然最好都不要安裝最好！！
    - 補充：[查詢 Flash 最新版本的方式](http://www.adobe.com/software/flash/about/)
2016/06/18 的現在已知 ``Flash 22.0.0.192`` 以上的版本，
才有修補台灣六月這波勒索病毒的入侵途徑。
- 瀏覽器設定：
  - 請盡量排除萬難(?)，只使用各廠牌最新版本瀏覽器。
  - Flash 等外掛程式，不要自動執行。
由使用者手動判斷每個元件進行放行。
萬一全都開自動執行，很容易在不知情的危險情況中招！
例如：[\[問題\] 臉書直播病毒? - 看板 AntiVirus - PTT](https://www.ptt.cc/bbs/AntiVirus/M.1465977318.A.88E.html)
    - 操作參考：到各廠牌瀏覽器的進階設定去修改。
以「Chrome」為例，去 ``設定 → 顯示進階設定``
[![設定方法](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/480x199/c4451f5f99e44cad137aef50142a5a1e/1466235209431.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/480x199/c4451f5f99e44cad137aef50142a5a1e/1466235209431.jpg)
再到 ``隱私權 → 內容設定``，之後所有都會預設無法使用外掛。
[![設定禁止](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/345x199/3c60586516438c6b5b65591a16cafe84/1466235303134.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/345x199/3c60586516438c6b5b65591a16cafe84/1466235303134.jpg)
[![設定禁止](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/350x240/9fe073f6d0c51cac37ff8b6925ebfa55/1466235355906.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/350x240/9fe073f6d0c51cac37ff8b6925ebfa55/1466235355906.jpg)
遇到足夠信任安全的網站，有必要再局部進行單一元件放行運作。
[![按右鍵進行放行](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/711x709/6c5e28fcd111a62d1c66a03f036a7b9a/1466235619862.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/711x709/6c5e28fcd111a62d1c66a03f036a7b9a/1466235619862.jpg)
  - 從進階設定修改成 JavaScript 完全不執行。
每次遇到信任的網站才加入白名單，並重新整理網頁。
這是比較極端的防禦法。
但可以很徹底的禁止莫名其妙突然跳出的網頁，
突然執行路過下載攻擊（Drive by download）的可能。
    - >「Drive by download」= 路過式下載（隱藏式下載、偷渡式下載、強迫下載、網頁掛馬）。
詳細：http://blog.trendmicro.com.tw/?p=17503
    - 操作參考：這種設定一樣都會在各大瀏覽器的進階設定裡面。
以「Chrome」為例，去 ``設定 → 顯示進階設定``
[![設定方法](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/480x199/c4451f5f99e44cad137aef50142a5a1e/1466235209431.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/480x199/c4451f5f99e44cad137aef50142a5a1e/1466235209431.jpg)
再到 ``隱私權 → 內容設定``，
[![設定禁止](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/345x199/3c60586516438c6b5b65591a16cafe84/1466235303134.jpg  "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/345x199/3c60586516438c6b5b65591a16cafe84/1466235303134.jpg)
之後找到 ``JavaScript`` 的項目，將他改成 ``不允許任何網站``。
[![不允許任何網站](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/319x155/1850fccc6a186f9a89d549838133c168/1466236220142.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/319x155/1850fccc6a186f9a89d549838133c168/1466236220142.jpg)
遇到足夠信任又熟悉的網站，再將它放行。
[![放行](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/840x763/5b7560ba5b86faefedf6ce7104ca0b0b/1466236526847.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/840x763/5b7560ba5b86faefedf6ce7104ca0b0b/1466236526847.jpg)
放行後，這個網站就會被加入例外清單不會被禁用。
  - 安裝各瀏覽器的檔廣告擴充功能或插件。
原理是檔下廣告，避免接觸到廣告進而降低被路過下載攻擊的可能性。
可以使用一些有持續更新阻擋問題網域清單的檔廣告功能，例如：
    - Adblock Plus
    - [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)
uBlock 跟 uBlock Origin 不一樣，推薦 uBlock Origin。
都一樣免費原理一樣。但是 uBlock Origin 有繼續維護更新。
uBlock 沒有。

----

##歹徒進來你家怎麼辦！？快躲好別給他殺！
###針對惡意加密行為「預先」做各種防範的建議
1. 完全拒絕你寫入，轉為極端保守派不結婚(X)不能進(不
設定資料夾或分割區的寫入權限為「**拒絕**」：
原理是讓**當下**的 Windows 使用者，無法修改特定資料夾或分區。
當這個病毒以這個使用者的身分，要進行自動加密。
會因為沒有權限而無法寫入。
  - 操作圖例：
圖例：
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/318x529/11368e55fde24ac732cc6995b9c1e58c/1466237194299.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/318x529/11368e55fde24ac732cc6995b9c1e58c/1466237194299.jpg)
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/367x230/99e24cd4b73007fb0f366b228eeca097/1466237257207.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/367x230/99e24cd4b73007fb0f366b228eeca097/1466237257207.jpg)
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/384x793/d9e7d4729adb51090aceb85074d1d9fe/1466237468402.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/384x793/d9e7d4729adb51090aceb85074d1d9fe/1466237468402.jpg)
  - ``FAT32 的分割區無法使用這個方式限制寫入權限！！``
  - 某些情況下順利變更整個分割區的權限後，
系統會說資源回收桶損毀然後要情你清空回收桶。
所以 ``請務必在變更權限前，先繞去資源回收桶手動整理一下``，
該留的存去別的地方，要清除的清乾淨。
回收桶淨空後，再開始調整權限。
  - 這招一樣會讓正常程式無法寫入。
所以要寫入之前，要瞬間先解除這項權限。用完再把權限調回拒絕寫入。
  - 個人建議針對 ``Administrators`` 跟第一發起人示範的 ``Authenticated Users``，都設定拒絕寫入。（如上圖）
    - 第一發起人：[Re: \[問題\] 關於勒索病毒的一點防治想法請教 - 看板 AntiVirus - 批踢踢實業坊](https://www.ptt.cc/bbs/AntiVirus/M.1461847912.A.603.html)
    - 改良建議：[Re: \[問題\] 檔案改唯讀，是否可破勒索病毒行為？ - 看板 AntiVirus - 批踢踢實業坊](https://www.ptt.cc/bbs/AntiVirus/M.1465260232.A.759.html)
  - 這招如果不想自己設定內建的介面，也有其他程式可以達成類似效果。
例如：[**這裡**](https://www.ptt.cc/bbs/AntiVirus/M.1465127023.A.96E.html)提到的白名單軟體 ``Secure Folders``（請關閉自動更新，因為作者已不維護）、``Easy File Locker``
當然也可以軟體跟手動設定並用。
  - **注意！這招在設定權限的時候，很容易遇到某些設定錯誤。**
    - 例如：
      - 沒有更改擁有權為現在使用者，造成修改權限被拒絕。
這種通常發生在有多重系統的時候，各系統會互搶。
例如 XP 設定過權限，到 Win7 因為不是當初的擁有者而無法修改。
這種情況只要進去 ``安全性 → 進階`` 修改 ``擁有者`` 幾乎都能改了。
      -  以為整體資料夾下的所有權限都跟母資料夾，或分區資料夾一樣，
獲得禁止寫入/修改的權限設定，但其實漏掉了一堆沒設定到。
遇到這種情況，一樣從最外面的母資料夾或分割區進去  ``安全性 → 進階`` 修改，直接按 ``變更權限`` ，
然後把 ``以這個物件的繼承權限「取代」所有子物件`` 打勾，之後按套用。
就可以把漏網之魚全都改成一樣禁止寫入的權限。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/373x467/ece3a474327f8c3cd47ef7b1d831f3f5/1466237661501.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/373x467/ece3a474327f8c3cd47ef7b1d831f3f5/1466237661501.jpg)
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/626x442/12ebcf82e96f1f9b31dfa24d53d540c5/1466237692221.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/626x442/12ebcf82e96f1f9b31dfa24d53d540c5/1466237692221.jpg)
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/636x445/a9ada9dcd96aabd7645c361ef8737719/1466237777285.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/636x445/a9ada9dcd96aabd7645c361ef8737719/1466237777285.jpg)
  - ~~我個人目前只有操作手動的部分，白名單軟體還沒玩過。~~
    - ``Secure Folders``、``Easy File Locker`` 我都玩了一下，都一樣只有英文版。
這兩款比較容易更改權限，可以快速解禁跟禁止。
但注意 ``Secure Folders 已經沒有官方網站也停止維護`` ，
因此安裝後要立刻取消自動更新功能，以防用偽裝的更新攻擊。
如果不排斥用軟體輔助設定，也可以用軟體輔助。
兩款功能相似，操作方法類似。
個人偏好名字有 Easy 的那款XD
~~原因是他沒有自動更新那種後門的感覺~~XDDDD
      - 介面跟用法大概是這樣，可以組合規則。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/1078x299/7f05f8106f5edeac81d7104b67aadd4b/1467049912851.jpg "點圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/1078x299/7f05f8106f5edeac81d7104b67aadd4b/1467049912851.jpg)
        - 有層次的例外規則寫法：
會有一些規則可以設定出例外的感覺。
例如我本來想讓整個 ``Z:\`` 分割區都只能讀不可寫。（規則３）
但卻有個例外的資料夾為 ``B某``，要讓他可以寫入。（規則２）
可是在 ``B某`` 裡面一樣又要有個資料夾，要讓他無法寫入。（規則１）
就變成這樣的順序，最上面的會先實現，優先權的概念。
所以如果有什麼規則會例外的，記得最裡面的資料夾規則先到最上面。
        - 圖的第五個規則是為了[禁止這個執行](https://twgemini616.wordpress.com/2007/10/17/wmpnetwk-exe-%E4%BD%9C%E7%A5%9F-%E7%A1%AC%E6%98%AF%E9%97%9C%E4%B8%8D%E6%8E%89/)。
我確定我不想用 WMP 可是沒設定這篇連結的服務關閉前，
他都會一直重新執行，還沒找到關閉方法前，
可以透過第五條規則讓他無法無限重複執行。
        - 圖的第六個規則是 IE 相關的東西一直被呼叫，
但我又確定我不使用 IE 覺得很煩，
所以才把 ``ielowutil.exe`` 的路徑找出來，之後禁止他所有權限能力。
2. 不給你門路，別想進我家門，連門都不給你，連見面都不給你見
分割區拿掉路徑代碼（例如 D：）：
沒有路徑就無法讓程式走到檔案，連讀取都無法讀取。
（除非他會像 Ghost 一樣可以直接指定 1:2，1:X 硬碟或分割區數字....）
這招一樣是 [**→ 在這篇 ←**](https://www.ptt.cc/bbs/AntiVirus/M.1461847912.A.603.html) 看到，
各位也可以進去看看，參考文中的操作方式。
拿掉路徑的操作上比較簡單，不容易誤會就不另外拍例圖了XD
  - ``但要注意的是，正在執行程式或被讀取資料的分割區，``
``要把程式相關都關掉後，再移除路徑代號比較好。``
``當然，作業系統分割區不要去移除他的路徑不然會.......很可怕XD``
  - 這適合用在不常使用或純資料儲存的分割區或資料夾。
  - 這招一樣會讓正常程式無法走到檔案路徑。
解決方法可以搭配進階一點的藏資料夾用法：消失的分割區
[\[心得\] 將檔案藏進特殊資料夾躲避勒索軟體的追殺 - 看板 AntiVirus - 批踢踢實業坊](https://www.ptt.cc/bbs/AntiVirus/M.1465602889.A.5EB.html)
還可以再搭配 Windows 內建指令 ``Subst``
造出來的特殊資料夾，反虛擬回分割區代號的方式，
辦到局部開放的存取的效果，控制災區(?)。
    - 詳細操作方法：之後再另外寫XD

3. 教你家系統，別聽別人的話，全都拒絕(誤
禁止在桌面執行 ``*.js``、``*.vbs``...等，Windows Script Host 指令檔案。
可以阻擋病毒啟動這個管道來做壞事的機會，讓病毒少一個管道使壞。
反正這個管道正常情況下，也很少人會用到了。
但這跟有款鄉民自己寫的 ``.vbs`` 自動偵測是否檔案已改的功能相衝突。
因為那個功能是依靠 ``.vbs`` 在視窗執行運作。
這個方法是禁用所有的 Windows Script Host 指令檔案，
所以他寫的那款也會直接無法使用。
可以當成無差別禁止。
  - 真實案例：[\[討論\] 隨身碟捷徑病毒解決方法](https://www.ptt.cc/bbs/AntiVirus/M.1466130803.A.8D6.html)、[原PO](https://m.facebook.com/story.php?story_fbid=544209945751521&id=100004875609135)
所以不只勒索病毒很愛用這些奇怪的指令檔做壞事，
USB 病毒也很愛，沒事就把他關了吧！
其他案例：[這隻勒索病毒不僅會偷密碼，還會偷比特幣錢包 | 資安趨勢](http://blog.trendmicro.com.tw/?p=18535)
  - 操作方式：透過 Regedit 修改 Reg 機碼，控制禁用。
    - 透過 ``*.reg`` 的方式設定禁用（這方式跟下面手動操作效果一樣）
      - 新增一個記事本文件，內容貼上下面這些後存檔。
```
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Script Host\Settings]
"Enabled"=dword:00000000
```
存檔後，修改副檔名為 ``.reg``，再用管理員權限使用者去執行他。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/909x156/4dedec550a07a65e63717ead53e8f3e2/1466241546434.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/909x156/4dedec550a07a65e63717ead53e8f3e2/1466241546434.jpg)
    - 手動新增：開始 → 用管理員權限執行 ``regedit``
之後走入目標路徑，然後新增下面這些內容。
      - 操作目標路徑：
``HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Script Host\Settings``
      - 操作對象：新增一個 ``Enabled``，填入數值「``0``」。
建議用 16 進位（但好像沒差）
要取消這項設定的時候，就把它改成「``1``」。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/580x269/a09421cbc73cdaffbf7e120c8fa7a9a1/1466241910621.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/580x269/a09421cbc73cdaffbf7e120c8fa7a9a1/1466241910621.jpg)
    - 自我檢測禁用是否設置成功能禁用
      - 隨便產個記事本或小畫家的檔案，把它副檔名改成 ``.vbs`` 或 ``.js``。
之後，執行那個檔案。
如果檔案執行後出現下面這個視窗，表示成功禁用。
[![成功](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/505x185/ad591050a4146a7212d19ac1b77f2f7e/1466240811606.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/505x185/ad591050a4146a7212d19ac1b77f2f7e/1466240811606.jpg)
其餘畫面則表示，禁用設定沒成功。可能哪裡步驟錯了。
例如下面這樣，就是根本沒有禁用，仍然有風險。
[![失敗](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/360x259/774271984fa2ca523313fefbc347cccc/1466240896526.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/360x259/774271984fa2ca523313fefbc347cccc/1466240896526.jpg)
    - 其他人的教學也可以參考看看：
[勒索軟體預防針，停用 Windows Script Host 功能，不要放棄治療 | 綠色工廠](http://portable.easylife.tw/5016)
4. 內建的開門狗開到最敏感尖叫模式
調整 Windows UAC 開到最高警報程度：
可以多少阻擋一些逾矩行為。
算是加強一些讓使用者有判斷是否應該阻擋的機會。
但這部分要仰賴使用者在 UAC 詢問時的判斷。
如果使用者放病毒去惡搞，還是一樣就會被惡搞。
  - 去控制台，搜尋框搜尋 ``UAC`` 之後就能找到 UAC。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/447x269/f832969547dfa15d587b9217297148b3/1466241345093.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/447x269/f832969547dfa15d587b9217297148b3/1466241345093.jpg)
然後進去把警報敏感度調到最高就可以了。
[![圖](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/509x432/06b61d855db3f51291ea5e051db20f8d/1466241465566.jpg "按圖可放大")](https://trello-attachments.s3.amazonaws.com/576407dffad99c0efbddef10/509x432/06b61d855db3f51291ea5e051db20f8d/1466241465566.jpg)

----

##以上設定方式，主要參考自以下連結的一些技巧。
###技巧有點分散，所以才需要一一整理彙整。
- [Re: \[問題\] 檔案改唯讀，是否可破勒索病毒行為？ - 看板 AntiVirus - PTT](https://www.ptt.cc/bbs/AntiVirus/M.1465260232.A.759.html)
  - 裡面內文跟推文有提供另一種應用方法，開第三個使用者，
只給第三個使用者寫入權限，詳細可進去看敘述。
  - ＰＳ：**檔案改成唯獨確定無法防止病毒，只能防手殘**。
  - [Re: \[問題\] 關於勒索病毒的一點防治想法請教 - 看板 AntiVirus](https://www.ptt.cc/bbs/AntiVirus/M.1465127023.A.96E.html)
  - [Re: \[問題\] 關於勒索病毒的一點防治想法請教 - 看板 AntiVirus](https://www.ptt.cc/bbs/AntiVirus/M.1461847912.A.603.html)
- [\[心得\] 將檔案藏進特殊資料夾躲避勒索軟體的追殺 - 看板 AntiVirus - PTT](https://www.ptt.cc/bbs/AntiVirus/M.1465602889.A.5EB.html)

Attention!!
ＰＳ：**檔案改成唯獨確定無法防止病毒，只能防手殘**。

<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>