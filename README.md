### 使用

+ 说明：这是一个可以帮助你管理类似与一个复制的场景的需求的库，它仅仅抽象了一个元素的变化过程。但它不能直接帮你做复制，而是你通过注册dragElement
+ 接着通过dragElementHide()与dragElementShow()方法来控制复制过程中元素的变化，然后再去给dom元素里添加被复制的元素
+ 你可以将其搭配上VueDragResize 与vue 的v-for 命令来实现一个可视化拖拽平台。
+ 可以参照demo =>https://github.com/qianzhuoyao/ADrag.git

```JavaScript
new PipeEvent()
    .setDragElement("123")
    //设置来源元素
    .setCopyElement(`456`)
    .dragElementHide()
    .pipeEventStart({
        downCallback: (pipe) => {
            pipe.dragElementShow()
            //鼠标按下回调 pipe 为PipeEvent该实例本身
        },
        moveCallback: (pipe, e) => {
            pipe.dragElementPosition({x: e.x, y: e.y})
            //鼠标移动回调 pipeOver 为PipeEvent该实例本身 e为鼠标放起的原生事件对象
        },
        overCallback: (pipeOver, e) => {
            console.log(pipeOver, e)
            //鼠标放起回调 pipeOver 为PipeEvent该实例本身 e为鼠标放起的原生事件对象
        },
    });
```
### FQ
arronqzy@outlook.com
