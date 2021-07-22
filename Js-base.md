## JS 一些基础
- 浅拷贝：最拷贝最外面一层的数据，对象只能拷贝引用
- 深拷贝：拷贝多层数据，对象也会拷贝每一层数据 属于彻底拷贝

##  ES6 Object.assgin(target,origin1,origin2)实现浅拷贝


## 深拷贝实现方式
### 1 for in 递归
    // 方法：深拷贝
    function deepCopy(newObj, oldObj) {
    for (let key in oldObj) {
        // 获取属性值 oldObj[key]
        let item = oldObj[key];
        // 判断这个值是否是数组
        if (item instanceof Array) {
            newObj[key] = [];
            deepCopy(newObj[key], item);
        } else if (item instanceof Object) {
            // 判断这个值是否是对象
            newObj[key] = {};
            deepCopy(newObj[key], item);
        } else {
            // 简单数据类型，直接赋值
            newObj[key] = item;
        }
    }
    }
    
    

### Object.freeze()冻结对象 不可修改
    
### ES6引入Class实现对象编程 之前是构造函数 
    class Point{
        constructor(x,y){
            this.x=x;
            this.y=y;
        }
        toString(){
            return this.x+"-"+this.y;
        }
    }


### offset Width Height
    元素内容+内边距+滚动条+边框
![offset](https://upload-images.jianshu.io/upload_images/831873-4adbf31826ddac04.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 ### client Width Height
        元素内容+内边距 
![client](https://upload-images.jianshu.io/upload_images/831873-d6fffef945d36b25.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### Event事件传递流
![Event事件传递](https://upload-images.jianshu.io/upload_images/831873-438060ca66fcf528.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

window->document->html->body
html节点  document.documentElement
body节点 document.body


### 事件委托 利用冒泡机制 对父节点冒泡事件触发 然后event.target拿到子节点做出相应的处理

