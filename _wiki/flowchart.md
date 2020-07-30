---
layout: wiki
title: Flow Chart
categories: flowchart
description: flowchart
keywords: flowchart
flow: true

---
### flowchart

```flow
st=>start: Start
e=>end
op1=>operation: My Operation
sub1=>subroutine: My Subroutine|invalid
cond=>condition: Yes or No?
cond2=>condition: Yes or No?
io=>inputoutput: catch something...
io2=>inputoutput: catch something...

st->op1->cond
cond(yes)->io->cond2
cond(no)->sub1(right)->op1
cond2(yes)->io2->e
cond2(no)->op1
```


參考:  
<a href="http://flowchart.js.org/">http://flowchart.js.org/</a>