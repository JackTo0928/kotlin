# GuessNumber 終極密碼
首次學習kotlin的第二個練習
> 目的:學習editTextNumber運用    
  if else條件式運用  
  資料型態轉換練習  
  多個UIbutton設定  
  防呆設定  
  
## APP功能介紹
點擊GUESS開始遊戲  
數字設定為0~200隨機產生亂數  
當輸入為空值或是值不在範圍0~200內時下方訊息顯示Wrong number!  
App剛開始執行會先判斷有無空值以及有無超過範圍後才開始進行比較  
當輸入的值小於Answers時訊息顯示input Higher~  
當輸入的值大於Answers時訊息顯示input Lower~  
當輸入正確Answers時訊息顯示Good Puppy!  
點擊HEHE則會公布Answers  
點擊RESTART則重新開始遊戲  

<img width="250" alt="1" src="https://user-images.githubusercontent.com/106436314/170830843-cf50c83b-1198-4e63-aae3-270d953b1237.jpg"><img width="250" alt="1" src="https://user-images.githubusercontent.com/106436314/170830843-cf50c83b-1198-4e63-aae3-270d953b1237.jpg">

## DEMO影片  
<img width="250" alt="123" src="https://user-images.githubusercontent.com/106436314/171168349-0cbfbdb5-f1fa-49a5-9aed-3b44454c8a70.gif">

* findViewById物件抓取
```
val re: Button =findViewById(R.id.button)
val guess: Button =findViewById(R.id.button2)
val hehe: Button =findViewById(R.id.button3)
val num: TextView =findViewById(R.id.textView)
val gue: TextView = findViewById(R.id.textView2)
val ans: TextView = findViewById(R.id.textView3)
val yans: TextView = findViewById(R.id.editTextNumber)
val kk: TextView = findViewById(R.id.textView4)
```

* text設定
```
re.text="restart"
guess.text="guess"
hehe.text="HeHe"
num.text="Number"
gue.text="Your Guess:"
kk.text="Welcome!"
```

* 設定Answers以及我們輸入的值
```
var A:Int=0
var In=yans.text
A=(0..200).random()
In=""
```

* GUESS監聽(Button觸發後執行Guess function)
```
guess.setOnClickListener{
       Guess()
        }
```

* Guess function副程式
```
fun Guess(){
    if("".equals(yans.getText().toString().trim())){
       kk.text="Wrong number!"
       yans.text=""
       }
    else{
         var In = Integer.parseInt(yans.getText().toString())
         if(In<0||In>200){
         kk.text="Wrong number!"
         yans.text=""
         }
         else{
              if(In>A){
                  kk.text="input Lower~"
                  yans.text=""
                  }
              else if(In<A){
                  kk.text="input Higher~"
                  yans.text=""
                  }
              else{
                  kk.text="Good Puppy!"
                  yans.text=""
                  }
             }
         }
     }
```

* HEHE監聽(Button觸發後執行的動作)
```
hehe.setOnClickListener{
      ans.text="$A"
      }
```


* RESTART監聽(Button觸發後執行的動作)
```
re.setOnClickListener{
    A=(0..200).random()
    yans.text=""
    ans.text=""
        }
```

本次學習在資料型態轉換及防呆設定(讓App剛開始先偵測防輸入空值以及輸入超過範圍以防會閃退的情況)方面還不夠掌握，今後會再多加努力練習。

