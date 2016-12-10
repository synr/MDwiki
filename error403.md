<h1 id="show_error_title">剛才的頁面，目前禁止訪問！</h1>
## 請你從正確管道取得相關權限，才能閱讀剛剛的頁面。
### 你怎麼會跳來這裡？
#### 可能有以下原因，最有可能的是 5 ～ 7。

1. 認證已失效，請重新從正確的入口進入。
通常發生在需要認證的頁面，你不能直接透過網址去開啟他。
必須要重新經過認證才能看。
  - 合法認證失效原因可能有：
    1. 重新整理網頁
    2. 你單純複製貼上前往網頁網址，造成沒有經過認證程序。
請改從正確認口，重新進入。
2. 部分頁面~~年久失修~~紀載內容已經不符現代，所以暫時關閉。
  - 如果有人想看會暫時性開放。
3. 因為，有些頁面不開放沒有認證的路人觀看。
4. 因為網頁在維修。
5. 也可能這只是測試頁面，只提供給測試人員測試使用。
如果你是測試人員，應該會拿到通行證。
有通行證就可以順利進來測試內容。
6. ~~簡單說這是一個頁面白名單系統~~，不完全對外公開的頁面需要授權。
7. ~~站長笨蛋~~忘記修應該開放的網站內容。
8. ~~你跟站長一樣手打網址打錯字~~，當然進不來。
9. 你連到已經不存在的幽靈網址

### 我就是想看，怎麼辦？

- 你可以透過以下方式直接連絡到站長本人。
只要你能聯絡到站長，
通常經由站長判斷，有 ~~87% 的可能會放行~~ XD。
  1. 點選網站上方選單（手機版則為螢幕最右上角的三條線）。
  裡面有個「交流」，再點選你想連絡的方式。
  2. 網站右下角，有個類線上即時通訊客服系統。
  這邊可以更直接連絡到站長。
  站長有空的時候你可能看到即時回應。
  3. ~~透過其他你知道的管道找到我，逼問我~~。 



<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>
  
<script type="text/javascript">
  //2016.12.05+ 採集之前的錯誤頁面資訊做出提示。
  if(!((localStorage['error_md'] === undefined)||(localStorage['error_md'] == null)||(localStorage['error_md'] == ''))){
    document.getElementById('show_error_title').innerHTML = '剛才的頁面「' + localStorage['error_md'] + '」，目前禁止訪問！';
    if(!((localStorage['error_url'] === undefined)||(localStorage['error_url'] == null)||(localStorage['error_url'] == ''))){
        document.getElementById('show_error_title').innerHTML = '剛才的頁面「' + localStorage['error_md'] + '」，目前禁止訪問！';
        document.getElementById('show_error_title').innerHTML = '剛才的頁面「' + '<a href=\"' + localStorage['error_url'] +  '\" target=\"_blank\">' + localStorage['error_md'] +  '</a>' + '」，目前禁止訪問！';
    }
  }
  localStorage.removeItem('error_md');
  localStorage.removeItem('error_url');
</script>
