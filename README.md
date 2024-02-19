# SweaverUi
Ui lib for my project (practice now)

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

<br>
<br>
<br>

# 更多组件正在开发中...