# 01. 样式篇
---
1. 行内样式 inline style
2. 内部样式 
3. 外部样式

# 02. font
---
1. font-family
2. font-weights
3. font-style
4. font-size

- 复合样式写法：
5. font：font-style font-weight font-size（必要的）/line-height font-family（必要的）
- 注意：其中font-size和font-family两者是必要的，如果没有这两个所有设置的字体样式将无效。

# 03. text
---
1. color
2. text-align
3. text-decoration
- none
- underline
- overline
- line-through
4. text-indent
5. line-height
- 行间距由上边距+文本高度+下边距组成的。

# 04. background
---
**背景颜色：**
1. background-color
- transparent
- color

**背景图片：**
2. background-image
- none
- url(url)

**背景平铺：**
3. background-repeat
- repeat
- no-repeat
- repeat-x
- repeat-y

**背景图片位置：**
4. background-position：x,y

**`方位名词：`**
- 如果指定的两个值都是方位名词，则两个值前后顺序无关，比如top，left 和 left，top效果是一致的。（因为left，right肯定指的是x轴。而top，bottom肯定指的是y轴。）
- 如果只指定了一个方位名词，另一个省略，则第二个值默认居中对齐。
- top，center，bottom，left，right
- 语法：background-position：right,top

**`精确单位：`**
- 如果参数值是精确坐标，那么第一个肯定是x坐标，第二个是y坐标。
- 如果只指定一数值，那么该数值一定是x坐标，另一个默认垂直居中。
- 语法：background-position：20px 50px.

**`参数是混合单位：`**
- 如果指定的两个值是精确单位和方位名词混合使用的，则第一个值是x坐标，第二个值是y坐标。（混合单位一定是有顺序关系的）

**背景图像固定：**
> 属性设置背景图像是否固定或者随着页面的其余部分滚动。
> background-attachment后期可以制作视差滚动的效果。
5. background-attachment
- scroll 滚动的，背景图像是随对象内容滚动的（默认值）。
- fixed  固定的，背景图像固定。

**背景图片简写：**
> 背景图片的简写不像font那样有明确的顺序要求。
> 但是通常我们常用的方式顺序如下。
background:背景颜色 背景图片 背景平铺 背景图片滚动 背景图片位置；

**背景色半透明：**
```css
  /* 使用rgba方式完成背景色半透明 */
  background:rgba(0,0,0,0.3)
```
- 最后一个参数是alpha透明度，取值范围在0~1之间。
- 在实际开发中习惯将0.3的0省略掉，写为background:rgba(0,0,0,.3)。
- 注意：背景半透明是指盒子背景半透明，盒子里面的内容不受影响。