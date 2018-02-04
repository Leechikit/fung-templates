# Fung-templates

It's a template repository for Fung.

## Create a repository

Create a repository on GitHub, and push some templates as branches to the repository.

There is a one-to-one match between each templates and each branches.

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

* `prompts`: a series of  questions or choices.
* `completeMessage`:show a message after completing the build command.

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