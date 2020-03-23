# ES6-LESSONS

## LESSON 1
#### 初始化文件,搭建ES6的基本开发环境,使ES6的语法自动转变成ES5的语法

##### 创建 `dist` 文件夹存放js文件. 创建 `src` 文件夹.

使用命令

> npm init -y

初始化项目, 在根目录下产生文件 `package.json`

```metadata json
{
  "name": "es6",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

### 全局安装  Babel-cli

使用命令安装 `babel-cli`

> npm install -g babel-cli

本地安装babel-preset-es2015 和 babel-cli

> npm install --save-dev babel-preset-es2015 babel-cli

查看文件 `package.json` 会发现多出下列配置信息

```metadata json
"devDependencies": {
    "babel-cli": "^6.24.1",
    "babel-preset-es2015": "^6.24.1"
  }
```

在根目录下新建.babelrc文件，并打开录入下面的代码

```metadata json
{
    "presets":[
        "es2015"
    ],
    "plugins":[]
}
```

这个文件我们建立完成后，现在可以在终端输入的转换命令了，这次ES6成功转化为ES5的语法。

> babel src/index.js -o dist/index.js

#### 简化转换命令

在学习vue 的时候，可以使用npm run build 直接利用webpack进行打包，在这里也希望利用这种方式完成转换。打开package.json文件，把文件修改成下面的样子。

```metadata json
{
  "name": "es6",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "babel src/index.js -o dist/index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-cli": "^6.24.1",
    "babel-preset-es2015": "^6.24.1"
  }
}
```

修改好后，以后我们就可以使用 `npm run build` 来进行转换了。

