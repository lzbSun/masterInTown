# Array 语法总结
## splice
splice() 方法用新元素替换旧元素，以此修改数组的内容。
> array.splice(start, deleteCount[, item1[, item2[, ...]]])

- start  
    从数组的哪一位开始修改内容。如果超出了数组的长度，则从数组的末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位。
- deleteCount
    整数，表示要移除的数组元素的个数。如果deleteCount是0,则不移除元素。这种情况下，至少应添加一个新元素。如果deleteCount大于start之后元素的总数，则从start后面的元素都将被删除(含第start位)
- itemN
    要添加进数组的元素。如果不指定，则splice() 只删除数组元素。
- 返回值
    由被删除的元素组成的一个数组，如果没有删除元素，则返回空数组。
- 实例
    ```javascript
        var myFish = ['angel', 'clown', 'mandarin', 'surgeon']
       let removeFish =  myFish.splice(2, 0, 'drum') // 返回[]
       // myFish ['angel', 'clown', 'mandarin', 'drum', 'surgeon']
        let arr = [1, 2, 3, 4, 5]
        arr.splice(1, 2, 3, 4, 5) //arr [1, 3, 4, 5, 4, 5]
   ```
## slice
把数组中一部分的浅复制存入一个新数组对象中，并返回这个数组
> array.slice([begin[, end]])

- begin
    从该索引处开始提取原数组中的元素（从0开始）
    如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取，slice(-2)表示提取原数组中的倒数第二个元素到最后一个元素（包含最后一个元素）
如果省略begin ，则slice从索引0开始。
- end
    在该索引出结束提取原数组元素（从0开始）。 slice会提取原数组中索引从begin到end的所有元素(包括begin, 但不包含end)。
    slice(1, 4) 提取原数组中的第二个元素开始到第四个元素的所有元素(索引为1，2，3的元素)。
如果该参数为负值，则它表示在原数组中的倒数第几个元素结束抽取。slice(-2, -1)表示抽取了原数组中的倒数第二个元素到最后一个元素(不包含最后一个元素)
    如果end被省略，则slice会一直提取到原数组末尾
**描述**
    不修改原数组，只会返回一个包含了原数组中提取部分元素的一个新数组。
    对于字符串和数字，slice会拷贝字符串和数字到新的数组中
```javascript
    var fruits = ['apple', 'orange', 'lemon', 'apple'];
    var citrus = fruits.slice(1, 3); [ 'orange', 'lemon']
```
