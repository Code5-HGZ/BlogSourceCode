## JS 常用函数

> **首字母大写，其余小写**
>
> ```javascript
> /**
>  * @param {string} str 要转换的字符串 
>  */
> function capitalize(str) {
>     str = str.toLowerCase().split("");
>     str[0] = str[0].toUpperCase();
>     return str.join("");
> }
> ```
>