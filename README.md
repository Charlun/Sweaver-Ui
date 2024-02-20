# SweaverUi
Ui lib for my project (practice now)

为了一个练手的博客项目做的ui组件库（就是个小练习）

## 基础配置
### 开始
通过包管理器安装SweaverUi
```javascript
npm i Sweaver-ui
```

随后在你项目的主入口文件中（通常是main.js）引入SweaverUi

全部引入
```javascript
import * as SweaverUI from 'sweaver-ui';

Object.keys(SweaverUI).forEach((componentName) => {
  app.component(componentName, SweaverUI[componentName]);
});
```

按需引入（以sweaver-button为例）
```javascript
import {SweaverButton} from 'sweaver-ui';
```
### 在项目全局样式中添加以下css变量可全局快速设定组件颜色配置
```css
:root 
{
  /* 主要颜色 */
  --primary-color: #3498db;

  /* 次要颜色 */
  --secondary-color: #2ecc71;

  /* 背景颜色 */
  --background-color: #f5f5f5;

  /* 边框颜色 */
  --border-color: #ddd;

  /* 内容颜色 */
  --content-color: #ffffff;
}
```
对某个组件进行单独设置颜色将会覆盖全局颜色设定

## 组件
### Sweaver-Button
#### 使用方法
```html
<!-- 文字按钮 -->
<sweaver-button>
  按钮
</sweaver-button>
<!-- 图标按钮 -->
<sweaver-button>
  <svg></svg>
</sweaver-button>
```

#### 属性
| 属性作用     | 属性名     | 类型   |备注|
|:--------:|:---------:|:-------:|:-------:|
| 设置按钮高度  | Height    | Number     |单位px|
| 设置按钮宽度 | Width  | Number     |单位px|
| 设置按钮背景颜色 | BgColor  | String     |/|
| 设置文本颜色 | Color  | String     |/|
| 设置文本大小 | FSize  | String     |单位不限|
| 设置按钮圆角| Radius  | Number     |单位px|

---
### Sweaver-Switch
#### 使用方法
```html
<sweaver-switch>
  <!-- 文字选项 -->
  <span>选项1</span>
  <span>选项2</span>
  <!-- 图标选项 -->
  <svg></svg>
<sweaver-switch/>
```
#### 属性
| 属性作用     | 属性名     | 类型   |备注|
|:--------:|:--------:|:--------:|:--------:|
| 背景颜色   | BgColor   | String  |  / |
| 高度       | Height    | Number  | 单位px |
| 宽度       | Width     | Number  | 单位px |
| 活动条颜色   | ActiveColor | String |  / |
| 活动条高度   | ActiveHeight | Number | 单位px|
| 活动条宽度   | ActiveWidth | String  | 百分比|
| 按钮颜色   | ButtonColor | String  | /|

---

### Sweaver-Input

#### 使用方法

```html
<!-- 默认状态为普通输入框 -->
<Sweaver-Input>
    <!-- 如果有标签写在这里没有则直接使用自闭合标签即可 -->
<Sweaver-Input/>
<!-- 此时为密文输入框 -->
<Sweaver-Input Passward>
```

#### 属性

|  属性作用  |   属性名    |  类型  |  备注  |
| :--------: | :---------: | :----: | :----: |
| 是否为密文 |  Passward   | Boolean |   /    |
|    高度    |   Height    | Number | 单位px |
|    宽度    |    Width    | Number | 单位px |
|   提示语   | Placeholder | String |   /    |
|   初始值   |    Value    | String | /|

---

### Sweaver-CheckBox

#### 使用方法

```html
<!-- 默认状态为多选框 -->
<Sweaver-CheckBox>
    <!-- 如果有标签写在这里没有则直接使用自闭合标签即可 -->
<Sweaver-CheckBox/>
<!-- 此时为单选框 -->
<Sweaver-CheckBox Radio>
```

#### 属性

|  属性作用  |   属性名    |  类型   | 备注 |
| :--------: | :---------: | :-----: | :--: |
| 是否为单选 |    Radio    | Boolean |  /   |
|    大小    |    Size     | String  |  /   |
| 选框组标识 |    Name     | String  |  /   |

---

### Sweaver-SearchBar

#### 使用方法

```html
<Sweaver-SearchBar>
```

#### 属性

| 属性作用 |   属性名    |  类型  |  备注  |
| :------: | :---------: | :----: | :----: |
|   高度   |   Height    | Number | 单位px |
|   宽度   |    Width    | Number | 单位px |
|  提示语  | Placeholder | String |   /    |
|  初始值  |    Value    | String |   /    |

---

### Sweaver-AvatarMenu

#### 使用方法

```html
<Sweaver-AvatarMenu Src="此处为头像src">
    <!-- 在此处添加你的菜单 -->
</Sweaver-AvatarMenu>
```

#### 属性

|          属性作用          | 属性名 |  类型  |  备注  |
| :------------------------: | :----: | :----: | :----: |
|            大小            |  Size  | Number | 单位px |
|          头像路径          |  Src   | String |   /    |
| 当头像无法显示时的替代文本 |  Alt   | String |   /    |

<br>
<br>
<br>

# 更多组件正在开发中...