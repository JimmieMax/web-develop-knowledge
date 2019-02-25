##前端开发知识总结

## 代码管理工具 Git

### Git flow

分支命名规则

- 每次提交必须写明注释，如果是修复Bug，请加上Bug号
- 创建特性分支，名称要以feture/开头，加上特性名
- 创建发布分支，名称要以release/开头，加上预发布版本号
- 创建Bug修复分支，名称要以bugfix/开头，加上Bug号
- 创建标签，名称要以tag/开头，加上发布版本号
- 合并分支时必须使用--no-ff参数，以保留合并历史轨迹

#### Git commit 规范[参考文档](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

Header部分只有一行，包括三个字段：type（必需）、scope（可选）和subject（必需）。
type:

- feat：新功能（feature）
- fix：修补bug
- docs：文档（documentation）
- style： 格式（不影响代码运行的变动）
- refactor：重构（即不是新增功能，也不是修改bug的代码变动）
- test：增加测试
- chore：构建过程或辅助工具的变动

## Front End 前端

### 前端框架Vue、React、Angular

- Vue+Element
- React+Ant Design
- Angular

### CSS

#### Flex 布局[参考文档](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool)

容器的属性

- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

#### CSS动画

- `transition`: 过渡动画
	- `transition-property`: 属性
	- `transition-duration`: 间隔
	- `transition-timing-function`: 曲线
	- `transition-delay`: 延迟
	- 常用钩子: `transitionend`

- `animation / keyframes`
	- `animation-name`: 动画名称，对应`@keyframes`
	- `animation-duration`: 间隔
	- `animation-timing-function`: 曲线
	- `animation-delay`: 延迟
	- `animation-iteration-count`: 次数
		- `infinite`: 循环动画
	- `animation-direction`: 方向
		- `alternate`: 反向播放 
	- `animation-fill-mode`: 静止模式
		- `forwards`: 停止时，保留最后一帧
		- `backwards`: 停止时，回到第一帧
		- `both`: 同时运用 `forwards / backwards`
	- 常用钩子: `animationend`
		
- 动画属性: 尽量使用动画属性进行动画，能拥有较好的性能表现
	- `translate`
	- `scale`
	- `rotate`
	- `skew`


### Javascript

#### ES6(参考文档)[http://es6.ruanyifeng.com/]

### 浏览器

从输入 url 到展示的过程

1. DNS 解析
2. TCP 三次握手
3. 发送请求，分析 url，设置请求报文(头，主体)
4. 服务器返回请求的文件 (html)
5. 浏览器渲染

### 服务端与网络

常见状态码

- 1xx: 接受，继续处理
- 200: 成功，并返回数据
- 201: 已创建
- 202: 已接受
- 203: 成为，但未授权
- 204: 成功，无内容
- 205: 成功，重置内容
- 206: 成功，部分内容
- 301: 永久移动，重定向
- 302: 临时移动，可使用原有URI
- 304: 资源未修改，可使用缓存
- 305: 需代理访问
- 400: 请求语法错误
- 401: 要求身份认证
- 403: 拒绝请求
- 404: 资源不存在
- 500: 服务器错误

### 安全

#### XSS攻击: 注入恶意代码

- cookie 设置 httpOnly
- 转义页面上的输入内容和输出内容

#### CSRF: 跨站请求伪造，防护:

- get 不修改数据
- 不被第三方网站访问到用户的 cookie
- 设置白名单，不被第三方网站请求
- 请求校验

## Back End

### Node、Koa、Egg[参考文档](https://eggjs.org/zh-cn/)

## 算法

### 基础排序算法

冒泡排序: 两两比较

```js
function bubleSort(arr) {
    var len = arr.length;
    for (let outer = len ; outer >= 2; outer--) {
        for(let inner = 0; inner <=outer - 1; inner++) {
            if(arr[inner] > arr[inner + 1]) {
                [arr[inner],arr[inner+1]] = [arr[inner+1],arr[inner]]
            }
        }
    }
    return arr;
}
```

### 递归运用(斐波那契数列)： 爬楼梯问题

初始在第一级，到第一级有1种方法(s(1) = 1)，到第二级也只有一种方法(s(2) = 1)， 第三级(s(3) = s(1) + s(2))

```js
function cStairs(n) {
    if(n === 1 || n === 2) {
        return 1;
    } else {
        return cStairs(n-1) + cStairs(n-2)
    }
}
```

Updating
)