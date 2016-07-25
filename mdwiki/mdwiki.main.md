#MDwiki 重點架構檔案
##靈魂檔案「mdwiki.html」
- 靈魂檔案：從官方下載來的 ``mdwiki.html``，所有運作都經過他。
  - 你可以把它像一般網站的慣例，更名為 ``index.html``。
如有其他用途，也可以自由設定。
只要自己知道開得到這個網頁就好。

##創建兩個重點檔案：「index.md」與「navigation.md」
- 需自創另外無中生有寫出來的 ``md`` 部分：
  - ``*.md``，可以用相關的純文字編輯器來寫。
也可以單純用記事本寫一寫，更改副檔名 ``*.txt`` 為 ``*.md``。
儲存的時候使用 ``UTF-8`` 編碼。
  - 結構上，至少要將下面這兩種檔名的檔案放在跟 ``靈魂檔案``，相同的資料夾中。
    - ``index.md``：首頁，內容隨意。
    - ``navigation.md``：畫面最上方的連結。
內容格式大概這樣
      - 最簡單的
```
[Home](index.md)
[About](about.md)
```
``*.md``用相對位址的寫法比較好。
      - 加入左上角標題的寫法
```
#MDwiki 試玩中
[Home](index.md)
[About](about.md)
```
      - 可以再加入下拉選單的寫法，[這裡有教](https://blog.ikke.moe/posts/mdwiki-tourial/)。
      - 佈景主題切換功能，也是[這裡有教](https://blog.ikke.moe/posts/mdwiki-tourial/) XD
        - ``[gimmick:themechooser](Theme)`` ：
        增加佈景主題選擇功能，括號內的 ``Theme`` 是按鈕文字。
        像我把它改成「替換佈景主題」。
        - ``[gimmick:theme](cosmo)``：指定第一次來網站的人看到的預設主題。
    - [你也可以直接下載我目前正在使用的這份「navigation.md」文件參考看看。](https://docs.google.com/uc?id=0B_b1e3AASsaLY2RncExYS0NocXM&export=download)
    