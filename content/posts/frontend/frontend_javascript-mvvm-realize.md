---
title: "手写数据绑定mvvm实现"
date: 2020-01-13T17:25:51+08:00
draft: false
tags: ["mvvm"]
categories: ["前端"]
featured_image: 
description: 
---

### mvc与mvvm

1.mvc

- model 模型层
- view 视图层
- controller 控制层

2.mvvm

mvvm由直接操作dom转变为数据驱动的方式，来更新页面数据。

- model 模型层
- view 视图层
- view model 视图模型层
  - view dom 监听
  - model 数据绑定

<img alt="mvvm-01" src="https://rudyarchitect.github.io/blog-images/frontend/frontend_mvvm-01.png">

### 基础知识

#### Object.defineProperty

  - 参数
    - obj 对象
    - prop 新属性或修改属性
    - descriptor 属性描述符
      - configurable
      - enumerable
      - value
      - wirtable
      - get
      - set


在一个对象上定义一个新属性，或者修改一个对象的现有属性，并返回该对象。

```javascript
const Test = function(){
    let item, arr = []
    Object.defineProperty(this, 'item',{
        get:() =>{
            console.log('get item of value')
            return item
        },
        set:(value)=>{
           item = value
           arr.push(item)
        }
    })
    this.getTest = ()=> arr
}

const a = new Test()
a.item
a.item = 1
a.item = 2
a.getTest() //['1','2']
```


#### 设计模式 

  观察者模式又称为发布-订阅模式或者消息机制，它定义了一种依赖关系，解决被观察对象和观察者之间的耦合。


  ```javascript
  const Observer = (function(){
      //消息容器
      let _messages = {}
      return {
          //监听
          listen:function(type,fn){
            //如果消息类型不存在，则创建一个消息类型
            if(typeof _messages[type] === 'undefined'){
                //创建消息执行队列
                _messages[type] = [fn]
            }else{
                _messages[type].push(fn)
            }
          },
          //发布
          publish:function(type,args){
            //消息执行队列不存在，返回
            if(!_messages[type]){
                return
            }
            //定义信息
            let events = {
                type:type,
                args:args || {}
            },
            i=0,
            len = _messages[type].length
            //遍历消息执行队列
            for(;i<len;i++){
                _messages[type][i].call(this,events);
            }
          },
          //移除
          remove:function(type,fn){
            //如果消息执行队列存在
            if(_message[type] instanceof Array){
                //从最后一个元素开始遍历
                let i = _messages[type].length - 1
                for(;i>=0;i--){
                    // 如果函数存在，则移除
                    _messages[type][i] === fn && _messages[type].splice(i,1)
                }
            }
          }
      }
  })()

  Observer.listen('test',function(e){
      console.log(e)
  })

  Observer.publish('test',{msg:'消息’}) //{type:'test',args:{msg:‘消息’}}
  ```



### 数据绑定实现

#### vue.js

<img alt="mvvm-01" src="https://rudyarchitect.github.io/blog-images/frontend/frontend_mvvm-02.png">

#### 手写mvvm

定义

```javascript
const Mvvm = function(options = {}){
    // vm.$options
    this.$options = options
    let data = this._data = this.$options.data
    //数据劫持
    Observer(data)
}
```

数据劫持

- 给观察的对象添加Object.defineProperty
- 深度响应（数据对象嵌套）

```javascript
const Observe = function(data){
    for(let key in data){
        let val = data[key]
        deepObserve(val)
        Object.defineProperty(data,key,{
            get(){
                return val
            },
            set(newVal){
                if(val === newVal){
                    return
                }
                val = newVal
                deepObserve(newVal)
            }
        })
    }
}

const deepObserve = function(data){
    if(!data || typeof data !== 'Object'){
        return
    }
    return new Observe(data)
}
```

数据代理

```javascript
const Mvvm = function(options = {}){
    ... ...
    // this代理this._data
    for(let key in data){
        Object.defineProperty(this,key,{
            get(){
                return this._data[key]
            },
            set(newVal){
                this._data[key] = newVal
            }
        })
    }  
}
```

模版编译

- v-model
- {{ }}

```javascript
const Compile = function(el,vm){
    vm.$el = document.querySelector(el)

}
```

测试

```html
// index.html
<body>
    <div id="app">
        <p>{{test}}</p>
    </div>
    <!--实现的mvvm-->
    <script src="mvvm.js"></script>
    <script>
        // 写法和Vue一样
        let mvvm = new Mvvm({
            el: '#app',
            data: {    
                test:'双向绑定‘
            }
        });
    </script>
</body>

```

<br>

<center>  ·End·  </center>