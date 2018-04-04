# Fung-templates

It's a template repository for Fung.

[中文文档](https://github.com/Leechikit/fung-templates/blob/master/README-cn.md)

## Create a repository

Create a repository on GitHub, and push some templates as branches to the repository.

There is a one-to-one match between each templates and each branches.

**template structure**:

```
├── template/
│   ├── ...
│   └── package.json
└── fung-config.js
```

## Add a template folder

add a template folder to save your template.

## Add a config file

add a config file named `fung-config.json` in your template folder.

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

* `prompts`: a question array containing [Question Object](#question-object).
* `completeMessage`:show a message after completing the build command.

## Question Object

A question object is a `hash` containing question related values:

- **type**: (String) Type of the prompt. Defaults: `input` - Possible values: `input`, `confirm`,
`list`, `rawlist`, `expand`, `checkbox`, `password`, `editor`
- **message**: (String|Function) The question to print. If defined as a function, the first parameter will be the current inquirer session answers.
- **default**: (String|Number|Array|Function) Default value(s) to use if nothing is entered, or a function that returns the default value(s). If defined as a function, the first parameter will be the current inquirer session answers.
- **choices**: (Array|Function) Choices array or a function returning a choices array. If defined as a function, the first parameter will be the current inquirer session answers.
Array values can be simple `strings`, or `objects` containing a `name` (to display in list), a `value` (to save in the answers hash) and a `short` (to display after selection) properties. 

## Placeholder

Use `{{ placeholder }}` to add placeholders in the files.

You can use expressions and operators in the placeholder.

```
{
  "name": "{{ name }}",
  "description": "{{ description }}",
  "version": "{{ version }}",
  "author": "{{ author ? author : 'leechikit'}}",
  "license": "{{ license }}",
  "scripts": {},
  "dependencies": {},
  "devDependencies": {}
}
```