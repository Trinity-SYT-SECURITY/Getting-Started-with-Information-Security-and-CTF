# WEB CTF

[靶機](httpsbwapp.hakhub.net)

[自架環境](https://www.jianshu.com/p/61dfc867d8e8)

![image](https://user-images.githubusercontent.com/96654161/181231178-72cf3bd2-6fe6-47c7-a76a-971427c6a51e.png)

架好的網站畫面

![image](https://user-images.githubusercontent.com/96654161/181231304-5b9eeda3-d0ab-4f18-966d-2fab20bf8059.png)

環境設置
+ 下載burp
+ 下載Firefox
+ 架設靶機

## WEB works
![image](https://user-images.githubusercontent.com/96654161/181234839-280b3c80-fc0c-4fca-b4f2-54615e8fd25b.png)
![image](https://user-images.githubusercontent.com/96654161/181234937-aa5f7602-1fe7-4771-b614-2183ad3b92db.png)

一旦訪問者在瀏覽器的地址欄中輸入您的域名，他們的computer就會發送請求以連接到保存您文件的網絡伺服器。在到達 Web 服務器之前，請求會通過DNS，它會查找服務器的 IP 地址。

DNS 確保瀏覽器連接到正確的服務器。

一切檢查完畢後，服務器就會處理您的網站顯示其內容所需的文件。

Web 瀏覽器“讀取”這些文件（HTML、CSS、圖像和其他文件）並將它們顯示在訪問者的屏幕上。

## HTTP

![image](https://user-images.githubusercontent.com/96654161/181235398-85877f2e-7d3f-4cb4-a23a-e73e4b481c24.png)

作為一種請求-響應協議，HTTP 通過在客戶端和服務器之間傳輸超文本消息，為用戶提供了一種與 HTML 文件等 Web 資源進行交互的方式。HTTP 客戶端通常使用傳輸控制協議 (TCP)連接與服務器進行通信。

HTTP 利用特定的請求方法來執行各種任務。所有 HTTP 服務器都使用 GET 和 HEAD 方法，但並非全部都支持這些請求方法的其餘部分：

+ GET 請求完整的特定資源
+ HEAD 請求沒有正文內容的特定資源
+ POST 將內容、消息或數據添加到現有 Web 資源下的新頁面
+ PUT 直接修改現有的 Web 資源或根據需要創建新的 URI
+ DELETE 刪除指定的資源
+ TRACE 向用戶顯示對 Web 資源所做的任何更改或添加
+ OPTIONS 向用戶顯示可用於特定 URL 的 HTTP 方法
+ CONNECT 將請求連接轉換為透明 TCP/IP 隧道
+ PATCH 部分修改了 Web 資源

![image](https://user-images.githubusercontent.com/96654161/181236133-663cd2a2-8b3a-4467-a956-ba3e2d7d1f9d.png)

+ HTTP請求方法
  + HTTP1.0定義了三種請求方法： GET, POST 和HEAD方法。
  + HTTP1.1新增了五種請求方法：OPTIONS, PUT, DELETE, TRACE 和CONNECT 方法
  + 
## HTTPS
![image](https://user-images.githubusercontent.com/96654161/181236446-65a10ae3-2665-4a52-b8a7-b2b7518ba425.png)

HTTPS 代表安全的超文本傳輸協議。它是一種用於保護兩個系統（例如瀏覽器和 Web 服務器）之間通信的協議

HTTPS 以加密格式傳輸數據。因此，HTTPS 可以防止黑客在瀏覽器和 Web 服務器之間傳輸期間讀取和修改數據。即使黑客設法攔截通信，他們也無法使用它，因為消息是加密的。

HTTPS使用安全套接字層 (SSL) 或傳輸層安全 (TLS) 協議在瀏覽器和 Web 服務器之間建立加密鏈接。TLS 是 SSL 的新版本。

![image](https://user-images.githubusercontent.com/96654161/181236641-13b3cca0-f2a1-44ae-96fa-da40993b8f0b.png)

要使域啟用 HTTPS，必須使用來自受信任的證書頒發機構 (CA) 的 SSL 證書頒發。當 Web 瀏覽器嘗試通過 HTTPS 與服務器連接時，它會檢查 SSL 證書是否與用戶嘗試通過稱為 SSL/TLS 握手的過程輸入的域名匹配。 


## Cookie 
Cookie 是儲存在瀏覽器的一小段文字資料，通常由伺服器透過 `Set-Cookie header` 傳遞給瀏覽器。瀏覽器收到後會將 `cookie` 儲存起來，並在之後的請求回傳 cookie 至同樣的伺服器。

由於有 domain 值的設定，Cookie 是有指定使用範圍的；僅會在請求的目標網域為 Cookie 設定的 domain 時被帶上；透過 domain、path 限縮 Cookie 的使用範圍，以及 Max-Age 指定有效期限，建立在 HTTP 這樣無狀態協議上的應用程式，也就得以獲取、控制使用者狀態了

Cookie 的運作是這樣的：

Server 端回應給 Browser 一個或多個 "Set-Cookie" HTTP Header

Client 端 ( Browser ) 接收到 Set-Cookie 指令時，會將 Cookie 的名稱與值儲存在 Browser 的 Cookie 存放區，並記錄該 Cookie 隸屬的網域、網址路徑、過期時間、是否為安全連線

當 Browser 再次發出 HTTP Request 指令到 Server 時，就會比對目前在 Browser 內的 Cookie 存放區有沒有「該網域」、「該目錄」、「過期時間尚未過期」且「是否為安全連線」的 Cookie，如果有的話就會包含在 HTTP Request 指令的 "Cookie" Header 中。

## Session
一個Session是用於一項活動的總時間。在計算機系統中，用戶Session在用戶登錄或訪問特定計算機、網絡或軟件服務時開始。它在用戶退出服務或關閉計算機時結束。Session可以在連接時臨時存儲與用戶活動相關的信息。會話cookie在網頁中用於存儲信息，以防用戶離開網頁或關閉其 Internet 瀏覽器。例如，這是網站可以記住您離開和回來時購物車中的內容的一種方式。

在計算機編程中，會話變量存儲臨時信息，有時用於檢索和查看多個網頁上的數據。需要用戶名和密碼的網站使用會話變量來幫助在網頁之間傳輸數據，但僅限於用戶登錄到計算機時。

## CTF
### [Information disclosure vulnerabilities](https://portswigger.net/web-security/information-disclosure)

![image](https://user-images.githubusercontent.com/96654161/181240113-b20f94fd-25b5-4b61-bb0c-05ea67dfb1f1.png)

信息洩露，也稱為信息洩露，是指網站無意中向用戶洩露敏感信息。根據具體情況，網站可能會將各種信息洩露給潛在的攻擊者，包括：

有關其他用戶的數據，例如用戶名或財務信息敏感的商業或商業數據關於網站及其基礎設施的技術細節

洩露敏感用戶或業務數據的危險相當明顯，但披露技術信息有時也同樣嚴重。儘管其中一些信息的用途有限，但它可能成為暴露額外攻擊面的起點，其中可能包含其他有趣的漏洞。在嘗試構建複雜的高嚴重性攻擊時，您能夠收集的知識甚至可以提供拼圖的缺失部分。

![image](https://user-images.githubusercontent.com/96654161/181241431-2b866680-7a60-408e-ad6f-7ff97846b6b6.png)


### [Directory Traversal - Files](https://portswigger.net/web-security/file-path-traversal)

![image](https://user-images.githubusercontent.com/96654161/181240420-fdf84038-6299-4cbb-9801-42f9589ea908.png)

目錄遍歷（也稱為文件路徑遍歷）是一種網絡安全漏洞，允許攻擊者讀取運行應用程序的服務器上的任意文件。這可能包括應用程序代碼和數據、後端系統的憑據以及敏感的操作系統文件。在某些情況下，攻擊者可能能夠寫入服務器上的任意文件，允許他們修改應用程序數據或行為，並最終完全控制服務器

+ [Pico - Forbidden Pat](http://saturn.picoctf.net:52683/)

![image](https://user-images.githubusercontent.com/96654161/181242673-62d17702-5bbb-436c-a2b1-2695abac8772.png)

>picoCTF{7h3_p47h_70_5ucc355_e5fe3d4d}

### Information Disclosure - phpinfo

`PHPinfo` 頁面輸出大量關於 PHP 當前狀態的信息。這包括有關 PHP 編譯選項和擴展、PHP 版本、服務器信息和環境、PHP 環境、操作系統版本信息、路徑、配置選項的主值和本地值、HTTP 標頭和 PHP License。

PHP 語言中的`phpinfo()`方法公開了大量關於 PHP、擴展、服務器和環境的信息。由於不同的環境有不同的設置，這`phpinfo()`可以幫助找出配置。它還可以方便調試過程。在生產環境中使用此函數調用可能很危險，因為提供的信息對於攻擊者進行攻擊很有價值。

### Information Disclosure - Special Files 
+ Robots.txt file 
robots.txt 文件用於向網絡機器人（例如搜索引擎爬蟲）提供有關允許或不允許機器人抓取和索引的網站內位置的說明。

robots.txt 的存在本身並不存在任何類型的安全漏洞。但是，它通常用於識別站點內容的受限或私有區域。因此，文件中的信息可能會幫助攻擊者繪製站點的內容，特別是如果標識的某些位置沒有從站點的其他地方鏈接。如果應用程序依賴 robots.txt 來保護對這些區域的訪問，並且沒有對它們實施適當的訪問控制，那麼這會帶來嚴重的漏洞。
+ [Pico CTF where are robots](https://jupiter.challenges.picoctf.org/problem/36474/)

![image](https://user-images.githubusercontent.com/96654161/181245474-5336e1c2-3959-41b1-abbf-c2988727c8c0.png)

![image](https://user-images.githubusercontent.com/96654161/181245423-1f44b5a1-58e5-4d27-a841-b0ca60adbcd7.png)

> picoCTF{ca1cu1at1ng_Mach1n3s_477ce}

### [.git/.svn 資料夾](https://iosentrix.com/blog/git-source-code-disclosure-vulnerability/)
Git 是一個版本控制系統 (VCS)，主要用於在 Web 開發過程中跟踪或監控文件夾或文件的修改。大多數網站管理員更喜歡它，因為它的“分支”功能不僅具有成本效益，而且在管理源代碼版本時也幾乎沒有復雜性。

在 Git 功能和修訂等工具中，控件在 Web 開發階段是必不可少的；每次在任何目錄中初始化 Git 時，它都會啟動本地存儲庫的創建。

在這種情況下，.git 存儲庫是項目中的 .git 文件夾。

它們是跟踪項目中文件或文件夾的所有修改的工具。如果刪除 .git 存儲庫，您可能會丟失所有項目開發歷史記錄。

如果您將 .git 文件夾保留給公眾訪問，它會向互聯網上的每個人提供對您的源代碼的訪問權限，這些人可能能夠獲取代碼中內置的您的知識產權、硬編碼的憑據（如果有的話），並發現其他邏輯缺陷.

![image](https://user-images.githubusercontent.com/96654161/181245082-99151ff2-7f14-4ac0-a0c0-8850ad994abc.png)

### [Insecure Login Forms](https://lockmedown.com/hacking-insecure-login-form/)

### [Insecure Hint & Hardcoded Password](https://cwe.mitre.org/data/definitions/798.html)
通常會造成一個重大漏洞，使攻擊者可以繞過軟件管理員配置的身份驗證。系統管理員可能很難檢測到這個漏洞。即使檢測到，也很難修復，因此管理員可能被迫完全禁用該產品。主要有兩種變化：

入站：該軟體包含一種身份驗證機制，可根據一組Hardcoded的憑據檢查輸入憑據。

出站：軟體連接到另一個系統或組件，它包含用於連接到該組件的Hardcoded憑據。

在 Inbound 變體中，會創建一個默認管理帳戶，並將一個簡單的密碼Hardcoded到產品中並與該帳戶相關聯。該Hardcoded密碼對於每次安裝的產品都是相同的，並且系統管理員通常無法在不手動修改程序或以其他方式修補軟件的情況下更改或禁用該密碼。如果密碼被發現或公開（在 Internet 上很常見），那麼任何知道該密碼的人都可以訪問該產品。最後，由於該軟體的所有安裝都將具有相同的密碼，即使是跨不同的組織，這使得諸如蠕蟲之類的大規模攻擊得以發生。

![image](https://user-images.githubusercontent.com/96654161/181248940-9f4632e5-e74c-4156-85e0-dce2890ac8bc.png)

### Cookie

+ [Pico CTF logon](https://jupiter.challenges.picoctf.org/problem/13594/)

一開始隨便登入

![image](https://user-images.githubusercontent.com/96654161/181251561-16779768-b565-4493-a632-895b8bcbd958.png)

![image](https://user-images.githubusercontent.com/96654161/181251674-b8ebfb8d-3347-49ad-a10f-0ff4ce8543db.png)

把admin=False改True再F5一次

![image](https://user-images.githubusercontent.com/96654161/181251805-298c4410-ef01-446c-ae6c-12ca31b30ee0.png)

> picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}

+ [Hackme CTF dafuq-manager 1](https://dafuq-manager.hackme.quest/)

先用guest / guest登入

![image](https://user-images.githubusercontent.com/96654161/181252990-cbf80348-42e1-4891-b68c-e4239d1ce4ca.png)

登入後只會有這些檔案

![image](https://user-images.githubusercontent.com/96654161/181253415-15673993-188f-47ad-b11c-fe6e1ca71278.png)

按F12在cookie中會看到

![image](https://user-images.githubusercontent.com/96654161/181253540-564a1117-6d15-4d59-b090-aa153b70da0d.png)

把show_hidden=no改true


> FLAG{Wow, how did you found me? I was hidden!}


### Javascript

+ [Pico CTF login](https://login.mars.picoctf.net/)

網站原始碼中有寫個路徑
>https://login.mars.picoctf.net/index.js

![image](https://user-images.githubusercontent.com/96654161/181256208-aae8278d-325f-405a-ae06-c87cda6947a0.png)

查看後發現有個base64編碼的字串

![image](https://user-images.githubusercontent.com/96654161/181256008-5fcb666e-9ebb-47d5-8022-0a8bc2fc1e9c.png)

拿去解碼後

![image](https://user-images.githubusercontent.com/96654161/181256128-8aec3893-3ba2-46b6-a55f-a6073608bb5c.png)

### [Hash、base64](https://dotblogs.com.tw/daniel/2019/05/06/223004)

![image](https://user-images.githubusercontent.com/96654161/181257296-6b999370-bfb1-414c-a73f-5fb9a1f8d17e.png)

編碼是將原本的資料經過一個運算轉換成另一組資料,如果要還原成原本資料解碼

加密可以確保資料的安全性（只有相同的Key才可還原成原本資料）很適合用在機密資料且須要還原使用

![image](https://user-images.githubusercontent.com/96654161/181257500-122c4746-8ba0-4c8d-8104-3c4699c50fbd.png)

Hash有幾個特點

+ 不管資料量多大經過SHA256運算字串長度都是一樣的
+ SHA256的原因是運算完的資料大小一定是 256 bit
+ 他是一個不可逆的算法
+ 相同的值用SHA運算過後值都是一樣的

一般我們可以把使用者密碼經Hash運算存入資料庫中,當作使用唯一識別碼(像指紋)下次使用者登入用運一樣的Hash算法 再將值拿來比較辨識使用者合法性.

![image](https://user-images.githubusercontent.com/96654161/181258066-0c3d6298-b330-4fb0-bb8f-99c0281bd41f.png)

![image](https://user-images.githubusercontent.com/96654161/181258226-3bde436c-b34c-435a-82b4-55cd83986ca7.png)


### BruteForce / Dictionary Attack

Brute-force attack 利用自動化軟件測試大量可能的組合來解碼密碼、個人識別碼 (PIN) 和其他形式的登錄數據

Dictionary attack definition 入侵者試圖通過企業和個人使用的常用單詞和短語的“字典列表”破解受密碼保護的安全系統

攻擊系統最簡單的方法是通過前門，並且必須有某種登錄方式。如果您有憑據，則可以像普通用戶一樣登錄，可能不會生成可疑的日誌條目，從而觸發 IDS簽名，或需要未修補的漏洞。如果您擁有系統管理員的憑據，生活會更加輕鬆。

+ Pico CTF Local Authority

這裡設定要從多少爆破到多少數字的 cookie
![image](https://user-images.githubusercontent.com/96654161/181264765-ca8275e5-5ba8-46d1-b56a-cf7e743ea852.png)


設定要找出的flag格式

![image](https://user-images.githubusercontent.com/96654161/181264366-d0a1b222-4c04-4d57-a67b-63aa9ed84b22.png)

這裡一定要改always

![image](https://user-images.githubusercontent.com/96654161/181264450-f4e3dde9-216a-4cb6-8a77-3310812bb959.png)


先用burp抓需要的資料

![image](https://user-images.githubusercontent.com/96654161/181261111-811d5dd2-5c8e-4a7f-a5fe-ef769a0a0644.png)

再用暴力破解找出cookie

![image](https://user-images.githubusercontent.com/96654161/181264072-116227af-b7cf-4776-a66e-2ffe6dd54d06.png)

找出長度差比較多的

> picoCTF{3v3ry1_l0v3s_c00k135_064663be}
