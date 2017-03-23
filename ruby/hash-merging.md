## Hash merging

Little trick about hash merge. We know the `merge` method already. So we define a, b and `merge` then with another.

```Ruby
a = { name: "Helen", age: 22, platform: "PlayStation4", game: "Nioh" }
b = { name: "Helen", age: 24, platform: "Switch"} 

> a.merge(b)
=> {:name=>"Helen", :age=>24, :platform=>"Switch", :game=>"Nioh"}

> b.merge(a)
=> {:name=>"Helen", :age=>22, :platform=>"PlayStation4", :game=>"Nioh"}
```

OK. the `merge` will keep the new-hash's (right side) value if they duplicate.

In Rails, you have `reverse_merge` method to do `merge` reversely.

If you add block after `merge` then you can do more other things. 

```Ruby
> b.merge(a) { |key, left, right| [left,right] }
=> {:name=>["Helen", "Helen"], :age=>[24, 22], :platform=>["Switch", "PlayStation4"], :game=>"Nioh"}

> b.merge(a) { |key, left, right| [left,right].uniq.sort }
=> {:name=>["Helen"], :age=>[22, 24], :platform=>["PlayStation4", "Switch"], :game=>"Nioh"}
```


- - -

## Hash merging 

小小技巧關於 Hash merge，我們應該都知道 `merge` 的功能，先定義 a, b 兩個做基本 `merge`

```Ruby
a = { name: "Helen", age: 22, platform: "PlayStation4", game: "Nioh" }
b = { name: "Helen", age: 24, platform: "Switch"} 

> a.merge(b)
=> {:name=>"Helen", :age=>24, :platform=>"Switch", :game=>"Nioh"}

> b.merge(a)
=> {:name=>"Helen", :age=>22, :platform=>"PlayStation4", :game=>"Nioh"}
```

我們可以看得出來 merge 的規則就是 key 取連集，但如果有同樣的， value 是以後面（右方）作為最後結果。

如果說你用 Rails 的話還有 `reverse_merge` 可以使用，同字面上所述，效果相反。

但其實 `merge` 後面可以加上 block 做一些變化，讓使用方式可以更靈活一點。

```Ruby
> b.merge(a) { |key, left, right| [left,right] }
=> {:name=>["Helen", "Helen"], :age=>[24, 22], :platform=>["Switch", "PlayStation4"], :game=>"Nioh"}

> b.merge(a) { |key, left, right| [left,right].uniq.sort }
=> {:name=>["Helen"], :age=>[22, 24], :platform=>["PlayStation4", "Switch"], :game=>"Nioh"}
```
