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

# 05. CSS的三大特性
---
1. **层叠性：** 相同的选择器设置相同的样式，此时一个样式就会覆盖(层叠)另一个样式。层叠性主要解决的是样式冲突问题。
- 样式冲突，遵循的原则是`就近原则`，哪个离结构近就执行哪个样式。
- 样式不冲突，不会层叠（也可以说后面的覆盖前面的）。

2. **继承性：** 子标签会继承父标签的某些样式，如文本颜色和字号。简单理解：继承父业。
- 恰当的使用继承可以简化代码，降低CSS样式的复杂性。
- 子元素可以继承父元素样式（text-，font-，line-这些元素开头的可以继承，以及color）。

3. **优先级：** CSS是通过权重来实现优先级的。

|        选择器         | 选择器优先级 |
| :-------------------: | :----------: |
|  继承或者*（通配符）  |  0，0，0，0  |
|      元素选择器       |  0，0，0，1  |
| 类选择器，伪类选择器  |  0，0，1，0  |
|       ID选择器        |  0，1，0，0  |
| 行内样式 inline-style |  1，0，0，0  |
|   !important重要的    |    无穷大    |

**优先级注意点：**
- 权重是4个数字组成的，但是不会进位。
- 可以理解为类选择器永远大于元素选择器，ID选择器永远大于类选择器。
- 等级判断是从左向右，如果某一位数值相同，则判断下一位数值。
- 注意：继承的权重是0，如果该元素没有直接选中，不管父元素权重多高，子元素得到的权重都是0。

- `权重会叠加，但是不会进位`。

06. 盒子模型
---
> 页面布局三大核心：盒子模型，浮动，定位。

**盒模型的组成：**
content，padding，border，margin

**边框样式：**
1. border-width
2. border-color
3. border-style

- 简写形式：border 1px red solid

