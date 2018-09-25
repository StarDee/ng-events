# ng-events for Angular (v2+)

## 介绍

ng-events is a simple global event bus to register to and trigger events.

ng-events 在 Angular 2 以上的版本中使用，类似于 ionic 中的 Events。可以使用 ng-events 注册一个全局事件，然后在需要的时候触发这个事件。


## 快速开始

```
npm install ng-events --save
```

在 Angular 6 以上的版本中使用,修改 angular.json 文件, 在Angular 6以下版本中使用，修改.angular-cli.json文件

```
 "scripts": [
              "node_modules/ng-events/dist/ng-events.js"
              // ...
            ]
```
当然也可以直接在index.html中引入，不过并不推荐这么做。

## 注册事件

- 你可以使用 ngEevents.on 注册一个全局事件:

```
ngEvents.on('eventName', function (item) {
    console.log(item.name + ' was selected!');
});
```

第一个参数是事件的唯一名称。 第二个参数是在触发指定事件时调用的回调函数。

- 您可以使用 ngEvents.off 方法取消注册的事件。

## 触发事件

使用 ngEvents.trigger 触发一个全局事件:

```
ngEvents.trigger('eventName', {
    id: 42,
    name: 'Pencil'
});
```

第一个参数是事件的唯一名称. 第二个是（可选）事件参数。
你可以添加任意数量的参数并在回调方法中获取它们。
