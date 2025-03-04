# Tabbar 标签栏

### 介绍

底部导航栏，用于在不同页面之间进行切换。

### 引入

在 Taro 文件中引入组件

```js
import { Tabbar, TabbarItem } from '@antmjs/vantui'
```

## 代码演示

### 基础用法

```jsx
function Demo() {
  const [active, setActive] = react.useState(0)
  return (
    <Tabbar
      active={active}
      onChange={(e) => setActive(e.detail)}
      safeAreaInsetBottom={false}
    >
      <TabbarItem icon="home-o">标签</TabbarItem>
      <TabbarItem icon="search">标签</TabbarItem>
      <TabbarItem icon="friends-o">标签</TabbarItem>
      <TabbarItem icon="setting-o">标签</TabbarItem>
    </Tabbar>
  )
}
```

### 通过名称匹配

在标签指定`name`属性的情况下，`vModel`的值为当前标签的`name`。

```jsx
function Demo() {
  const [active, setActive] = react.useState('home')
  return (
    <Tabbar active={active} onChange={(e) => setActive(e.detail)}>
      <TabbarItem name="home" icon="home-o">
        标签
      </TabbarItem>
      <TabbarItem name="search" icon="search">
        标签
      </TabbarItem>
      <TabbarItem name="friends" icon="friends-o">
        标签
      </TabbarItem>
      <TabbarItem name="setting" icon="setting-o">
        标签
      </TabbarItem>
    </Tabbar>
  )
}
```

### 显示徽标

```jsx
function Demo() {
  const [active, setActive] = react.useState('home')
  return (
    <Tabbar active={active} onChange={(e) => setActive(e.detail)}>
      <TabbarItem icon="home-o">标签</TabbarItem>
      <TabbarItem icon="search" dot>
        标签
      </TabbarItem>
      <TabbarItem icon="friends-o" info="5">
        标签
      </TabbarItem>
      <TabbarItem icon="setting-o" info="20">
        标签
      </TabbarItem>
    </Tabbar>
  )
}
```

### 自定义图标

```jsx
function Demo() {
  const [active, setActive] = react.useState('home')

  return (
    <Tabbar active={active} onChange={(e) => setActive(e.detail)}>
      <TabbarItem
        info="3"
        renderIcon={
          <Image
            src="https://img.yzcdn.cn/vant/user-inactive.png"
            mode="aspectFit"
            style="width: 30px; height: 18px;"
          ></Image>
        }
        renderIconActive={
          <Image
            src="https://img.yzcdn.cn/vant/user-active.png"
            mode="aspectFit"
            style="width: 30px; height: 18px;"
          ></Image>
        }
      >
        自定义
      </TabbarItem>
      <TabbarItem icon="search">标签</TabbarItem>
      <TabbarItem icon="setting-o">标签</TabbarItem>
    </Tabbar>
  )
}
```

### 自定义颜色

```jsx
function Demo() {
  const [active, setActive] = react.useState(0)
  return (
    <Tabbar
      activeColor="#07c160"
      inactiveColor="#000"
      active={active}
      onChange={(e) => setActive(e.detail)}
    >
      <TabbarItem icon="home-o">标签</TabbarItem>
      <TabbarItem icon="search">标签</TabbarItem>
      <TabbarItem icon="friends-o">标签</TabbarItem>
      <TabbarItem icon="setting-o">标签</TabbarItem>
    </Tabbar>
  )
}
```

### 结合自定义 tabBar

请参考 [微信官方文档](https://developers.weixin.qq.com/miniprogram/dev/framework/ability/customTabbar.html) 与 [代码片段](https://developers.weixin.qq.com/s/vaXgTsmQ7hnm)。

### TabbarProps [[详情]](https://github.com/AntmJS/vantui/tree/main/packages/vantui/types/tabbar.d.ts)

| 参数                | 说明 | 类型                                                                                                                                                                                                                                 | 默认值 | 必填    |
| ------------------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------ | ------- |
| active              | -    | _&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>_                                                                                                                                                                                  | -      | `false` |
| activeColor         | -    | _&nbsp;&nbsp;string<br/>_                                                                                                                                                                                                            | -      | `false` |
| inactiveColor       | -    | _&nbsp;&nbsp;string<br/>_                                                                                                                                                                                                            | -      | `false` |
| fixed               | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                           | -      | `false` |
| placeholder         | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                           | -      | `false` |
| border              | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                           | -      | `false` |
| zIndex              | -    | _&nbsp;&nbsp;number<br/>_                                                                                                                                                                                                            | -      | `false` |
| safeAreaInsetBottom | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                                                                                                                           | -      | `false` |
| children            | -    | _&nbsp;&nbsp;ReactNode<br/>_                                                                                                                                                                                                         | -      | `false` |
| onChange            | -    | _&nbsp;&nbsp;(event:&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;detail:<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;string<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&brvbar;&nbsp;number<br/>&nbsp;&nbsp;})&nbsp;=>&nbsp;void<br/>_ | -      | `false` |

### TabbarItemProps [[详情]](https://github.com/AntmJS/vantui/tree/main/packages/vantui/types/tabbar.d.ts)

| 参数             | 说明 | 类型                                                                                                                             | 默认值 | 必填    |
| ---------------- | ---- | -------------------------------------------------------------------------------------------------------------------------------- | ------ | ------- |
| info             | -    | _&nbsp;&nbsp;ReactNode<br/>_                                                                                                     | -      | `false` |
| name             | -    | _&nbsp;&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>_                                                                              | -      | `false` |
| icon             | -    | _&nbsp;&nbsp;string<br/>_                                                                                                        | -      | `false` |
| dot              | -    | _&nbsp;&nbsp;boolean<br/>_                                                                                                       | -      | `false` |
| iconPrefix       | -    | _&nbsp;&nbsp;string<br/>_                                                                                                        | -      | `false` |
| renderIconActive | -    | _&nbsp;&nbsp;ReactNode<br/>_                                                                                                     | -      | `false` |
| renderIcon       | -    | _&nbsp;&nbsp;ReactNode<br/>_                                                                                                     | -      | `false` |
| children         | -    | _&nbsp;&nbsp;ReactNode<br/>_                                                                                                     | -      | `false` |
| onClick          | -    | _&nbsp;&nbsp;(<br/>&nbsp;&nbsp;&nbsp;&nbsp;name:&nbsp;string&nbsp;&brvbar;&nbsp;number<br/>&nbsp;&nbsp;)&nbsp;=>&nbsp;void<br/>_ | -      | `false` |
