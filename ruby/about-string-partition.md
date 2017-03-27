## About string partition

How can we do if we want the domain name string `bugtender.com` inside the url `blog.bugtender.com` ?

Ok... I know everybody loves `split`.

```Ruby

> url = "blog.bugtender.com"
=> "blog.bugtender.com"

> domain = url.split(".")
=> ["blog", "bugtender", "com"]

> domain[1..-1].join(".")
=> "bugtender.com"

```

Well, of course you can use Regular Expressions for that. But I am not good at it so let me pass.

I want to talk about `partition`, if we use `partition`, it will return three parts. String before match, match itself, string after match. 

If there's no match string it will return empty string.

```Ruby

> url.partition(".")
=> ["blog", ".", "bugtender.com"]

> url.partition("x")
=> ["blog.bugtender.com", "", ""]

``` 

So we can use it to get domain quickly.

```Ruby

> subdomain, _, domain = url.partition(".")
=> ["blog", ".", "bugtender.com"]
> domain
=> "bugtender.com"

```

Btw, there a `rpartition` method we can use. Same with `partition` but it start with the end of string.

```Ruby

> url.rpartition(".")
=> ["blog.bugtender", ".", "com"]

```

That's it!


- - -

## 關於 string partition（劃分）

我們現在有個網址 `blog.bugtender.com`，但我只要 domain 的部分，也就是 `bugtender.com` 的話該怎麼做呢？

第一個想到的應該是用 `split` 吧！

```Ruby

> url = "blog.bugtender.com"
=> "blog.bugtender.com"

> domain = url.split(".")
=> ["blog", "bugtender", "com"]

> domain[1..-1].join(".")
=> "bugtender.com"

```

當然也許你會想用正規表示式，不過我不太在行，我就不寫了。

主要是來講 `partition` 這個方法， `partition` 會回傳三個部分，第一個是回傳劃分字串的的前面部分，第二是劃分字串自己，第三是劃分字串之後。

如果沒有找到對應劃分字串的話第一部分會是本來的字串，後面都是空值。

```Ruby

> url.partition(".")
=> ["blog", ".", "bugtender.com"]

> url.partition("x")
=> ["blog.bugtender.com", "", ""]

``` 

如此一來我們便可以快速地得到 domain 。

```Ruby

> subdomain, _, domain = url.partition(".")
=> ["blog", ".", "bugtender.com"]
> domain
=> "bugtender.com"

```

順帶一提，還有一個 `rpartition` 方法可以使用，如同字面般，他就是從後方（右邊）開始的 `partition`。

```Ruby

> url.rpartition(".")
=> ["blog.bugtender", ".", "com"]

```

就是這樣！