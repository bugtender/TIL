## About For and Each 

You know more about `Each` and `For` if you are a Ruby engineer.
Both of them are almost the same things.

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> for ranger in rangers
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!

> rangers.each do |ranger|
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!
```

In fact, both them are `Each`, `For` just a syntax sugar for `Each`.
We can rewrite object's each to prove it.

```Ruby
> class MightyMorphinRangers
>   def each
>     yield "Mastodon"
>     yield "Pterodactyl"
>     yield "Triceratops"
>     yield "Saber-Toothed Tiger"
>     yield "Tyrannosaurus"
>   end
> end

> rangers =  MightyMorphinRangers.new

> for ranger in rangers
>   puts "#{ranger}!!"
> end
Mastodon!!
Pterodactyl!!
Triceratops!!
Saber-Toothed Tiger!!
Tyrannosaurus!!
```

The different part is that the `For` will keep the lastest value. `Each` does not.

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> rangers.each do |ranger|
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!

> puts ranger
NameError: undefined local variable or method `ranger' for main:Object

```

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> for ranger in rangers
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!

> puts ranger
Red

```

That's it.

- - -

## 關於 For 和 Each

如果你是一個 Ruby 工程師，你應該認識 `For` 和 `Each` 相當久一段時間了。

簡單來說呢，兩個功能其實十分類似，都是把東西`全部`噴出來。

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> for ranger in rangers
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!

> rangers.each do |ranger|
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!
```

實際上呢，他們都是 `Each` ， `For` 只是語法糖 (syntax sugar) 而已，我們用新的 Object 並且複寫他的 each 證實

```Ruby
> class MightyMorphinRangers
>   def each
>     yield "Mastodon"
>     yield "Pterodactyl"
>     yield "Triceratops"
>     yield "Saber-Toothed Tiger"
>     yield "Tyrannosaurus"
>   end
> end

> rangers =  MightyMorphinRangers.new

> for ranger in rangers
>   puts "#{ranger}!!"
> end
Mastodon!!
Pterodactyl!!
Triceratops!!
Saber-Toothed Tiger!!
Tyrannosaurus!!
```

比較不一樣的地方是， `For` 會保留最後的 value， 而 `Each` 則是每次都是開新的 scope，所以 loop 的值不會保留

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> rangers.each do |ranger|
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!

> puts ranger
NameError: undefined local variable or method `ranger' for main:Object

```

```Ruby

rangers = ["Black", "Pink", "Yellow", "Blue", "Red"]

> for ranger in rangers
>   puts "I am #{ranger} Ranger!!"
> end
I am Black Ranger!!
I am Pink Ranger!!
I am Yellow Ranger!!
I am Blue Ranger!!
I am Red Ranger!!

> puts ranger
Red

```

大概是這樣啦。