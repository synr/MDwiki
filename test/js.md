```javascript
var hello = function () {
    // say hello
    alert('Hello world!');
}
```

```markdown
# MDwiki 試玩中
[MDwiki](index.md)
[魔力寶貝]()

  * #露畢恩島
  * [2016.06.30 改版後開放的新地圖 露畢恩島](cg.md)
  ----
  * #123
  * [2]()
  ----
  * #456
  * [3]()

[測試]()  

  * # YouTube
  * [測試](youtube.md)
  - - - -
  * # 高亮化
  * [Javascript](js.md)
  - - - -
  * # Mac
  * [Post 4](post4.md)

[gimmick:themechooser](替換佈景主題)
- - - - 
[gimmick:theme](flatly)
```

----

###表格測試
- 這部分好像是原本 Markdown 就有，但在 Trello 不能用XD

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

```markdown
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```
- ``-----`` 代表預設的靠左對齊，等同於 ``:-----``
- ``:-----:`` 代表置中對齊
- ``-----:`` 代表靠右對齊

----

##插圖排版
###圖片居於文字左邊
將圖片的鏈接放置在段落文本的正上方，中間不加換行。
```
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
這裡是段落內容，注意兩行中間並沒有任何的換行！
```
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
這裡是段落內容，注意兩行中間並沒有任何的換行！
###圖片居於文字右邊
將圖片的鏈接放置在段落文本的正下方，中間不加換行。
```
這裡是段落內容，注意兩行中間並沒有任何的換行！
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
```
這裡是段落內容，注意兩行中間並沒有任何的換行！
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
###圖片與文字無關
只需要在文字與圖片之間加上換行即可。
```markdown
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)

這裡是段落內容，注意兩行中間有換行！
```
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)

這裡是段落內容，注意兩行中間有換行！
###圖片並排
兩張圖片的鏈接並列，中間沒有換行。

![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
```
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
![](http://www.squishable.com/mm5/graphics/00000001/gopher_understudy.jpg)
```

<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>