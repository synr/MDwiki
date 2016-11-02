#MDwiki 重點架構檔案

提示！目前只是簡單寫，但重點都會寫出來。

##建構架設前，可以先嘗試了解一下 Markdown。
- 因為這算是完全要用 ``Markdown`` 來寫內容的網站。
所以建議要有一點相關寫法的概念。
當然，如果你就是衝著 ``Markdown`` 而來，你屬於早就熟悉的人。那這些都可以跳過XD

- ``Markdown`` 是一個純文字內容編輯語法。
他的特色是能夠讓使用者更簡單的專注編輯內文，視覺上簡潔方便後續更新維護。
擺脫傳統相關語法會出現前後標籤，造成視覺上不流暢又凌亂又不直覺的缺點。

- 寫法你可以參考中文非官方網站的簡易說明書：[Markdown 語法說明](http://markdown.tw)。
- 英文 OK 的話也可以直接看官方的語法說明：[Markdown: Syntax](http://daringfireball.net/projects/markdown/syntax)。

- 都不想看的話，至少要會超連結的寫法！
個人私心認為 ``Markdown`` 的超連結寫法是很精簡的代表，也是介紹時~~推坑(?)~~的最佳誘因XD
放心，很簡單的！因為 ``Markdown`` 這套內文編輯語法都設計得很直覺。
- ``Markdown`` 超連結的寫法如下：
  - 規則
~~~
[連結文字](連結網址)
~~~
  - 實例
~~~
[Google](http://www.google.com)
~~~
- 無關的宣傳一下，[Trello.com](https://trello.com) 跟 [Plurk.com](http://plurk.com)（噗浪）都支援 Markdown！
如果你不確定喜不喜歡這種寫法，你可以直接在本來就已經支援的網站，先用用看熟悉一下。

----

##靈魂檔案「mdwiki.html」
- 靈魂檔案：從官方下載來的 ``mdwiki.html``，所有運作都經過他。
  - 你可以把它改成像一般網站的慣例檔名 ``index.html``。
如有其他用途，也可以自由設定。
只要自己知道開得到這個網頁就好。
  - 檔案結構上，以 ``mdwiki.html`` 所在的地方為準當作根目錄，
  搭配的 ``*.md`` 檔案要跟他放在同一個資料夾內（包含其中的子資料夾）。
  但 ``mdwiki.html`` 之外的上層資料夾，如果有 ``*.md`` 就不在解析範圍內。

----

##創建重點檔案「index.md」、「navigation.md」與設定檔
###最少要創建「index.md」與「navigation.md」
- 需自創另外無中生有寫出來的 ``.md`` 純文字文件檔：
  - ``*.md`` 可以用相關的通用型純文字編輯器或專門的 Markdown 編輯軟體或線上網站來寫。
例如兼推薦：
    - 編輯程式語言很好用的 [**Sublime Text**](https://www.sublimetext.com) 或類似的純文字編輯軟體。
    - 可線上編輯的網站：[stackedit.io](http://stackedit.io)
    你也可以閱讀資訊，嘗試各種類似網站找到你喜歡的線上編輯網站。
    [七款支援即時預覽的線上 Markdown 文件編輯器 - 玩物尚誌](http://blog.lyhdev.com/2013/12/markdown.html)
  - 也可以單純用記事本寫一寫，存檔後更改副檔名 ``*.txt`` 為 ``*.md``。
  - 儲存的時候使用 ``UTF-8`` 編碼（建議不含 BOM）。
  - 結構上，至少要將下面這兩種檔名的檔案，放在跟 ``靈魂檔案`` 相同的資料夾中。
    - ``index.md``：首頁，內容隨意。
    - ``navigation.md``（非必要，但建議使用）：畫面最上方的連結列。
可以設定單的下拉選單，多層的無法成功。
可能是考慮到手機、平板上多層比較難布置才沒有支援多層選單。
當然，如果你不想要網站出現上放那排連結選單，也可以不要創這個檔案。
``navigation.md`` 內容格式大概這樣
      - 最簡單的基礎的寫法
```
[Home](index.md)
[About](about.md)
```
        - 如果要連結站內的其他 ``*.md`` 文章，相對位子寫法跟絕對位子都可以。
但 MDwiki 不支援回上層的 ``..`` 寫法去解析 ``*.md`` 路徑，所以相對位子會比較不好用。
在多層資料夾的時候，相對位子的寫法很容易出錯。
因此，個人強烈推薦使用絕對路徑的寫法。
        - 絕對路徑的寫法是把「``*.html``」那層資料夾當根目錄，
再根據你分配 ``*.md`` 檔案的資料夾架構去寫。
開頭前面加上 ``#!`` 就表示要使用站內絕對路徑的寫法去連結相關 ``*.md``。
例如：
如果我的 ``about.md`` 放在 ``about 資料夾`` 中的  ``about 資料夾`` 中的  ``about 資料夾`` ，
那就要寫成下面這樣。
```
[Home](#!index.md)
[About](#!about/about/about/about.md)
```
      - 加入左上角標題的寫法（非必要，喜歡再用）
```
#MDwiki 試玩中
[Home](index.md)
[About](about.md)
```
      - 可以再加入單層下拉選單的寫法，[這裡有教](https://blog.ikke.moe/posts/mdwiki-tourial/)。
      - 佈景主題切換功能，也是[這裡有教](https://blog.ikke.moe/posts/mdwiki-tourial/) XD
        - ``[gimmick:themechooser](Theme)`` ：
        增加佈景主題選擇功能，括號內的 ``Theme`` 是按鈕文字。
        像我把它改成「替換佈景主題」。
        - ``[gimmick:theme](cosmo)``：指定第一次來網站的人看到的預設主題。
    - <a href="javascript:window.open(location.href.replace(/(.*)#!.*/,'$1navigation.md'),'_blank');" target="_blank">你也可以直接下載我目前正在使用的這份「navigation.md」文件參考看看。</a>

補充提示：
相關詳細操作方法，暫時直接給其他教學網站的連結XD
如果未來有閒可能會慢慢更新這個頁面，把詳細操作設定都寫進來。
在那之前，請參考本內文提供的各種教學連結XD

<!-- 
    - [你也可以直接下載我目前正在使用的這份「navigation.md」文件參考看看。](https://docs.google.com/uc?id=0B_b1e3AASsaLY2RncExYS0NocXM&export=download)
    - <a href="javascript:window.open(location.href.replace(/(.*)#!.*/,'$1navigation.md'),'_blank');" target="_blank">你也可以直接下載我目前正在使用的這份「navigation.md」文件參考看看。</a>
 -->