---
title: css常见问题
tags: [面试题]
date: 2024-08-04 18:22:36
draft: true
hideInList: false
isTop: false
feature: 
---
## 什么是BFC

块级格式化上下文（Block Formatting Context，BFC）是 CSS 中的一个重要概念，它是页面中块级盒子布局发生的区域，规定了内部块级盒子如何布局，并且与外部元素互相影响不会影响到外部元素。BFC 有助于解决布局问题，特别是在处理浮动元素、清除浮动、外边距折叠等方面起到关键作用。

具体来说，BFC 具有以下特性：

- 内部的块级盒子会在垂直方向上一个接一个放置。
- 属于同一个 BFC 的两个相邻块级盒子的外边距会发生折叠。
- BFC 的区域不会与浮动盒子重叠，会自动扩展以适应其内容的大小。
- 创建 BFC 的方式包括根元素、浮动元素、绝对定位元素、块级容器、弹性盒子等。

## Position 的值有哪些

1. **static**：
    
    - 默认值，元素按照正常的文档流进行布局，不受`top`、`right`、`bottom`、`left`等属性影响。
2. **relative**：
    
    - 元素相对于其正常位置进行定位，可以使用`top`、`right`、`bottom`、`left`属性进行偏移，但仍然占据原来的空间。
3.  **absolute**：
    
    - 元素相对于最近的定位祖先（`relative`、`absolute`、`fixed`或`sticky`的元素）进行定位，如果没有定位祖先，则相对于初始包含块（通常是`<html>`）进行定位。使用`top`、`right`、`bottom`、`left`属性进行精确位置控制，不保留其在正常文档流中的位置。
4. **fixed**：
    
    - 元素相对于浏览器窗口进行定位，使用`top`、`right`、`bottom`、`left`属性进行精确位置控制，滚动页面时元素保持固定在相同位置。不保留其在正常文档流中的位置。
5. **sticky**：
    
    - 元素根据用户的滚动位置进行定位，在其父元素内切换`relative`和`fixed`定位。开始时按照正常文档流进行布局，但在用户滚动到指定的偏移位置时变为固定定位。

## flex布局

基本概念

1. **主轴（Main Axis）** 和 **交叉轴（Cross Axis）**：
    
    - 主轴：flex 项目排列的方向（水平或垂直）。
    - 交叉轴：与主轴垂直的方向。
2. **容器（Container）** 和 **项目（Items）**：
    
    - 容器：应用 `display: flex` 或 `display: inline-flex` 的元素。
    - 项目：容器内的直接子元素。

容器属性

**display**：定义容器为 Flex 布局。
**flex-direction**：定义主轴方向。
**flex-wrap**：定义是否换行。
**justify-content**：定义主轴对齐方式。
**align-items**：定义交叉轴对齐方式。
**align-content**：定义多行对齐方式。

项目属性

**order**：定义项目排列顺序。
**flex-grow**：定义项目放大比例。
**flex-shrink**：定义项目缩小比例。
**flex-basis**：定义项目在主轴上的初始大小。
**flex**：简写属性，组合了 `flex-grow`, `flex-shrink` 和 `flex-basis`。
**align-self**：覆盖容器的 `align-items` 属性，为单个项目设置对齐方式。

## scss和less的区别


SCSS 和 LESS 是两种 CSS 预处理器，它们都提供了增强的 CSS 功能，如变量、嵌套规则、混合、继承等。然而，它们在语法和功能上有一些区别。以下是两者之间的主要区别：

语法
变量定义
SCSS 使用 $ 符号定义变量
**LESS** 使用 `@` 符号定义变量
混合（Mixins）
**SCSS** 使用 `@mixin` 定义混合，使用 `@include` 引用混合
**LESS** 直接定义一个类，然后使用类名调用
继承
**SCSS** 使用 `@extend` 进行继承
**LESS** 使用 `&:extend` 进行继承
