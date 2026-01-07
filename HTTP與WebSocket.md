此兩種協議皆為應用層，HTTP 建立在 TCP 之上，WebSocket 建立於 HTTP 之上。

## 一、HTTP
是一種「請求-響應」的過程，例如在瀏覽網頁時，使用者發出了請求(網址)，另一端就回傳網頁內容與狀態 (HTML+CSS+JS, status)，例如常看到的 404 就是其中一種狀態。以下為其中一種請求例子
```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0
Accept: text/html
```
響應
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1234

<html>...</html>
```
狀態有以下幾種
```
1xx → 訊息——請求已被伺服器接收，繼續處理
2xx → 成功——請求已成功被伺服器接收、理解、並接受
3xx → 重新導向——需要後續操作才能完成這一請求
4xx → 請求錯誤——請求含有詞法錯誤或者無法被執行
5xx → 伺服器錯誤——伺服器在處理某個正確請求時發生錯誤
```
HTTP 使用方法除了 GET 外還有以下幾種，RESTful API 就是基於此方法再去撰寫，前後端交換資料很常用到 GET/POST
```
GET → 讀取資源
POST → 建立新資源
PUT → 更新整個資源
PATCH → 更新部分資源
DELETE → 刪除資源
```
特點就是響應完就斷線，若要保持連線，則需要用到 WebSocket。
## 二、WebSocket
