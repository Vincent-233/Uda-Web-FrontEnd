## CSS选择器
- Cascading Style Sheets，为样式服务，如何将HTML和css文件中样式关联在一起呢？答案是`CSS Selector` 
- CSS选择器，最基本的有如下几种：
    - Id， Tag中定义的ID属性
    - Tag，Tag各类，比如 button, div, table 等
    - Class，Tag中定义的Class属性
    - Attribute，通过Attribute的值进行过滤

![](https://s2.loli.net/2022/09/12/4D6su8HZKIamySz.png)

- CSS举例
    - Tag，例如设置段落样式
    ``` css
    p { color:red;}
    ```
    - Class，Tag含class属性
    ``` css
    .brand { color:blue;}
    ```
    - Id， Tag含id属性
    ```css
    #solo  {color: purple}
    ```
    - Attribute
    ```css
    /* Links with "example" anywhere in the URL */
    a[href*="example"] {
    background-color: silver;
    }
    ```
- 多个选择器放一起
    ```css
    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
    font-family: "Helvetica", "Arial", sans-serif;
    }
    ```
除此之处，还有Pseudo-classes等甚于历史和动作的选择器，可参考[MDN CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


## CSS与HTML的关联
### inline
直接在Tag的Style属性中写CSS，如：
  ``` html
  <p style="color: red; font-size: 20px;">I'm learning to code!</p>
  ```
  优点：非常直接精确地设置元素的样式    
  缺点：维护性差，代码冗余，需求变化后代码工作量大

### Style标签
在Head中包含Style标签，相同页面可以引用
``` html
<head>
<style>
    p {
    color: red;
    font-size: 20px;
    }
</style>
</head>
```
比inline多了css代码的重用，但仅限单页面级别

### 外部CSS文件
单独编写css文件，然后在HTML的Head中用link标签将其引入:
```html
<link href="./style.css" type="text/css" rel="stylesheet" />
```
此外在css文件中也可以引入其它css文件
```css
// at the top of your main CSS file

@import “./layout”;
@import “./images”;
@import “./blog-cards”;
```
大型项目推荐使用css文件，有利用于代码利用和扩展

![](https://s2.loli.net/2022/09/12/ApTLs8SiVONPlqc.png)