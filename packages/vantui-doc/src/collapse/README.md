# Collapse 折叠面板

### 介绍

将一组内容放置在多个折叠面板中，点击面板的标题可以展开或收缩其内容。

### 引入

在 Taro 文件中引入组件

```js
import { Collapse, CollapseItem } from '@antmjs/vantui'
```

## 代码演示

### 基础用法

通过`value`控制展开的面板列表，`activeNames`为数组格式。

```jsx
function Demo() {
  const [values, setValues] = react.useState(['1'])

  return (
    <Collapse value={values} onChange={(e) => setValues(e.detail)}>
      <CollapseItem title="有赞微商城" name="1">
        提供多样店铺模板，快速搭建网上商城
      </CollapseItem>
      <CollapseItem title="有赞零售" name="2">
        网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
      </CollapseItem>
      <CollapseItem title="有赞美业" name="3" disabled>
        线上拓客，随时预约，贴心顺手的开单收银
      </CollapseItem>
    </Collapse>
  )
}
```

### 手风琴

通过`accordion`可以设置为手风琴模式，最多展开一个面板，此时`activeName`为字符串格式。

```jsx
function Demo() {
  const [values, setValues] = react.useState(['1'])

  return (
    <Collapse accordion value={values} onChange={(e) => setValues(e.detail)}>
      <CollapseItem title="有赞微商城" name="1">
        提供多样店铺模板，快速搭建网上商城
      </CollapseItem>
      <CollapseItem title="有赞零售" name="2">
        网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
      </CollapseItem>
      <CollapseItem title="有赞美业" name="3">
        线上拓客，随时预约，贴心顺手的开单收银
      </CollapseItem>
    </Collapse>
  )
}
```

### 事件监听

`vanCollapse` 提供了 `change`, `open` 和 `close` 事件。`change` 事件在面板切换时触发，`open` 事件在面板展开时触发，`close` 事件在面板关闭时触发。

```jsx
function Demo() {
  const [values, setValues] = react.useState(['1'])

  return (
    <>
      <Collapse
        value={values}
        onChange={(e) => setValues(e.detail)}
        onOpen={(e) => Toast.show(`打开${e.detail}`)}
        onClose={(e) => Toast.show(`关闭${e.detail}`)}
      >
        <CollapseItem title="有赞微商城" name="1">
          提供多样店铺模板，快速搭建网上商城
        </CollapseItem>
        <CollapseItem title="有赞零售" name="2">
          网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
        </CollapseItem>
        <CollapseItem title="有赞美业" name="3">
          线上拓客，随时预约，贴心顺手的开单收银
        </CollapseItem>
      </Collapse>
      <Toast id="collapse-mess" />
    </>
  )
}
```

### 自定义标题内容

```jsx
function Demo() {
  const [values, setValues] = react.useState(['1'])

  return (
    <Collapse value={values} onChange={(e) => setValues(e.detail)}>
      <CollapseItem
        renderTitle={
          <View>
            有赞微商城
            <Icon name="question-o" />
          </View>
        }
        name="1"
      >
        提供多样店铺模板，快速搭建网上商城
      </CollapseItem>
      <CollapseItem title="有赞零售" name="2">
        网店吸粉获客、会员分层营销、一机多种收款，告别经营低效和客户流失
      </CollapseItem>
      <CollapseItem title="有赞美业" name="3">
        线上拓客，随时预约，贴心顺手的开单收银
      </CollapseItem>
    </Collapse>
  )
}
```

### CollapseProps [[详情]](https://github.com/AntmJS/vantui/tree/main/packages/vantui/types/collapse.d.ts)

| 参数      | 说明 | 类型                                                                                                                                                                                                                                                      | 默认值 | 必填    |
| --------- | ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------- |
| value     | -    | _&nbsp;&nbsp;attr:<br/>&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;Array<<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;><br/>&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;string<br/>_ | -      | `false` |
| accordion | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                                                | -      | `false` |
| border    | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                                                | -      | `false` |
| children  | -    | _&nbsp;&nbsp;attr:<br/>&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;Array<ReactNode><br/>&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;ReactNode<br/>_                                                                                                                   | -      | `false` |
| onChange  | -    | _&nbsp;&nbsp;(<br/>&nbsp;&nbsp;&nbsp;&nbsp;event:&nbsp;ITouchEvent<br/>&nbsp;&nbsp;)&nbsp;=>&nbsp;any<br/>_                                                                                                                                               | -      | `false` |
| onOpen    | -    | _&nbsp;&nbsp;(<br/>&nbsp;&nbsp;&nbsp;&nbsp;event:&nbsp;ITouchEvent<br/>&nbsp;&nbsp;)&nbsp;=>&nbsp;any<br/>_                                                                                                                                               | -      | `false` |
| onClose   | -    | _&nbsp;&nbsp;(<br/>&nbsp;&nbsp;&nbsp;&nbsp;event:&nbsp;ITouchEvent<br/>&nbsp;&nbsp;)&nbsp;=>&nbsp;any<br/>_                                                                                                                                               | -      | `false` |

### CollapseItemProps [[详情]](https://github.com/AntmJS/vantui/tree/main/packages/vantui/types/collapse.d.ts)

| 参数            | 说明              | 类型                                                | 默认值 | 必填    |
| --------------- | ----------------- | --------------------------------------------------- | ------ | ------- |
| name            | -                 | _&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>_ | -      | `false` |
| title           | -                 | _&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>_ | -      | `false` |
| value           | -                 | _&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>_ | -      | `false` |
| icon            | 对应 Icon 的 name | _&nbsp;&nbsp;string<br/>_                           | -      | `false` |
| label           | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| disabled        | -                 | _&nbsp;&nbsp;boolean<br/>_                          | -      | `false` |
| clickable       | -                 | _&nbsp;&nbsp;boolean<br/>_                          | -      | `false` |
| border          | -                 | _&nbsp;&nbsp;boolean<br/>_                          | -      | `false` |
| isLink          | -                 | _&nbsp;&nbsp;boolean<br/>_                          | -      | `false` |
| children        | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| renderTitle     | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| renderIcon      | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| renderRightIcon | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| renderValue     | -                 | _&nbsp;&nbsp;ReactNode<br/>_                        | -      | `false` |
| size            | -                 | _&nbsp;&nbsp;"large"<br/>_                          | -      | `false` |
