# includefile-loader
include .js .css .html ...

## 安装

**Install**

```bash
npm install --save-dev includefile-loader
```

## 注意事项 》不要相互嵌套《 否则有不好的结果

## 案例
```html
|include
--|a.js
--|b.js
--|base.html
--|body.html
--|footer.html
--|header.html
--|style.css
|text.html
```

### text.html
```html
<include src="include/base.html">
  <include src="./include/header.html"></include>
  <include src="./include/body.html"></include>
  <include src="./include/footer.html">
    <include src="./include/header.html"></include>
  </include>
</include>
```

### base.html
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <include src="style.css" />
  </head>
  <body>
      <!-- {{ include }} -->
  </body>
</html>
```

### 懒! 结果就不贴了
