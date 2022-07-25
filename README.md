<!-- 上課檔案 https://hackmd.io/KoZmL1CvRKmL5ftEDoHgKQ?both -->

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


#### Username
帳號登入的 username, 長度可以 1 至 32 個字元。

#### Password
這個欄位會用 x 字元代替加密的密碼，而加密的密碼儲存在 /etc/shadow 檔案內。

### id 指令可以用來查詢使用者帳號 ID 與各群組 ID 資訊：
當建立使用者時，會指定使用者 ID 與預設群組 ID，這個使用者 ID 與群組 ID 就是所謂的真實使用者 ID（Real UID，即 RUID）與真實群組 ID（Real GID，即 RGID）。

由於 Linux 系統上的行程可以用其他的使用者或群組權限來執行，所以當程式在執行時可能會以其他的使用者身分來執行，這就是有效使用者 ID（Effective UID，即 EUID）與有效群組 ID（Effective Group ID，即EGID）。在大部分的狀況下，真實與有效的 UID 與 GID 會是一樣的。

若要取得有效的 UID 與 GID，可以使用 -u 與 -g 參數：

+ 有效使用者 ID
`id -u`
>1000
+ 有效群組 ID
`id -g`
>1000

#### User ID (UID)
每個帳號都有一個獨一無二的 user ID (UID), UID 0 是留給 root，而 1 至 99 預留給系統帳號。

#### Group ID (GID)
儲存在 /etc/group 的 primary group ID.

#### Other
Home Directory: 帳號的家目錄。

Shell: 帳號使用的 shell

![](https://i.imgur.com/1gSjfdM.png)
```
root:x:0:0:root:/root:/bin/bash
^    ^ ^ ^ ^    ^     ^
|    | | | |    |     Shell
|    | | | |    家目錄
|    | | | 使用者資訊名欄               
|    | | 初始群組GID                         
|    | UID --------------------------> |___0___|__管理員__|
|    以前密碼欄                          |_1~999_|_系統帳號_|
帳號名稱                                 |_>1000_|一般使用者|
```
[參考資料](https://officeguide.cc/linux-id-command-tutorial-examples/)



### grep
Linux grep 命令用於查找文件裡符合條件的字符串。

grep 指令用於查找內容包含指定的範本樣式的文件，如果發現某文件的內容符合所指定的範本樣式，預設grep 指令會把含有範本樣式的那一列顯示出來。若不指定任何文件名稱，或是所給予的文件名為-，則grep 指令會從標準輸入設備讀取數據。

![](https://i.imgur.com/WqAT0kY.png)

例如在 /etc/os-release 檔案中搜尋 kali 關鍵字

![](https://i.imgur.com/BXXvh4y.png)

執行的結果會列出所有含有關鍵字的整行文字。

grep 亦可搭配萬用字元（*）同時搜尋多個檔案，例如在 /etc/ 目錄之下所有 *.conf 檔案中，尋找 network 這個字眼：

![](https://i.imgur.com/0GNt5Y6.png)

搜尋多個檔案時，在輸出中會標示資料來源是哪一個檔案。

除了搜尋檔案內容之外，亦可搭配管線（pipe）篩選串流資料，例如篩選出含有 network 關鍵字的檔案名稱：

![](https://i.imgur.com/X8Qg3eh.png)

[參考資料](https://www.runoob.com/linux/linux-comm-grep.html)

### head/cat/tail
#### cat
cat（英文全拼：concatenate）命令用於連接文件並打印到標準輸出設備上。

指定一個檔案，輸出內容
![](https://i.imgur.com/LEAglzb.png)

[參考資料](https://www.runoob.com/linux/linux-comm-cat.html)

#### head
head指令會讀取所給予檔案的內容，並將其內容的最前面部份作標準輸出。預設為10行。

看該檔案頭部

![](https://i.imgur.com/fmHIw6U.png)

常用方式:
+ `-c`：--bytes=N 指定輸出開頭的 "N" 個字元組。
+ `-n`：--lines=N 指定輸出開頭的 "N" 行。
+ `-q`： --quiet, --silent 不輸出檔案名稱的標頭。
+ `-v`：一定顯示含有檔案名稱的標頭。

範例：

+ 列出fileA最前面10行內容

`head fileA`

+ 列出fileA最前面20列內容

`head -n 20 fileA`

+ 列出檔案fileA最前面200Bytes內容

`head -c 200 fileA`

#### tail
tail 命令可用於查看文件的內容，有一個常用的參數-f常用於查閱正在改變的日誌文件。

tail -f filename會把filename 文件裡的最尾部的內容顯示在屏幕上，並且不斷刷新，只要filename 更新就可以看到最新的文件內容。

看該檔案尾部
![](https://i.imgur.com/g0JM80F.png)

常用方式:

+ `-n` N:顯示最後 N 行的訊息 (大寫N 為數字)
+ `-f`:持續讀取檔案，直到按 Ctrl + c 為止 (可觀察檔案持續更新的內容)

[參考資料](https://www.runoob.com/linux/linux-comm-tail.html)

### find 
find 的 -type 參數可以指定檔案的類型，常用的選項有：

+ `d`：目錄。
+ `p`：具名的 pipe（FIFO）。
+ `f`：一般的檔案。
+ `l`：連結檔，如果與 -L 或 -follow 參數同時使用時，就只會搜尋到有問題的連結檔，如果想要與 -L 同時使用，請改用 -xtype。
+ `s`：socket 檔案。

指定檔名搜尋

搜尋時是以整個硬碟裡的資料為主

[參考資料](https://blog.gtwang.org/linux/unix-linux-find-command-examples/)

## 搜尋
### locate 
Linux locate命令用於查找符合條件的文檔，他會去保存文檔和目錄名稱的數據庫內，查找合乎範本樣式條件的文檔或目錄。

一般情況我們只需要輸入locate your_file_name即可查找指定文件。

搜尋時是以資料庫檔案裡的資料為主

locate 與find 不同: find 是去硬盤找，locate 只在/var/lib/slocate 資料庫中找。

locate 的速度比find 快，它並不是真的查找，而是查數據庫，一般文件數據庫在/var/lib/slocate/slocate.db 中，所以locate 的查找並不是實時的，

[參考資料](https://www.runoob.com/linux/linux-comm-locate.html)

#### 尋找檔案

使用 `locate` 快速尋找系統上的檔案，例如尋找含有 `.bashrc` 關鍵字的檔案

![](https://i.imgur.com/3Sq1QAr.png)

#### 計算數量

若要計算符合條件的檔案數量，可以加上 `-c`

![](https://i.imgur.com/iy0hV4x.png)

#### 大小寫

locate 在比對檔案時，預設會區分英文字母的大小寫，若不要區分大小寫，可以加上 -i

![](https://i.imgur.com/LHrKEgT.png)

### whereis 
該指令會在特定目錄中查找符合條件的文件。這些文件應屬於原始代碼、二進製文件，或是幫助文件。

該指令只能用於查找二進製文件、源代碼文件和man手冊頁，一般文件的定位需使用locate命令。

![](https://i.imgur.com/lNok4zh.png)
[參考資料](https://www.runoob.com/linux/linux-comm-whereis.html)

### which 
Linux which命令用於查找文件。

which指令會在環境變量$PATH設置的目錄裡查找符合條件的文件。

通常都是用來尋找『執行檔』

![](https://i.imgur.com/9sU78fF.png)

[資料參考](https://www.runoob.com/linux/linux-comm-which.html)

## 解壓縮
![image](https://user-images.githubusercontent.com/96654161/180784999-1171547e-b596-4052-b3d7-1690ecbe8a8f.png)
[參考資料](https://michael-hsu.medium.com/linux-%E5%A3%93%E7%B8%AE%E8%88%87%E6%89%93%E5%8C%85%E6%8C%87%E4%BB%A4-tar-zip-gz-bz2-xz-77ab131c2cc3)

### tar 
tar 是用來建立，還原備份文件的工具程序，它可以加入，解開備份文件內的文件。

# 打包當前資料夾下所有檔案 
$ tar cvf example.tar . 
# 解包 
$ tar xvf example.tar
[資料參考](https://www.runoob.com/linux/linux-comm-tar.html)

### wget 
wget 是一個自動檔案下載工具，在大部份的 Linux 系統上都會內建這個指令，其支援各式各樣的下載方式

+ -t0: 設定重試次數。當連結中斷或超時，wget會重新連接。-t0代表把重試次數設為無窮多。
+ -c:  設定續傳功能。
+ -nH: 不建立該網站名稱的子目錄 /example.com/，而直接在當前目錄下建立鏡像的目錄結構。
+ -np: 不遍歷父目錄，如果有連結連到目標資料夾的parent或其他目錄，不下載。
+ -m:  鏡像，相當同時使用-r和-N。
+ -r:  遞迴下載，把文件中所有的連結都下載回來。
+ -N:  下載時檢查timestamp，只下載有更新的文件，如果檔案大小和最修改日期都一樣就不下載。
+ -P:  指定下載到本機的某個目錄下。

GNU Wget是一個命令行程序，用於從Web下載文件。Wget可以讓您可以使用HTTP，HTTPS和FTP協議下載文件。

wget提供了許多選項，允許您下載多個文件，恢復下載，限制速度，遞歸下載，在後台下載，鏡像網站等等。

wget命令現已預先安裝在大多數Linux發行版上。要檢查

[資料參考](https://www.myfreax.com/usage-of-the-linux-wget-command/)


### 基本下載檔案

![](https://i.imgur.com/OPcA5rw.png)

### 指定儲存的檔名

![](https://i.imgur.com/JTYgBer.png)

### 從檔案中讀取網址

![](https://i.imgur.com/Ismewi2.png)

### ifconfig 
### 基本網路介面

執行 ifconfig 指令不帶任何參數，可以顯示目前主機上已經啟用的網路介面

ifconfig 主要是可以觀察與修改網路介面的相關參數，可以修改的參數很多，包括IP參數以及MTU等等都可以修改。

ifconfig 可以設置網絡設備的狀態，顯示當前的設置。

![](https://i.imgur.com/X6RAjpz.png)

若要查看主機上所有的網路介面（包含未啟用的網路介面），可以加上 -a 參數(本環境已全部啟用)

若要讓 ifconfig 僅顯示簡略的資訊，可以採用 -s 參數

![](https://i.imgur.com/eRsu0tw.png)

### 設定網路 IP 位址、遮罩
ifconfig 指令也可以用來設定網路介面的 IP 位址與網路遮罩，系統管理者在測試或除錯時很常使用。

ifconfig 設定網路介面 IP 位址與遮罩的語法為：

ifconfig 網路介面 IP位址 netmask 遮罩

例如將 eth0 網路介面的 IP 位址從10.0.2.15設定為192.168.0.100，網路遮罩設定為 255.255.255.0，則可執行

![](https://i.imgur.com/v82x6aM.png)

## netstat
Linux netstat 命令用於顯示網絡狀態。

netstat 指令可以讓你了解整個 Linux 系統的網絡情況。

Linux 的 netstat 指令可以用來查詢各種網路相關資訊，檢測各種網路相關的問題。

在 Linux 系統中若要檢查網路相關的問題，netstat 是一個很常使用到的指令之一，雖然他只能在本機執行，但是他可以列出非常多很有用的資訊，像 socket、TCP、UDP、IP 與 ethernet 層的各種資訊都可以利用 netstat 來查詢。

列出所有連接埠（Port）

![](https://i.imgur.com/3SA1zsd.png)

僅列出 TCP 的連接埠：

`netstat -at`

僅列出 UDP 的連接埠：

`netstat -au`

## 列出 Listening 狀態的連接埠

列出所有 listening 狀態的連接埠：

`netstat -l`

列出所有 listening 狀態的 TCP 連接埠：

`netstat -lt`

列出所有 listening 狀態的 UDP 連接埠：

`netstat -lu`

### 統計數據

列出各種協定的統計數據：

`netstat -s`

列出 TCP 的統計數據：

`netstat -st`

列出 UDP 的統計數據：

`netstat -su`

如果要顯示應詳細的統計數據，可以再加上 -w 參數：

`netstat -sw`

## ps 
### 介紹
在Linux中我們可以使用ps指令(Process status)來觀察行程(Process)的資訊，當ps指令不加任何選項時，只會顯示該使用者在當次登入時的資訊：

![](https://i.imgur.com/8MvnC50.png)

PPID:PPID全名是Parent Process ID，是父行程編號代表該行程編號。

![](https://i.imgur.com/scofZer.png)

上圖第二行代表的資訊是ps -f行程，這個行程是由bash行程(PID 312)衍生出來的子行程(PPID 312)，我們可以通常說bash是ps -f的父行程。

ps也可以查看系統行程，我們可以ps指令加上aux選項查看系統行程。

![](https://i.imgur.com/aaod44Z.png)

欄位說明

![](https://i.imgur.com/L2JqGDh.png)

[參考資料](https://david50.pixnet.net/blog/post/45224451-%5B%E7%AD%86%E8%A8%98%5Dlinux%E6%8C%87%E4%BB%A4-ps(process-status))

### 優先權(nice value)
在 Linux 中每個執行中的程式都會有一個 niceness 值，系統的 scheduler 在對每個行程在排程時，就會參考這個數值來決定執行的先後順序，niceness 可用的數值從 -20（最高優先權）到 19（最低優先權），數值越小代表執行優先權越高。

我們可使用"l"參數查看nice值

![](https://i.imgur.com/PKohyPQ.png)
[資料參考](https://blog.gtwang.org/linux/linux-nice-scheduling-priority/)

## kill刪除程序

kill能將目前運作的行程刪除，當kill指令送出訊號收到訊號的行程將依本身訊號值決定是否結束，能否結束還要看行程本身

Linux kill 命令用於刪除執行中的程序或工作。

kill 可將指定的信息送至程序。預設的信息為 SIGTERM(15)，可將指定程序終止。若仍無法終止該程序，可使用 SIGKILL(9) 信息嘗試強制刪除程序。程序或工作的編號可利用 ps 指令或 jobs 指令查看。
[資料參考](https://www.runoob.com/linux/linux-comm-kill.html)

### 若要強制結束可使用語法

kill PID

### 使用行程名稱刪除正在執行的行程 

有時同一程式會同時執行好幾個行程，若使用kill一個一個刪實在太慢也太麻煩了，此時可以使用killall將相同名稱的行桯一次刪除。

語法：killall 行程名稱

## htop 
htop 是另外一個類似 top 的監控工具，它的功能與操作介面比 top 更完整，可以顯示每個程式完整的執行參數，或以行程樹（process tree）的方式顯示，若要管理多個行程時，也可以一次選擇多個行程批次處理。
![image](https://user-images.githubusercontent.com/96654161/180788000-835918d7-0099-4a16-a776-7d42ab8609d7.png)

kali裡預設沒有安裝，需要安裝才能使用

sudo apt-get install htop

![](https://i.imgur.com/IWqclQO.png)

執行 htop 指令之後就會開啟監控畫面

![](https://i.imgur.com/z64hTkE.png)

可以看到每個 CPU 的使用率(6核心16G記憶體)

![](https://i.imgur.com/uWqOcQl.png)

而中間的部份，我們可以使用方向鍵（上、下、左、右）來查看系統上每個行程的資訊，下方有標示從 F1 到 F10 鍵的功能，例如按下 F5 就會以行程樹（process tree）來顯示

![](https://i.imgur.com/PsfJA6U.png)
