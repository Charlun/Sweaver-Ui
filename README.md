# SweaverUi
Ui lib for my project (practice now)

## 基础配置
### 引入

```javascript
npm i Sweaver-ui
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
#### 属性
| 属性作用     | 属性名     | 类型   |备注|
|:--------:|:---------:|:-------:|:-------:|
| 设置按钮高度  | Height    | Number     |单位px|
| 设置按钮宽度 | Width  | Number     |单位px|
| 设置按钮背景颜色 | BgColor  | String     |/|
| 设置文本颜色 | Color  | String     |/|
| 设置文本大小 | FSize  | String     |单位不限|
| 设置按钮圆角| Radius  | Number     |单位px|

