<!-- Date: 2017-06-02 11:41 -->

# algorithm 基础算法之双向冒泡排序

这次记录一下冒泡排序的升级版：双向冒泡排序

冒泡排序内容可以参考[基础算法之 冒泡排序](http://vue2.codequan.com/home/article/2017112420583534),双向冒泡排序作为毛爬坡排序的升级版，主要思路如下：

每次遍历过程中，先把最大的排到最后去，再把最小的排到最前面去，遍历一次后，数组的第一个和最后一个就被固定了，后续的遍历不需要再考虑已经被固定了的元素，因此无论在遍历次数还是遍历元素的数量上都有了极大的优化。

我们先看一下代码的实现

```js
function sort(array) {
    var len = array.length;
    for (var i = 1; i <= len; i++) {
        var skip = false;
        // 最大的挪到最后
        var a = len - i - 1;
        for (var j = i - 1; j <= a; j++) {
            array[j] > array[j + 1] && (skip = true) && swap(j, j + 1, array);
        }
        if (!skip) {
            console.log(1);
            break;
        }
        skip = false;
        console.log(1, array);
        var b = len - i;
        // 最小的挪到最前面
        for (var k = len - i; k >= i; k--) {
            array[k] < array[k - 1] && (skip = true) && swap(k, k - 1, array);
        }
        if (!skip) {
            console.log(2);
            break;
        }
        console.log(2, array);
    }
}
sort([8, 7, 6, 5, 4, 3, 2, 1]);
```

以[8,7,6,5,4,3,2,1]为例

```
第一轮遍历：
从[0]开始，遍历到[6]
结果为 [7,6,5,4,3,2,1,8]， 8被确认为被遍历元素中的最大值，后续遍历不需要考虑[7]元素

从[6]开始，遍历到0
结果为 [1,7,6,5,4,3,2,8]， 1被确认为被遍历元素中的最小值，后续遍历不需要考虑[0]元素


第二轮
从[1]开始，遍历到[5]
结果为 [1,6,5,4,3,2,7,8]， 7被确认为被遍历元素中的最大值，后续遍历不需要考虑[6,7]元素

从[5]开始，遍历到1
结果为 [1,2,6,5,4,3,7,8]， 2被确认为被遍历元素中的最小值，后续遍历不需要考虑[0,1]元素


第三轮
从[2]开始，遍历到[4]
结果为 [1,2,5,4,3,6,7,8]， 6被确认为被遍历元素中的最大值，后续遍历不需要考虑[5,6,7]元素

从[4]开始，遍历到[2]
结果为 [1,2,3,5,4,6,7,8]， 3被确认为被遍历元素中的最小值，后续遍历不需要考虑[0,1,2]元素

第四轮
对比[3][4]的元素大小
结果为 [1,2,3,4,5,6,7,8]，

现在所有的元素已经排序成功了，为了避免多余的循环，我们可以在这里直接打断循环。因此我们引入了skip变量。

当所有的对比都没有满足需求的时候，就认为排序已经成功，就可以打断循环了
```
