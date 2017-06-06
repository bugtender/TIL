# About Ghost posts order

Last time, we successfully [host the ghost on the Google Cloud Platform](https://github.com/bugtender/til/blob/master/internet/about-google-cloud-platform-ghost.md). The posts order is default by `DESC`. Which mean the lastest published post is the first order. But now we need to reverse posts order by `ASC`. 

In `/opt/bitnami/apps/ghost/htdocs/core/server/models.js` about line 505. There is a function name `orderDefaultOptions`. By this [stackoverflow answer](https://stackoverflow.com/questions/29754660/ghost-blog-posts-sort-order), it is the setting of posts order. But nothing change after we switched that.

```javascript
orderDefaultOptions: function orderDefaultOptions() {
      return {
        status: 'ASC',
        published_at: 'ASC',
        updated_at: 'DESC',
        id: 'DESC'
      };
    },
```

So I look around Ghost's GitHub code and I found this [part](https://github.com/TryGhost/Ghost/blob/master/core/server/models/base/index.js#L489). This if else block show that there is a `orderDefaultRaw` will excute before `orderDefaultOptions`. This is it.

Go back to `/opt/bitnami/apps/ghost/htdocs/core/server/models.js` file. After `orderDefaultOptions` part about line 509 there is the `orderDefaultRaw`. So we change the `posts.published_at DESC,` to `ASC`. Good!

```javascript
orderDefaultRaw: function () {
  return '' +
    'CASE WHEN posts.status = \'scheduled\' THEN 1 ' +
    'WHEN posts.status = \'draft\' THEN 2 ' +
    'ELSE 3 END ASC,' +
    'posts.published_at ASC,' +
    'posts.updated_at DESC,' +
    'posts.id DESC';
  },
```

Remember to restart after you change something.

```shell
$ /opt/bitnami/ctlscript.sh restart ghost
$ /opt/bitnami/ctlscript.sh restart apache
```

- - - 

# 有關 Ghost 文章排序

上次在 [Google Cloud Platform 上面架好 Ghost](https://github.com/bugtender/til/blob/master/internet/about-google-cloud-platform-ghost.md) 之後，由於要把文章 (posts) 依照 `published_at` 反序，我們需要先寫的文章在第一篇，找了 [stackoverflow 的解法](https://stackoverflow.com/questions/29754660/ghost-blog-posts-sort-order) 之後發現沒有用，就開始把想法動到 code 上面。

在 `/opt/bitnami/apps/ghost/htdocs/core/server/models.js` 裡面大約 505 行的地方有一個 `orderDefaultOptions` 的 function，根據 stackoverflow 的說法是這邊可以調整文章排序 `ASC` 或 `DESC` ，但是不知為何我們的 Ghost 調整之後重開都沒有用。

```javascript
orderDefaultOptions: function orderDefaultOptions() {
      return {
        status: 'ASC',
        published_at: 'ASC',
        updated_at: 'DESC',
        id: 'DESC'
      };
    },
```

大概去 Ghost 的 GitHub 上面看了一下 issue 跟 code ，才發現這是之後才加上去複寫排序的設定，大概是[這一段](https://github.com/TryGhost/Ghost/blob/master/core/server/models/base/index.js#L489)，所以理論上只要去找到原始 query 修改，應該就能成功。

很幸運的是，原始 query 就在 `orderDefaultOptions` 下面，大約 509 行的地方，我們把 `posts.published_at DESC,` 改成 `ASC` 即可。

```javascript
orderDefaultRaw: function () {
  return '' +
    'CASE WHEN posts.status = \'scheduled\' THEN 1 ' +
    'WHEN posts.status = \'draft\' THEN 2 ' +
    'ELSE 3 END ASC,' +
    'posts.published_at ASC,' +
    'posts.updated_at DESC,' +
    'posts.id DESC';
  },
```

最後記得重開 Ghost 跟 Apache 。

```shell
$ /opt/bitnami/ctlscript.sh restart ghost
$ /opt/bitnami/ctlscript.sh restart apache
```
