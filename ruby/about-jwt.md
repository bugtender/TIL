## Aboud JWT

JWT(JSON Web Token). A stateless and small size token.

We can use JWT for prevent CSRF Attack.

If we use JWT, client side will not saving user data, and server just need to authorize the token. Make conneting more easy !

A real JWT I use in my side project:

>eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiOTEzYzM4Y2MtZTdmZC00ZjUwLThlNWUtNzg1NmI1ZTE3OTZhIn0.rNBFFSIXYJOZS8Sa3ITw_4mQjM_16x7lqUmTxuhzwjs

There's three part split by `.`. It's call Header, Payload and Signature.

- Header

Header inclued the information like `Hey I am a JWT.` and which algorithm used in this JWT.

- Payload

Including some information you want JWT carring. But others can decode this part so please don't put the security thing in.

- Signature

To create the this part you have to take the encoded `Header`, the encoded `Payload`, a secret, the algorithm specified in the `header`, and sign that.

OK, we can authorize by JWT now. Pretty clean and easy. uh?

[Ref](https://jwt.io/)

- - -

## 關於 JWT

在寫 React 登入的時候學到的東西，因為之前登入都是用 Rails + devise 去作呵呵。

JWT 全名 JSON Web Token，特色就是無狀態(stateless)、輕薄短小，可以塞 HTTP Header，還可以在其中塞一些不影響安全的資料。

主要可以解決的是防止以前登入方式的一些攻擊漏洞（CSRF Attack），還有 Session 本身具有狀態性。

使用 JWT 之後，client 端這邊不用儲存用戶訊息， server 端也因為只要驗證 JTW 省去很多多重登入要解決的問題。 

下面就是一個我在測試用的 JWT ：

>eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiOTEzYzM4Y2MtZTdmZC00ZjUwLThlNWUtNzg1NmI1ZTE3OTZhIn0.rNBFFSIXYJOZS8Sa3ITw_4mQjM_16x7lqUmTxuhzwjs

我們可以看到 JWT 本身可以用 `.` 切成三個部分，第一部分我們稱它為 Header ，第二部分 Payload ，第三部分是 Signature 。

- Header

通常 Header 裡面放的資訊是聲明我是 JWT 還有我這個 JWT 是用什麼算法包裝的

- Payload

就是你要用 JWT 帶著的消息，這部分是可以反解出來的，所以建議不要放危害安全的資訊在這裡。

- Signature

這邊的生成需要 hash 過的前面兩項再加上我們的私鑰還有在 Header 提到的算法算成，主要用途當然就是驗證啦！

用法就是客戶登入之後，server 驗證成功給予合法 JWT，之後各種溝通都帶著 JWT 就沒有問題了。  


[Ref](https://jwt.io/)