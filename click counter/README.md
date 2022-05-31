# Click counter 敲擊計數器
首次學習kotlin的第一個練習
> 目的:學習var關鍵字運用  
  findViewById物件抓取  
  UIButton的應用  
  text的設定  
  setOnClickListener監聽運用  
  
## APP功能介紹
點擊PUSHME開始計數
點擊RESTART則重新計數  

<img width="250" alt="1" src="https://user-images.githubusercontent.com/106436314/170830843-cf50c83b-1198-4e63-aae3-270d953b1237.jpg">

## DEMO影片  
![Uploading Record_2022-05-29-16-10-10_3e90b8aa1fd0617ad35224c1a9dd01bd_.gif…]()

* findViewById物件抓取
```
val tip: Button=findViewById(R.id.button)
val re: Button =findViewById(R.id.button2)
val cc: TextView =findViewById(R.id.count2)
val count:TextView = findViewById(R.id.count1)
```
* text設定
```
tip.text="pushme"
re.text="restart"
cc.text="Count"
```
* 設定計數一開始為0
```
var clickcount=0
```
* PUSHME監聽(Button觸發後執行的動作)
```
tip.setOnClickListener{
    clickcount++
    count.text="$clickcount"
        }
```
* RESTART監聽(Button觸發後執行的動作)
```
re.setOnClickListener{
   clickcount=0
   count.text="$clickcount"
        }
```
目前是剛開始學，因此對語法及型態等等方面還不夠熟悉
之後再繼續努力多加練習
