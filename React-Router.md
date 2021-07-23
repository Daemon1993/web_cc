## 路由
>hash路由 低版本 更新 兼容 HashRouter  -> 前面有#/
url路由 BrowserRouter
内存路由    MemoryRouter url不变  ui会变
![Router APi](https://upload-images.jianshu.io/upload_images/831873-144ce0749ff754a8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>传参数
页面状态尽量通过URL参数定义
Route path后定义规则 
跳转组件 通过 props.match.parmas拿到相关参数
```
 <Route path="/home/:name" component={Home} />
```

>在React-Router路由中 一种新的组件写法
(match)=>()  高阶函数 直接传递match过来

```
const Home1=({match})=>(<h1>{match.params.name}</h1>)
```