## JS 常用功能封装



```javascript
/**
 * 首字母大写，其余小写
 * @param {string} str 要转换的字符串 
 */
function capitalize(str) {
    str = str.toLowerCase().split("");
    str[0] = str[0].toUpperCase();
    return str.join("");
}
```



```javascript
/**
 * 统计字符串中每个字符的出现频率，返回一个 Object，key 为统计字符，value 为出现频率
 * @param {string} str 需要统计的字符串
 */
function count(str) {
    result = {}

    // 去除空格并转换为字符数组
    str = str.replace(" ", "").split("");

    // 重复字符串只保留一个作为健
    let keys = []
    for(let s of str){
        if(!keys.includes(s)){
            keys.push(s)
            result[s] = 0;
        }
    }

    // 统计字符串出现次数
    for(let s of str){
        result[s] += 1;
    }

    return result;
}

```



```javascript
/**
 * css 中经常有类似 background-image 这种通过 - 连接的字符，通过 javascript 
 * 设置样式的时候需要将这种样式转换成 backgroundImage 驼峰格式
 * font-size ==> fontSize
 * -webkit-border-image ==> webkitBorderImage
 * @param {string} sName 需要转换的css属性
 */
function cssStyle2DomStyle(sName) {
    // 将css属性根据 - 分割为单词数组, 如果属性有前缀, 去除前缀
    sName = sName.split("-")
    for(let i = 0; i < sName.length; i++) {
        if(sName[i] == ""){
            sName.splice(i, 1)
        }
    }

    // 从单词数组第二个元素开始将单词首字母转换为大写
    for(let i = 1; i < sName.length; i++){
        let tmp = sName[i].split("")
        tmp[0] = tmp[0].toUpperCase()
        tmp = tmp.join("")
        sName[i] = tmp
    }

    return sName.join("")
}
```

