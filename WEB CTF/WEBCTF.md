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

## HTTPS
![image](https://user-images.githubusercontent.com/96654161/181236446-65a10ae3-2665-4a52-b8a7-b2b7518ba425.png)

HTTPS 代表安全的超文本傳輸協議。它是一種用於保護兩個系統（例如瀏覽器和 Web 服務器）之間通信的協議

HTTPS 以加密格式傳輸數據。因此，HTTPS 可以防止黑客在瀏覽器和 Web 服務器之間傳輸期間讀取和修改數據。即使黑客設法攔截通信，他們也無法使用它，因為消息是加密的。

HTTPS使用安全套接字層 (SSL) 或傳輸層安全 (TLS) 協議在瀏覽器和 Web 服務器之間建立加密鏈接。TLS 是 SSL 的新版本。

![image](https://user-images.githubusercontent.com/96654161/181236641-13b3cca0-f2a1-44ae-96fa-da40993b8f0b.png)

要使域啟用 HTTPS，必須使用來自受信任的證書頒發機構 (CA) 的 SSL 證書頒發。當 Web 瀏覽器嘗試通過 HTTPS 與服務器連接時，它會檢查 SSL 證書是否與用戶嘗試通過稱為 SSL/TLS 握手的過程輸入的域名匹配。 
