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

* `prompts`: 一个包含[问题对象](#questions)的数组。
* `completeMessage`: 构建完成后输出的信息。

## 问题对象

A question object is a `hash` containing question related values:

- **type**: (String) Type of the prompt. Defaults: `input` - Possible values: `input`, `confirm`,
`list`, `rawlist`, `expand`, `checkbox`, `password`, `editor`
- **message**: (String|Function) The question to print. If defined as a function, the first parameter will be the current inquirer session answers.
- **default**: (String|Number|Array|Function) Default value(s) to use if nothing is entered, or a function that returns the default value(s). If defined as a function, the first parameter will be the current inquirer session answers.
- **choices**: (Array|Function) Choices array or a function returning a choices array. If defined as a function, the first parameter will be the current inquirer session answers.
Array values can be simple `strings`, or `objects` containing a `name` (to display in list), a `value` (to save in the answers hash) and a `short` (to display after selection) properties.

## 占位符

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