# Fung-templates

一个基于 **Fung** 的模板仓库。

## 创建一个远程仓库

在 **GitHub** 上创建一个仓库，把模板作为分支推送到模板仓库。

每个模板和分支是一一对应的关系。

## 添加配置文件

在你的模板跟目录中添加一个名为`fung-config.json`的配置文件。

*fung-config.js*
```
{
  "prompts": {
    "name": {
      "type": "string",
      "required": true,
      "message": "Project name"
    },
    "description": {
      "type": "string",
      "required": true,
      "message": "Project description",
      "default": "A Vue.js project"
    },
    "author": {
      "type": "string",
      "message": "Author"
    },
    "license": {
      "type": "string",
      "message": "License",
      "default": "MIT"
    }
  },
  "completeMessage": "To get started:\n\n  npm install\n  npm run dev"
}
```

* `prompts`: a series of  questions or choices.
* `completeMessage`: 构建完成后输出的信息。

## Placeholder

Use `{{ placeholder }}` to add placeholders in the files.

```
{
  "name": "{{ name }}",
  "description": "{{ description }}",
  "version": "{{ version }}",
  "author": "{{ author }}",
  "license": "{{ license }}",
  "scripts": {},
  "dependencies": {},
  "devDependencies": {}
}
```