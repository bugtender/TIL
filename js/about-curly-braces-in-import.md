## About curly braces in import

What's the different between these two line.

```
import d from "a";

import { d } from "a";
```

In fact, they are same if the second one write like this.

```
import d from "a";

import { default as d } from "a";
```

Obviously, if you want to import the default module from a. You don't need curly braces.
In the other words, if there's many module in a or you want to import multiple module in same name.
You need curly braces to defined.

- - -

## 有關 import 的大括號


以下兩個有什麼不同？

```
import d from "a";

import { d } from "a";
```

其實呢，下面兩個 import 幾乎是相同的

```
import d from "a";

import { default as d } from "a";
```

我想應該很明顯的，就是如果需 import 的是 default module ，就可以不用大括號。
換言之，如果有多個或是相同名稱避免撞名，就必須使用大括號並且調整。
