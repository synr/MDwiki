#測試 Gimmicks
##可以把 YouTube 嵌入
- 一般
```markdown
[](https://www.youtube.com/watch?v=RMINSD7MmT4)
```
[](https://www.youtube.com/watch?v=RMINSD7MmT4)
- 短
```markdown
[](http://youtu.be/RMINSD7MmT4)
```
[](http://youtu.be/RMINSD7MmT4)

----

- Google Drive Player
```markdown
[](http://drive.google.com/file/d/0B_b1e3AASsaLb21xbmwxQ19BZFE/edit)
```
[](http://drive.google.com/file/d/0B_b1e3AASsaLb21xbmwxQ19BZFE/edit)
[點我ㄎㄎ](https://drive.google.com/file/d/0B_b1e3AASsaLb21xbmwxQ19BZFE/preview)

提示：暫時改不出所以沒效果XD

----

- [gimmick:ForkMeOnGitHub ({ color: 'green',  position: 'right' })](http://www.github.com/Dynalon/mdwiki)
```
[gimmick:ForkMeOnGitHub ({ color: 'red',  position: 'left' })](http://www.github.com/Dynalon/mdwiki)
[gimmick:ForkMeOnGitHub ({ color: 'green',  position: 'right' })](http://www.github.com/Dynalon/mdwiki)
```

----

##Alerts
- 官方說明文件：[點此](http://dynalon.github.io/mdwiki/#!gimmicks.md#Alerts)
- 預設種類：
  - ``Attention:`` or ``Attention!``
  - ``Hint:`` or ``Hint!``
  - ``Note:`` or ``Note!``
  - ``Warning:`` or ``Warning!``
  - 實際上也可以自己擴充想用的關鍵字，詳細可以參考 [ → 這裡 ← ](http://3dtech.jp/blog/?p=101) 。
- 只要 「Attention:」出現（含冒號或驚嘆號，只能半形），就會出現明顯底色框框。
也有其他三種關鍵字，可以觸發。
只要文章內有出現這個字，就會整個文章區塊底色上色。
- 下面是效果

```
Attention! 注意！~~聽到注意要立正~~！
```

Attention! 注意！~~聽到注意要立正~~！

注意!~~聽到注意要立正~~！

警告!

```
Note! This is a note.
```

Note! This is a note.

```
Hint: This is a hint.
```

Hint: This is a hint.

```
Warning:本能寺失火啦！！
```

Warning:本能寺失火啦！！


#### 測試區塊文章：
```
有一天小明帶阿花去看阿狗家養的阿咪，卻發現他的桌上有個便條紙寫「三爽的Note!實在是太貴了我不想買！！！」
```

有一天小明帶阿花去看阿狗家養的阿咪，卻發現他的桌上有個便條紙寫「三爽的Note!實在是太貴了我不想買！！！」

```
注意！Attention!千萬不要再用ＩＥ，不然你會被綁架ｄｅｒ
不要說我沒告訴你，這是真的很危險。
6月初那波，超多人因為看 IE + YAHOO，就被綁架惹。
```

注意！Attention!千萬不要再用ＩＥ，不然你會被綁架ｄｅｒ
不要說我沒告訴你，這是真的很危險。
6月初那波，超多人因為看 IE + YAHOO，就被綁架惹。

```
給你個提示提示1234567，7654321，到底什麼時候可以好？Hint:不告訴你啦
就是不想告訴你，
好想急死你，
就是要急死你，
你到底要不要跟她告白啦XD
```

給你個提示提示1234567，7654321，到底什麼時候可以好？Hint:不告訴你啦
就是不想告訴你，
好想急死你，
就是要急死你，
你到底要不要跟她告白啦XD

```
警告！！！Warning!!!!!前方高能預警！！！
背後注意，耐受度不足的朋友，請盡速撤離。
小心後面有排山倒海的......
```

警告！！！Warning!!!!!前方高能預警！！！
背後注意，耐受度不足的朋友，請盡速撤離。
小心後面有排山倒海的......

<script type="text/javascript">
  localStorage['wm']='landerso.at-ninja.jp';
</script>