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
+ `-l` 參數可以顯示檔案與目錄的詳細資訊
+ `-S` 可以讓檔案依照檔案的大小來排序
+ `-a` 參數可以顯示隱藏的檔案與目錄
+ `-h` 參數可以讓輸出的資訊以比較容易閱讀的格式呈現
+ `-F` 參數可以讓檔案名稱的後面加上檔案類型的標示字元
+ `-r` 參數可以讓檔案的列表以反向的排序列出
+ `-R` 參數可以靠遞迴的方式列出所有子目錄的檔案
+ 若要讓檔案依照時間排序，讓最新的檔案排在最後，可以使用 `-ltr`
+ 每個檔案都有一個 inode 屬性，若要列出每個檔案的 inode，可以使用 `-i` 參數
+ `--version` 參數可以輸出 ls 版本資訊
+ `-d` 參數可以讓 ls 只列出目錄
+ `-n` 參數可以讓 ls 顯示使用者的 UID 與群組的 GID 值

[參考資料](https://blog.gtwang.org/linux/linux-ls-command-tutorial/)

### cd 
![](https://i.imgur.com/GlVWPkp.png)
用 cd 指令，從您目前的目錄移動至其他目錄。您必須具有指定目錄中 的執行（搜尋）許可。

如果未指定 Directory 參數，則 cd 指令會將您移至您的登入目錄（ksh 及 bsh 環境中的 $HOME，或 csh 環境中的 $home）

Linux cd（英文全拼：change directory）命令用於切換當前工作目錄。

其中dirName 表示法可為絕對路徑或相對路徑。若目錄名稱省略，則變換至使用者的`home` 目錄(也就是剛login 時所在的目錄)。

另外，`~`也表示為`home` 目錄的意思，`.`則是表示目前所在的目錄，`..`則表示目前目錄位置的上一層目錄。

![](https://i.imgur.com/a0U27eo.png)

[參考資料](https://www.runoob.com/linux/linux-comm-cd.html)

### mkdir 
mkdir是Linux常用的一條基本命令，表示如果當前路徑下不存在該目錄(文件夾)，則新建該目錄(文件夾)。其語法結構如下：

默認情況下會將新建的目錄權限設置未rwxrwxr-x，如果想設置其他權限，選項可以採用-m，例如

`$ mkdir -m 777 test`

建立一個名為 hello 的目錄

![](https://i.imgur.com/G5rZ2jz.png)

必定建立資料夾 (如果路徑中沒有前n層資料夾，會自動建立)

`mkdir -p ./path/FolderName`

[參考資料](https://www.ibm.com/docs/zh-tw/aix/7.1?topic=directories-creating-mkdir-command)

### cp

CP是Linux(Unix Like)常用使用命令之一，用來複製檔案與目錄。
+ -a：除了具有-p參數功能外，還能加入SElinux屬性
+ -i：如果要複製過去的位置已經有相同檔案，會在覆蓋前詢問是否持續進行
+ -p：將檔案本身屬性(權限、所有者、時間)同時複製過去(一般用於備份居多)
+ -r：針對目錄下檔案做遞歸複製(白話：整個目錄下每一個檔案複製到你想要的位置)
+ -s：複製成符號連結檔(symbolic link)(白話：複製成捷徑檔)

範例1：將from.txt檔案從user1目錄，複製到user2目錄下，並改名為meow.txt

`cp /user1/from.txt /user2/desktop/meow.txt`

範例2：將frome目錄下，user1目錄夾連同檔案整個複製到to目錄

`cp -r /from/user1 /to/`

範例3：將source目錄下，user目錄夾連同檔案與屬性整個備份到backup目錄

`cp -rp /source/user1 /backup/` 

範例4：複製多個檔案到to目錄夾

`cp  user1.txt user2.txt /to/` 

範例5：利用萬用符號*複製多個符合.mp3檔案到to目錄夾

`cp  /from/*.mp3 /to/` 

> 補充說明：像是特殊權限檔案(/etc/shadow)，密碼檔、設定檔、…等，需要加上-a或-p參數，才能完整複製檔案。如果複製過程希望有進度條功能，建議改用scp或rsync指令

### rm
rm是Linux(Unix Like)常用使用命令之一，用來刪除檔案與目錄。

+ `-f`：force=>強制(強迫武力)，使用時不會出現警告訊息，會自動忽略不存在的檔案。
+ `-i`：進行檔案刪除前，會詢問是否確認要刪除。
+ `-r`：針對目錄及底下檔案做遞歸刪除。(白話：把整個目錄跟檔案都砍掉)

範例1：將tmp目錄底下的killme.txt檔案刪除

`rm /tmp/killme.txt`

範例2：將tmp目錄底下的test目錄與檔案刪除

`rm -r /tmp/test`

範例3：將tmp目錄底下的info刪除，刪除前會詢問

`rm -i /tmp/info`

範例4：強制將tmp目錄底下的任何屬於mp3檔案刪除，刪除時不會詢問

`rm -f /tmp/*.mp3`

想不開想砍掉整個根目錄, 可以用以下兩種指令:
```
rm -rf –no-preserve-root /
或
rm -rf /*
```

### 重導向(>)與管道(|) 

最典型的程式會將程式執行的結果輸出在螢幕上（也就是說標準輸出預設就是螢幕），而我們可以使用 `>` 這個重新導向的運算子，將程式的標準輸出導向檔案，這樣輸出的訊息內容就會被儲存在檔案中，其用法為：

 `ls > output.txt`
這樣就會把` ls `指令的輸出儲存至 `output.txt `檔案中，而執行這行指令時，螢幕上就不會有其他的輸出了。

如果 output.txt 這個檔案不存在的話，就會自動建立這個檔案，並把資料寫入其中。但若是這個檔案已經存在了，系統會把它的內容先清空，再將 `ls` 的輸出儲存進去，所以如果原本 `output.txt` 檔案中存在有舊的資料，就會全部被清掉。

 `date >> output.txt`

這樣一來，他就會在 output.txt 檔案中，於原本的 ls 輸出之後，再加上一行日期資訊。

若程式發生錯誤時，錯誤訊息預設也是會輸出在螢幕上（標準錯誤輸出預設為螢幕），例如：

 `ls non_exist > output.txt`
這裡我們使用 ls 查看一個不存在的檔案，讓它產生錯誤，執行之後會在螢幕上看到一行錯誤訊息：

`ls: non_exist: No such file or directory`

這一行就是來自於` ls `標準錯誤輸出的訊息，而 `output.txt` 這個輸出檔案也會被建立，不過它的內容是空的（因為程式沒有產生任何正常的輸出）。

如果我們想要把程式的錯誤訊息導入檔案，可以使用 > 運算子，把標準錯誤輸出（2）導至指定的檔案：

 `ls non_exist &> output.txt`

要把兩個程式的輸入與輸出串接起來，就可以使用管線（pipe）。

`ls | nl`

`nl` 這個指令會把每一行資料加上行號，這一指令會將 ls 的輸出導給 nl，讓每個檔案名稱加上行號後，輸出在螢幕上。

管線與重新導向可以混用：

`ls | nl > output 2>&1`
串接多個程式的狀況也是很常見的：

`ls | grep keyword | nl | head -n 5`
這個例子是在 ls 的輸出中，以 grep 篩選出有 keyword 的檔名，交給 nl 加上行號，最後交給 head 輸出前 5 行資料

[參考資料](https://blog.gtwang.org/linux/linux-io-input-output-redirection-operators/)


## 檔案權限
Superuser 不受權限規範
因 Linux 是多人多工(multi-tasking,multi-user)的作業系統,也就是可很多人使用,所以一定要有某種機制來適當的隔離不同登入者檔案的讀、寫、執行和刪除,甚至是進入某個目錄,這種安全機制就是檔案的〝擁有者〞(ownership)和〝權限〞(permission)。

目錄的權限和檔案的權限功能有些不一樣,如下表:
![image](https://user-images.githubusercontent.com/96654161/180779209-8e4b5b55-7a5f-4a43-97e7-26fe970ed949.png)

指令 `chmod (change mode)`可改變檔案和目錄的權限和特殊權限,只有該檔的擁有者和〝root〞有權去更動其權限。

chmod 可接受〝數字表示法〞(Numberic representation)和〝符號表示法〞(Textual representation),這兩種用法的使用者比例旗鼓相當。數字表示法比較簡短,但如非工科的人員可能會對〝十進制轉二進制〞感到頭大,而符號表示法寫起來可能比較冗長。

![image](https://user-images.githubusercontent.com/96654161/180779641-91a5d45d-d895-4ca1-bfb0-107b8107a458.png)
![image](https://user-images.githubusercontent.com/96654161/180779707-5276395b-f886-4930-8dcb-c4e267da5e9e.png)

[資料參考](https://www.hy-star.com.tw/tech/linux/permission/permission.html#dir_permission)

#### user 擁有者
預設的情況,檔案由那一帳號建立的,誰就是那檔案的使用者 (user )和擁有者(owner),故 user 也叫 owner,而只有檔案的擁有者和〝root〞,可自由的更改其權限。

#### group 群組
一至多個使用者帳號者可組成一團體即 group (群組),可類比為公司的部門或學校的班級或社團等,要怎麼組成一群組可自行規劃。當然也可一個帳號同時加入多個群組,檔案/目錄若屬某一群組所有,可設定若干的群組管理來規範。通常新建一帳號時會同時建立一個和帳號同名的群組,如想知自己的群組帳號名稱可用指令 groups 來查詢。
other 其他沒規範在 owner 和 grouop 的都算是〝other〞(其他)。

Linux 登入的時候實際上有兩個身份,一個是登入者(user)另一是伴隨登入者的群組(group),而如有建立檔案,此檔會記錄這兩個身份。

![](https://i.imgur.com/0xgO2Mk.png)
> 前面的osboxes士user 後面的士group

