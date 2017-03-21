## sort_by in an array

We know that we have `sort` method in Ruby.

```Ruby
  a = [9, 7, 8]
  
  a.sort
  => [7, 8, 9]
```

But if you want to sort an array by other attributes. There's a method call `sort_by` can sort the array by any attributes in objects of array.

```Ruby
  a = [["Peter", 9], ["Vincent", 7], ["Jyn", 8]]

  a.sort_by { |x| x[1] }
  => [["Vincent", 7], ["Jyn", 8], ["Peter", 9]]

  a.sort_by { |x| x[0].length }
  => [["Jyn", 8], ["Peter", 9], ["Vincent", 7]]
```

- - -

## 用 sort_by 排序陣列 

我們都知道 Ruby 有 `sort` 可以使用

```Ruby
  a = [9, 7, 8]
  
  a.sort
  => [7, 8, 9]
```

但如果陣列中不只是數值，要比較其他值之類的，就可以利用 `sort_by` 然後指定你要排列的依據

```Ruby
  a = [["Peter", 9], ["Vincent", 7], ["Jyn", 8]]

  a.sort_by { |x| x[1] }
  => [["Vincent", 7], ["Jyn", 8], ["Peter", 9]]

  a.sort_by { |x| x[0].length }
  => [["Jyn", 8], ["Peter", 9], ["Vincent", 7]]
```

