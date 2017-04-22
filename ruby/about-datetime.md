## About DateTime

I found this interesting thing when I translate [Ruby style guide in Traditional Chinese](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhTW.md) .

In short, Ruby can calculate date for historical calendar reform.

#### [Miguel de Cervantes](https://en.wikipedia.org/wiki/Miguel_de_Cervantes) 
  - He wrote the Don Quixote.
  - He die in 23 April 1616.

#### [William Shakespeare](https://en.wikipedia.org/wiki/William_Shakespeare) 
  - He wrote a lots of book. 
  - He die in 23 April 1616.

We can found that they die in same day.

But, Cervantes lives in Italy and Shakespeare lives in England. 

The true is, Shakespeare died after Cervantes about 10 days.

```Ruby
  > shakespeare=DateTime.iso8601('1616-04-23',Date::ENGLAND)
  => #<DateTime: 1616-04-23T00:00:00+00:00 ((2311415j,0s,0n),+0s,2361222j)>
  > cervantes=DateTime.iso8601('1616-04-23',Date::ITALY)
  => #<DateTime: 1616-04-23T00:00:00+00:00 ((2311405j,0s,0n),+0s,2299161j)>

  > shakespeare == cervantes
  => false

  > (shakespeare-cervantes).to_i
  => 10
```

- - - 

## 關於 DateTime

在翻譯 [Ruby style guide 繁體中文版](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhTW.md) 的時候發現的。

簡單來說，Ruby 遇到以前的曆法是可以指定並且做運算的。

我們找兩個歷史人物：

#### [米格爾•德•塞萬提斯•薩維德拉](https://zh.wikipedia.org/wiki/%E7%B1%B3%E6%A0%BC%E5%B0%94%C2%B7%E5%BE%B7%C2%B7%E5%A1%9E%E4%B8%87%E6%8F%90%E6%96%AF) 
  - 他寫了《唐·吉軻德》
  - 他死在 1616 年 4 月 23 日

#### [威廉·莎士比亞](https://zh.wikipedia.org/wiki/%E5%A8%81%E5%BB%89%C2%B7%E8%8E%8E%E5%A3%AB%E6%AF%94%E4%BA%9A) 
  - 他寫了一堆作品
  - 他死在 1616 年 4 月 23 日

乍看之下這兩個人好像死在同一天。

但是呢，這兩個人生活的地方不同，一個在義大利一個在英國，使用的曆法不同，所以莎士比亞過世的日期其實晚了塞萬提斯十天。  

```Ruby
  > shakespeare=DateTime.iso8601('1616-04-23',Date::ENGLAND)
  => #<DateTime: 1616-04-23T00:00:00+00:00 ((2311415j,0s,0n),+0s,2361222j)>
  > cervantes=DateTime.iso8601('1616-04-23',Date::ITALY)
  => #<DateTime: 1616-04-23T00:00:00+00:00 ((2311405j,0s,0n),+0s,2299161j)>

  > shakespeare == cervantes
  => false

  > (shakespeare-cervantes).to_i
  => 10
```

[ref](https://gist.github.com/pixeltrix/e2298822dd89d854444b)