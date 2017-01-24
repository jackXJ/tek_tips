### xpath总结
- "//"：表示选择任意位置的某个节点
- "/"：表示选择根节点
- "@"： 表示选择某个属性


####  例子

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<bookstore>
  <book>
    <title lang="eng">Harry Potter</title>
    <price>29.99</price>
  </book>
  <book>
    <title lang="eng">Learning XML</title>
    <price>39.95</price>
  </book>
</bookstore>

```

- /bookstore ：选取根节点bookstore，这是绝对路径写法。
- //book ：选择所有 book 子元素，而不管它们在文档中的位置。
- bookstore//book ：选择所有属于 bookstore 元素的后代的 book 元素，而不管它们位于 bookstore 之下的什么位置。
- bookstore/book ：选取所有属于 bookstore 的子元素的 book元素，这是相对路径写法。
- //@lang ：选取所有名为 lang 的属性。
- /bookstore/book[1] ：表示选择bookstore的第一个book子元素
- /bookstore/book[last()] ：表示选择bookstore的最后一个book子元素。
- /bookstore/book[last()-1] ：表示选择bookstore的倒数第二个book子元素。
- /bookstore/book[position()<3] ：表示选择bookstore的前两个book子元素。
- //title[@lang] ：表示选择所有具有lang属性的title节点。
- //title[@lang='eng'] ：表示选择所有lang属性的值等于"eng"的title节点。
- /bookstore/book[price] ：表示选择bookstore的book子元素，且被选中的book元素必须带有price子元素。
- /bookstore/book[price>35.00] ：表示选择bookstore的book子元素，且被选中的book元素的price子元素值必须大于35。
- /bookstore/book[price>35.00]/title ：表示在例14结果集中，选择title子元素。
- /bookstore/book/price[.>35.00] ：表示选择值大于35的"/bookstore/book"的price子元素。
