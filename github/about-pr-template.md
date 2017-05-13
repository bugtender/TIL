## About GihHub Pull Request templates

There's lots of developer in my team. And each developer has his own style in writing doc and pull-request message. It's make code review a lettle harder.

So we decide to sync our Pull Request Style.

1. Shrink the Pull Request Size.
2. If you can't shrink it. Detail your pull request message.

There's many way to write a GOOD detail message.

Like `What's this PR do?`, `Where should the reviewer start?`, `How should this be manually tested?`, etc.

The message will make the developer check his code again and let developer learn how to communicate with real people.

So we fork a template from the Internet. Just name it `PULL_REQUEST_TEMPLATE.md` and save it to your repository.

Next time you open the new PR. GitHub will automatically fill the question for you.

Pretty cool ! 

```
What's this PR do?

Where should the reviewer start?

How should this be manually tested?

Any background context you want to provide?

What are the relevant tickets?

Screenshots (if appropriate)

Questions:

Is there a blog post?
Does the knowledge base need an update?
Does this add new (Python) dependencies which need to be added to chef?
```


## 關於 GihHub Pull Request 範本

由於幾個月前敝司工程師突然大舉徵才變成原本的 1.5 倍，為了讓每個工程師在 review PR 的時候不要太長昏昏去或是覺得麻煩直接 skip ，我們決定採取下面兩種做法。

1. 每個 Pull Request 都要縮小，最好是小而多，而不是一包大包的丟上來。
2. 如果小 Pull Request 是先 Merge 進一個比較大的 Feature Branch ，那麼 Branch 對 Master 的 Pull Request 要詳細地寫清楚做了什麼。

照著這樣跑一陣子之後還是發現有一些東西沒有辦法切細，還是會有一些不知道為什麼好大包的跑出來。

那我們只好從說明開始下手，你要拿大包的上來你就給我寫清楚你做了什麼事。

像是這個 PR 是做什麼的啊？ Reviewer 應該從哪裡開始看起啊？ 你需要提供什麼背景故事嗎？ 還是有其他關聯的 tickets ？

這樣的做法會讓寫 PR 的人在回答這些問題的過程中在思考一次自己所寫的 code，並且負起別人也應該看得懂的責任。

所以我們從網路上拷貝了一份問題大全，然後只要在 Repo 生成 `PULL_REQUEST_TEMPLATE.md` 當作範本

之後開新的 PR 時， GitHub 便會直接的把 `PULL_REQUEST_TEMPLATE.md` 內容帶入 PR 內容，省了一點時間呢。

下面就是我們直接致敬別人的版本

```
What's this PR do?

Where should the reviewer start?

How should this be manually tested?

Any background context you want to provide?

What are the relevant tickets?

Screenshots (if appropriate)

Questions:

Is there a blog post?
Does the knowledge base need an update?
Does this add new (Python) dependencies which need to be added to chef?
```