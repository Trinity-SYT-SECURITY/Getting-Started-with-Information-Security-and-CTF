如果要塞flag的話..

![image](https://user-images.githubusercontent.com/96654161/182135844-c2240eeb-b33d-4921-bf3e-9916baa374b4.png)


### HTTP Header 竄改

這題要通過竄改User-Agent

![image](https://user-images.githubusercontent.com/96654161/182141988-573330f4-abf9-4d66-b74f-1c8067f3c15f.png)

https://www.whatismybrowser.com/guides/the-latest-user-agent/android

拿其中一個測試，對User-Agent做更改

`Mozilla/5.0 (Linux; Android 12) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.5060.129 Mobile Safari/537.36.`


![image](https://user-images.githubusercontent.com/96654161/182141636-cfd96b9c-fd4c-43df-b432-a52f047b31bb.png)

![image](https://user-images.githubusercontent.com/96654161/182141683-1a8a14c3-8bcd-444f-b3c9-b4e2534bc758.png)

### Injection
攻擊者透過輸入資料內加入惡意語句，改變網站行為，達到惡意目的

+ OS Command Injection
  + 後端直接丟給 Shell 處理
  + 可以在正常輸入後面走私其他 Shell Script 進去讓他執行
  + 善用 `|` 、 `||` 、 `&` 、 `&&` 、 `;` 、 `>` 、 `$()` 、 ` 、 `#` 、 `${IFS}` 、去掉空白等等手法繞過檢查
![image](https://user-images.githubusercontent.com/96654161/182142877-9e93acea-6242-4a8d-ae21-e7ceae12cc5a.png)

![image](https://user-images.githubusercontent.com/96654161/182145372-4f0b7aed-0bd4-4d6f-95a9-24f50b9b306e.png)

+ SQL Injection
  + 後端拿使用者輸入的資料做 SQL 查詢
  + 後端將攻擊者挾帶進去的 SQL 語句當作正常 SQL 語句的一部份，改變原本 SQL 查詢行為
