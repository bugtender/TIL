## About Shebang

Shebang is `#!` in the source code. Under Unix-like OS, when a script with a shebang is run as a program, OS will parse the value below shebang and run it as interpreter.

Like `#!/bin/sh` everywhere. :smile:

We call it "magic comment" in ruby. You can specify which path of ruby you want. Or you can add more setting.

Like `#!/usr/local/bin/ruby`

- - -

## 關於 Shebang

Shebang 在程式碼裡面是 `#!` ，在 Unix 系列的 OS 下，當你要執行含有 shebang 的程式時，OS 會先解譯 Shebang 後的內容當作直譯器指令並且呼叫。

最常見的大概就是 `#!/bin/sh`。

在 Ruby 中，我們稱之為魔法註解（ magic comment ），我們可以利用他指定使用特殊位置的 Ruby，或是加入更多設定。

像是 `#!/usr/local/bin/ruby`