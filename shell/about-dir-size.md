## About dir size

```
$ du -h -d 1 rails-project | sort -r 
8.0K	rails-project/log
8.0K	rails-project/db
692K	rails-project
444K	rails-project/.git
4.0K	rails-project/test
 92K	rails-project/config
 56K	rails-project/app
 24K	rails-project/bin
 16K	rails-project/public
  0B	rails-project/vendor
  0B	rails-project/tmp
  0B	rails-project/lib
```

uh, excuse me.

`du -h -d 1` mean Disk Usage. `-h, --human-readable`, `-d 1,  --max-depth=1`.

`sort -r` Sort it reverse!

Enjoy!

- - -

## 關於檔案資料夾容量

其實會出現這篇，是因為我想試圖理解我的某個 repo 為什麼這麼大，最後查到是 `/.git` 佔了一半，傻眼。

```
$ du -h -d 1 rails-project | sort -r 
8.0K	rails-project/log
8.0K	rails-project/db
692K	rails-project
444K	rails-project/.git
4.0K	rails-project/test
 92K	rails-project/config
 56K	rails-project/app
 24K	rails-project/bin
 16K	rails-project/public
  0B	rails-project/vendor
  0B	rails-project/tmp
  0B	rails-project/lib
```

說文解字時間

`du -h -d 1` 就是 Disk Usage ，`-h, --human-readable` 你們人類懂的，`-d 1,  --max-depth=1`，一層就好。

`sort -r` 反過來排序。

其實這樣不用移出去用右鍵看還蠻快的。