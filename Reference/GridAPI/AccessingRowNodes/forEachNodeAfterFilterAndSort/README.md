### Accessing Data
### iterate only nodes that pass the filter and ordered by the sort order
### 在节点筛选排序后迭代
```
api.forEachNodeAfterFilterAndSort(function(rowNode, index) {
    console.log('node ' + rowNode.data.athlete + ' passes the filter and is in this order');
});
```
### 使用场景
#### 1.在filter/sort之后，需要重新处理数据的场景
#### 2.需要filter/sort之后的数据做其他处理，比如导出Excel，下载等
### 伪代码
```
//
var itemsToUpdate = [];
api.forEachNodeAfterFilterAndSort(function (rowNode, index) {
    var data = rowNode.data;
    //...
    //处理data
    data.type === '0'?'ABC':'DEF';
    //...
    itemsToUpdate.push(data);
});
//更新Grid
api.updateRowData({ update: itemsToUpdate });
```
