---
layout: post
title: Javascript 合併 Json Object
categories: [Javascript]
tags: [Tech.]
description: 使用 Javascript 合併 Json Object
keywords: Javascript, json
---

使用 JavaScript 將 2 份不同的 Json object 以識別欄位的值進行合併


### 先來看看第一個 JSON 的內容
```json
    [
        {id:1,name:'aaa'},
        {id:3,name:'bbb'},
        {id:5,name:'ccc'},
        {id:7,name:'ddd'}     
   ]
```

### 先來看看第二個 JSON 的內容
```json
    [
        {id:1,parameter1:'x', parameter2:'y', parameter3:'z'},
        {id:3,parameter1:'u', parameter2:'v', parameter3:'w'},
        {id:5,parameter1:'q', parameter2:'w', parameter3:'e'},
        {id:7,parameter1:'xx', parameter2:'xx', parameter3:'xx'},
        {id:9,name:'eee'}
    ]
```
### 合併後的結果
```json
    [
        {"id":1,"name":"aaa","parameter1":"x","parameter2":"y","parameter3":"z"},
        {"id":3,"name":"bbb","parameter1":"u","parameter2":"v","parameter3":"w"},
        {"id":5,"name":"ccc","parameter1":"q","parameter2":"w","parameter3":"e"},
        {"id":7,"name":"ddd","parameter1":"xx","parameter2":"xx","parameter3":"xx"},
        {"id":9,"name":"eee"}
    ]
```

### JavaScript
```javascript
var json1 = [{id:1,name:'aaa'},
     {id:3,name:'bbb'},
     {id:5,name:'ccc'},
     {id:7,name:'ddd'}     
   ];

var json2 = [{id:1,parameter1:'x', parameter2:'y', parameter3:'z'},
     {id:3,parameter1:'u', parameter2:'v', parameter3:'w'},
     {id:5,parameter1:'q', parameter2:'w', parameter3:'e'},
     {id:7,parameter1:'xx', parameter2:'xx', parameter3:'xx'},
     {id:9,name:'eee'}
    ];

function joinObjects() {
  var idMap = {};
  // Iterate over arguments
  for(var i = 0; i < arguments.length; i++) { 
    // Iterate over individual argument arrays (aka json1, json2)
    for(var j = 0; j < arguments[i].length; j++) {
       var currentID = arguments[i][j]['id'];
       if(!idMap[currentID]) {
          idMap[currentID] = {};
        }
      // Iterate over properties of objects in arrays (aka id, name, etc.)
      for(key in arguments[i][j]) {
          idMap[currentID][key] = arguments[i][j][key];
      }
    }
  }
  
  // push properties of idMap into an array
  var newArray = [];
  for(property in idMap) {
    newArray.push(idMap[property]);
  }
  return newArray;
}
joinObjects(json1, json2)
document.write(JSON.stringify(joinObjects(json1, json2)));
```

# CodePen Sample

<p class="codepen" data-height="663" data-theme-id="dark" data-default-tab="js,result" data-user="BensonCho" data-slug-hash="yLYdZeO" style="height: 663px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Json Merge Sample">
  <span>See the Pen <a href="https://codepen.io/BensonCho/pen/yLYdZeO">
  Json Merge Sample</a> by Benson (<a href="https://codepen.io/BensonCho">@BensonCho</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
