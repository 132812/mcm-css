# css笔记（1）–text-fill-color

## text-fill-color
`text-fill-color`可以重新设置字体的颜色，进行文字遮盖。
主要是用来做镂空文字的（将文字颜色设置为透明，之后使用text-stroke描边）。
`text-stroke` 是`text-stroke-width`和`text-stroke-color`的简写方式，指定了边的宽度和颜色。
**注意**这两个属性是需要加上前缀`-webkit`的，加了之后在firebox中也可以正常运行。

语法：
`-webkit-text-fill-color: [color]`
`-webkit-text-stroke: [width] [color]`

**例子1--镂空文字**：
css 
```
p{
    font-size: 40px;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke:1px #000;
}
```
html
```
    <p>世界有了你，风和日暖</p>
```

**效果展示**

![镂空文字](textPic1.png)

解释：通过将字体颜色设置为transparent，然后对字体的边进行宽度颜色设置。
如果通过`color：transparent`设置的话，则连边都看不到了。

**例子2**：
与`linear-gradient`结合，生成渐变文字。
css
```
    p{
        font-size: 40px;
        background-image:-webkit-linear-gradient(#eee,#f96);
        -webkit-background-clip:text;
        -webkit-text-fill-color:transparent;
        -webkit-text-stroke:1px transparent;
    }

```

**效果展示**

![渐变文字](textPic2.png)

解释：先将文字颜色设置为透明，然后将背景渐变颜色除文本外区域全部裁剪掉。
注意点：使用`text-stroke`描边之后，会使文字柔和许多，不会太过生硬。