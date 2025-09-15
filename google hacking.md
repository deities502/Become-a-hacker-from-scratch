```markdown
# Google Hacking

Google Hacking 原指利用 Google 搜索引擎搜索信息来进行入侵的技术和行为；现指利用各种搜索引擎搜索信息来进行入侵的技术和行为。Google Hacking 并不是单指 Google 浏览器，指的是一种信息收集方式。

我们平常在浏览器中直接加上关键词进行搜索，搜索结果中很多内容都不是我们想要的。因此我们可以通过搜索引擎提供的一些特殊语法，帮助我们快速搜索到目标内容。

这种在信息收集阶段很有用，可以让我们快速的发现一些感兴趣的内容。轻量级的搜索可搜索出一些遗留后门，不想被发现的后台入口，中量级的搜索出一些用户信息泄露，源代码泄露，未授权访问等等，重量级的则可能是mdb文件下载，CMS 未被锁定install页面，网站配置密码，SQL注入、远程文件包含漏洞等重要信息

## 基本用法

### site

- **语法**：`site:网址`
- **功能**：搜索指定域名的网页内容，可用于搜索子域名或与该域名相关的内容。

示例：
```plaintext
site:sohu.com inurl:php?id
```

### filetype

- **语法**：`filetype:文件类型`
- **功能**：搜索指定文件类型。

示例：
```plaintext
site:xx.com filetype:asp
site:xx.com filetype:php
site:xx.com filetype:jsp
site:xx.com filetype:aspx
```

### inurl

- **语法**：`inurl:keyword`
- **功能**：搜索 URL 中存在特定关键字的网页，可用于搜寻有注入点的网站。

示例：
```plaintext
inurl:.php?id=
inurl:.jsp?id=
inurl:.asp?id=
inurl:/admin/login.php
inurl:login
inurl:admin
```

### intitle

- **语法**：`intitle:keyword`
- **功能**：搜索标题中存在特定关键字的网页。

示例：
```plaintext
intitle:后台登录
intitle:管理员登录
intitle:index of
intitle:index of "parent directory"
intitle:index of "password"
```

### intext

- **语法**：`intext:keyword`
- **功能**：搜索正文中存在特定关键字的网页。

示例：
```plaintext
intext:Powered by Discuz
intext:powered by wordpress
intext:Powered by *CMS
intext:powered by xxx inurl:login
```

---

## 逻辑运算符

### 逻辑或 OR

- **语法**：`A OR B` 或 `A + B`
- **功能**：查找含有检索词 A 或 B 之一，或同时包含 A 和 B 的网页。

### 逻辑与 AND

- **语法**：`A AND B` 或 `A * B`
- **功能**：查找同时包含检索词 A 和 B 的网页。

### 逻辑非 NOT

- **语法**：`NOT keyword` 或 `-keyword`
- **功能**：强制搜索结果中不出现此关键字。

### 完整匹配

- **语法**：`"keyword"`
- **功能**：强制搜索结果完整出现此关键字，不对关键词进行切割。

---

## 总结

以下是常见的 Google Hacking 语法及其用途：

| 语法                | 含义                               | 利用示例                                         |
|---------------------|------------------------------------|--------------------------------------------------|
| `intext:关键字`     | 搜索网页正文中含有关键字的网页       |                                                  |
| `intitle:关键字`    | 搜索标题中含有关键字的网页           |                                                  |
| `cache:关键字`      | 搜索缓存中的内容                     |                                                  |
| `define:关键字`     | 搜索关键字的定义                     |                                                  |
| `filetype:文件名`   | 搜索特定的文件类型                   |                                                  |
| `info:关键字`       | 搜索指定站点的基本信息               |                                                  |
| `inurl:关键字`      | 搜索含有关键字的 URL 地址            | 查找别人留下的 webshell，如 `inurl:diy.asp`        |
| `link:关键字`       | 查找与关键字做了链接的 URL 地址      | 可能搜索到敏感信息                               |
| `site:域名`         | 返回域名中所有的 URL 地址            |                                                  |
| `stocks:`           | 搜索公司股票市场信息                 |                                                  |
| `insubject`         | 搜索 Google 组的标题行               |                                                  |
| `msgid`             | 搜索新闻组帖子的标识符和字符串       |                                                  |
| `group`             | 搜索 Google 组帖子的题目             |                                                  |
| `author`            | 搜索新闻组帖子的作者                 |                                                  |
| `bphonebook`        | 仅搜索商业电话号码簿                 |                                                  |
| `rphonebook`        | 仅搜索住宅电话号码簿                 |                                                  |
| `phonebook`         | 搜索商业或住宅电话号码簿             |                                                  |
| `daterange`         | 搜索某个日期范围内被索引的网页       |                                                  |
| `inanchor`          | 搜索链接锚文本中的关键字             |                                                  |
```

