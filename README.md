## CTF introduce

+ Capture The Flag 奪旗遊戲
+ 透過**合法環境**切磋駭客攻防技術的競賽
+ 以各種資安手段奪取 / 防禦 Flag
+ 一串字串,拿到就能得分
+ 通常有固定格式,可能像是`FOO{bar_123_anything}`
+ 也可能沒有明顯格式,像是`U82q5TCMMQ9xuFoI3dYX61s7OZ`

### Web 網站安全
對於網頁運作原理、各種網頁語言、框架都要有初步了解

### Reverse 逆向工程
+ 給你一個編譯好的執行檔,要你分析將其破解或找出隱藏的 flag
+ 考驗對於反組譯以及堆蹤分析程式碼、組合語言等能力

### Crypto 密碼學
+ 給你一個加密過的訊息,要你還原出明文
+ 考驗對於密碼學、加密演算法的熟悉程度

### Pwn 程式安全
+ Pwn (Penetration and Own )
+ 給你一個運行有弱點的服務,要你建構惡意的輸入,改變程式行為或流程,進而取得伺服器控制權
+ 同樣需要對於程式底層知識有足夠了解

### Forensics 數位鑑識
+ 封包分析、 log 分析、檔案分析、 Memory Dump 等等
+ 考驗各種偵蒐、取證的能力

### Misc 雜項
+ 其他無法歸類於前面項目的題形
+ 也有可能是前面項目的綜合
+ 或是腦洞大開的通靈題

## 練習平台
+ Pico CTF https://picoctf.org/
+ CTF Learn https://ctflearn.com/
+ Overthewire https://overthewire.org/wargames/
+ PwnableKr https://pwnable.kr/
+ PwnableTw https://pwnable.tw/
+ Hacker101 https://ctf.hacker101.com/
+ Bugku https://ctf.bugku.com/
+ Hackerone https://www.hackerone.com/
+ hackme https://ctf.hackme.quest/

## 學習資源
+ Got Your PW 資安資源與工具整理 https://gotyour.pw/
+ Bamboofox 學習資源 https://bamboofox.cs.nctu.edu.tw/
+ SCIST 課程資源 https://www.youtube.com/playlist?list=PLN7NYsAnUHW4sTY8fbSsn6BfM7uXfk5I4

## linux 介紹
```
linux 主機：
ssh guest@140.117.169.217 -p 5532
密碼： isctest
```

### ls
ls 直接執行 ls 帶任何參數的話，會列出目前目錄中的檔案與目錄列表。
![](https://i.imgur.com/1BZuHRL.png)
+ `-l` 參數可以顯示檔案與目錄的詳細資訊。
+ `-S` 可以讓檔案依照檔案的大小來排序
+ `-a` 參數可以顯示隱藏的檔案與目錄。
+ `-h` 參數可以讓輸出的資訊以比較容易閱讀的格式呈現。
+ `-F` 參數可以讓檔案名稱的後面加上檔案類型的標示字元。
+ `-r` 參數可以讓檔案的列表以反向的排序列出。
+ `-R` 參數可以靠遞迴的方式列出所有子目錄的檔案。
+ 若要讓檔案依照時間排序，讓最新的檔案排在最後，可以使用 `-ltr`
+ 每個檔案都有一個 inode 屬性，若要列出每個檔案的 inode，可以使用 `-i` 參數
+ `--version` 參數可以輸出 ls 版本資訊。
+ `-d` 參數可以讓 ls 只列出目錄
+ `-n` 參數可以讓 ls 顯示使用者的 UID 與群組的 GID 值

[參考資料](https://blog.gtwang.org/linux/linux-ls-command-tutorial/)



### cd 
![](https://i.imgur.com/GlVWPkp.png)
一開始在osboxes目錄下，因此單純使用 ls 時，會列出工作目錄底下的資料(Desktop Documents等等)亦即是一堆目錄下應該會存在的目錄名稱。 而當讀者操作『 cd /usr 』之後，工作目錄會變成該目錄usr，所以提示字元裡面也將 ~ 變成了 usr 了，並且顯示目錄下應該會存在的目錄名稱。
![](https://i.imgur.com/a0U27eo.png)








