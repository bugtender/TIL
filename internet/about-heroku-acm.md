## About Heroku ACM and Cloudflare

> ACM = Automated Certificate Management

I upgrade my Heroku Rails App on `bugtender.com` to hobby dyno with Let's Encrypt SSL.

Feel goooood ~ and the SSL setting is amazing easy.

Few days ago I want to publish my blog site with GitHub Page on `blog.bugtender.com`.

But you can't use github free SSL if you let your page with custom domain.

So we use Cloudflare for blog's SSL.

Only one thing you need to notice is that the `bugtender.com` record only work on `DNS Only` status. The guide is [here](https://kb.heroku.com/how-can-i-use-automated-certificate-management-with-cloudflare).

| Name          | Type  | Value         |  Status                  |
| :------------ |:----- | -------------:| ------------------------:|
| www           | CNAME |          to @ | DNS and HTTP Proxy (CDN) |
| bugtender.com | CNAME | to Heroku DNS |                 DNS Only |
| blog          | CNAME |  to gitHub.io | DNS and HTTP Proxy (CDN) |

That's it. Feel gooood.

- - - 

## 有關 Heroku ACM 與 Cloudflare

因為感覺 Heroku 的 Let's Encrypt SSL 有點酷（不是免費啦要用 Hobby Dyno）

所以就花了點小錢把 `bugtender.com` 這個 Rails App 升級了，

Heroku SSL 的設定簡單到我就不多說了，因為就是去 Setting 裡面開啟，

但最近想要把之前的 blog 用 subdomain 掛著 `blog.bugtender.com` ，

而他是使用 GitHub Page ，因為 GitHub Page 用 custom domain 就不能用內建的免費 SSL，

所以這邊就要轉用 Cloudflare 發的 COMODO SSL 的，

其實整個設定也不算太麻煩，要注意的點只有 Cloudflare 指向 Heroku 時不能用預設亮燈的 `DNS and HTTP Proxy (CDN)` 要用灰色的 `DNS only` ，因為會打架造成 Heroku 看不到她自己發的 SSL ，就會一直發信提醒你警告你沒設定好，官方說明在[這裡](https://kb.heroku.com/how-can-i-use-automated-certificate-management-with-cloudflare)。

| Name          | Type  | Value         |  Status                  |
| :------------ |:----- | -------------:| ------------------------:|
| www           | CNAME |          to @ | DNS and HTTP Proxy (CDN) |
| bugtender.com | CNAME | to Heroku DNS |                 DNS Only |
| blog          | CNAME |  to gitHub.io | DNS and HTTP Proxy (CDN) |

這樣去檢查的話 `bugtender.com` 就會是 Let's Encrypt 而 `blog` 就是 Cloudflare 的 COMODO 了。
