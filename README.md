# fly-tools
开发工具


json 编码/解码 转GET参数 GET参数转json unicode转中文 中文转unicode 
```javascript
//json格式化
//https://stackoverflow.com/questions/4810841/pretty-print-json-using-javascript
console.log(JSON.stringify(JSON.parse({"id":1}), null, 2))

//压缩
console.log(JSON.stringify({"id":1}))

//GET转json
let p = new URLSearchParams("id=1&name=za")
let j = {}
p.forEach((v, k) => {
    console.log(k, v)
    j[k] = v 
})
console.log(j)
```