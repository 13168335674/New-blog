# Build

1. 添加新文章

```
cd /docs/blog
添加新 md 文件
```

2. 配置访问目录

```
cd docs/.vuepress
vim conifg.js

···
sidebar: {
  "/blog/": [
    {
      title: "new article",
      path: "new article",
    },
  ]
}
···
```

3. 部署

```
sh deploy.sh
```
