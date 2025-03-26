# what
通过 HTML+CSS+JS 做一个说明书、样本生成模板

1. 设计说明书的 css 样式模板
2. 添加 editor 模板（实时预览）
3. 构建后台数据库
4. 发布

# how
## 🧠 Editor 方案设计 by ChatGPT

方式一：本地 HTML 编辑器 + JS 实现导出
适合你离线使用，技术掌控强，自主性高。

步骤 1：创建一个 editor.html 页面
这个页面提供一个表单界面，用户通过填写表单字段来输入产品信息。

步骤 2：用户点击“生成”按钮时，JavaScript 生成 HTML 字符串
你可以使用 template literal（模板字符串）在 JS 中拼出最终的 HTML。

步骤 3：用 Blob + a 标签 实现本地 HTML 文件下载

```
const blob = new Blob([htmlContent], {type: 'text/html'});
const link = document.createElement('a');
link.href = URL.createObjectURL(blob);
link.download = 'product.html'; 
link.click();
```
