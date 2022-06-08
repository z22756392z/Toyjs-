# Toyjs-
* 來源自[ccc-c/toyjs: Tiny JavaScriptish interpreter (github.com)](https://github.com/ccc-c/toyjs)

## Toyjs報告

這是研究[ccc-c/toyjs: Tiny JavaScriptish interpreter (github.com)](https://github.com/ccc-c/toyjs) 後的報告 

#### Toyjs是什麼

這是個是個編譯器 有著Javascript中的一些的功能。 Toyjs是用C和javascript編寫而成的。

他有著以下功能:

* 閉包(Closures)

* 可編譯自己

* 垃圾收集器

  mark-sweep: 標記和回收 每次創造一個新物件後 新的物件會有上一個創造的物件連起來 , 也是所有的物件是連在一起 當需要空間時 GC 會遍歷所有物件把沒標記的物件回收



[new_object](./new_object.txt)

[Type](./Type.txt)