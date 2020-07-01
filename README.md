# eslint prettier work together模版

## Wait what are Eslint and Prettier?
`Eslint is a javascript linter that can help you find syntax or other errors. Eslint can be extended by plugging in pre-defined configs or completely configuring it yourself. Paired with the plugin for vscode, it can show you errors as you type.
Prettier is a code formatter for quite a few languages, including javascript. You can have code being automatically or optionally formatted with it.`
<br>
<br>
当eslint和prettier一起工作时，达到的效果是，eslint能够检测.prettierrc配置的规则，同时prettier能够自动格式化某些.eslintrc中配置规则。


## 安装vscode插件
- ESLint
- Prettier
<br>

## 安装依赖
- eslint
- prettier
- eslint-config-prettier
- eslint-plugin-prettier
<br>

## 配置`.selintrc`文件
In here we basically tell Eslint to:
- Extend from the recommended prettier config
- Register the Prettier plugin we installed
- Show Prettier errors as errors
```
{
  "extends": ["plugin:prettier/recommended", "airbnb"], // 继承airbnb规范
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "warn",
    "no-console": ["warn", { "allow": ["warn", "error"] }]
    ... // 更多rules
   }
 }
```
<br>

## 配置`.prettierrc`文件
```
{
  "printWidth": 80,
  "trailingComma": "none",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  "useTabs": false,
  "bracketSpacing": true,
  "insertPragma": false,
  "arrowParens": "avoid"
}
```
<br>

## 配置`.vscode/settings.json`文件
```
{
  // 确保按save键时自动format格式
  "editor.formatOnSave": true
}

```




