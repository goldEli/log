# JavaScript Style Guide

1. 风格：prettier（vscode 安装perttier插件）。

2. 一个函数不能超过50行，一个函数只做一件事情。

3. 一个文件不能超过250行。

4. 中文必须要英文双引号。

5. 文件名或者变量名须具有描述性。

6. 使用 === 和 !== ，禁止使用 == 和 !=。

7. 尽量少用 if else，禁止在 else 中嵌套if else。

```
// bad
if (a === 1) {
  // do somthing
} else {
  // do something
}

// good 
if (a === 1) {
  // do somthing
  return
} 
// do something

```

8. 每行代码结束，使用分号。

9. 给函数命名，这在做堆栈的时候很有帮助：
```
// bad
var log = function (msg) {
  console.log(msg);
};

// good
var log = function log(msg) {
  console.log(msg);
};
```

10.文件名与类名完全相同
```
// file contents
class CheckBox {
  // ...
}
module.exports = CheckBox;

// in some other file
// bad
var CheckBox = require('./checkBox');

// bad
var CheckBox = require('./check_box');

// good
var CheckBox = require('./CheckBox');

```
