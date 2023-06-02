# Markdown editor Using React （Document）

## Introduction

这个在线markdown editor可以为用户提供**实时**的markdown to Text **渲染**。用户在左面的markdown textfield输入md内容，相应的Text会在右边的textfield同步显示出来。

主要涉及了

- react project的部署
- html 和css的用法
- 利用`{useState} from "react"`在组件之间传递参数
- 文本框的使用
- `*ReactMarkdown* from "react-markdown"`的使用

<img src="D:./intro.png" style="zoom:50%;" />

## 项目结构

MY-MARKDOWN-EDITOR\SRC
│  App.css
│  App.js
│  App.test.js
│  editorContext.js
│  index.css
│  index.js
│  reportWebVitals.js
│  setupTests.js
│  
└─components
        markedInput.jsx
        result.jsx
        component.css

- App.js 是 root component，是application的主容器
- editorContext.js
- components里面的两个jsx 负责两个文本框的功能



## 依赖

```json
"marked": "^5.0.4",
"react": "^18.2.0",
"react-dom": "^18.2.0",
"react-scripts": "5.0.1",
"react-markdown": "^8.0.7",
"styled-components": "5.3.11",
"web-vitals": "^2.1.4"
```



## App.js

在App() 里面定义了一个`useState()`的hook 函数

`const contextValue` 是一个对象，保存了 `markdownText` 和 `setMarkdownText` 的值。这个对象可以使用 React 的 Context API 将这些值传递给其他组件。

 `markdownText` 将存储 Markdown 文本的内容，而 `setMarkdownText` 将用于更新这个内容。通过使用 `useState` 钩子，可以实现**实时渲染**



### markedInput.jsx

把markdown text利用一个`onInputChange` 函数放到` {setMarkdownText}` 里面，这样别的组件就可以访问了



## result.jsx

获取`markdownText`。 在html里面利用 `ReactMarkdown`标签把`markdownText`变成plain text



### App.css

app.js 样式

### component.css

两个.jsx 样式
