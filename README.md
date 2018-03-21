> 让 Javascript对象 映射可以像 C# AutoMapper 一样简单。

### 作者信息

- 原创作者：百小僧
- 开发时间：2018年03月21日
- 当前版本：`1.0.0`
- 项目名称：[automapper.js](https://gitee.com/monksoul/automapper.js)
- 联系方式：QQ/8020292
- 压缩版本：`1KB`


### 使用文档

- 引入 [automapper.js](https://gitee.com/monksoul/automapper.js)

```html
<script src="automapper.js" type="text/javascript"></script>
```

- 示例

```javascript

// # 示例一

var srcObj = { name: "百小僧", age: 25, gender: '男' }; // 源类型
var destObj= { name: null, age: null, gender: null };   // 目标类型

// 创建映射关系
automapper.createMap("src","dest");
// 开始映射
automapper.map("src","dest",srcObj,destObj);
// 输出结果：
// srcObj => { name: "百小僧", age: 25, gender: '男' }
// destObj => { name: "百小僧", age: 25, gender: '男' }


// # 示例二

var srcObj = { name: "百小僧", age: 25, gender: '男' }; // 源类型
var destObj = { firstName: null, age: null, sex: null, birthday: null };    // 目标类型

// 创建映射关系
automapper.createMap("src", "dest")
    .forMember("firstName", function (src, dest) { return "Mr." + src.name })
    .forMember("sex", srcObj.gender)
    .forMember("birthday", '1993-05-27');
// 开始映射
automapper.map("src", "dest", srcObj, destObj);
// 输出结果：
// srcObj => { name: "百小僧", age: 25, gender: '男' }
// destObj => {firstName: "Mr.百小僧", age: 25, sex: "男", birthday: "1993-05-27"}

```

### 参数介绍

[automapper.js](https://gitee.com/monksoul/automapper.js) 只包含两个静态方法 `automapper.createMap`、`automapper.map`，一个成员方法 `forMember`

- `createMap(srcKey, destKey)`：创建映射关系

    - srcKey ：源对象Key，`String` 类型
    - destKey：目标对象Key，`String` 类型


- `map(srcKey, destKey, srcObj, destObj)`：开始隐射

    - srcKey ：源对象Key，`String` 类型，需与 `CreateMap` 配置中的 `srcKey` 对应
    - destKey：目标对象Key，`String` 类型，需与 `CreateMap` 配置中的 `destKey` 对应
    - srcObj：源对象，`JSON Object` 类型
    - destObj：目标对象，`JSON Object` 类型


- `forMember(prop, any)`：配置成员映射关系

    - prop：目标对象属性名，`String` 类型
    - any：支持 `Object`、`Function(src,dest)`类型


### 开源地址

- 码云地址：[automapper.js](https://gitee.com/monksoul/automapper.js)

### 喜欢就 `star` 一下

如果你喜欢 [automapper.js](https://gitee.com/monksoul/automapper.js)，可以点击右上角的star，想实时关注进度，可以点击右上角的watch。

最后，感谢每一个提建议和使用的朋友！因为你们，我们才能坚持！也是因为你们，未来才会更美好！