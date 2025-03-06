创建一个新的文件夹
1.初始化环境
npm init -y
2.安装ts到本环境
npm install -D typescript
3.初始化一个tsconfig.json文件
npx tsc --init 
4.对package.json文件进行修改

5.对tsconfig.json进行一些设置
从上到下依次是：
主文件入口，编译出来的文件地址，是否有ts说明，出问题能更好溯源
  "rootDir": "./src"
  "outDir": "./dist"
  
  "declaration": true
  "sourceMap": true
6.编写好主文件后，进行npm run build，编译文件到dist目录
一个声明文件，一个是内容文件

7.现在就可以进行登录npm然后发布啦
npm login

npm publish

注意事项
1.如果发布失败，查看一下是不是名字在npm上已经存在，在package.json里面更改name即可
2.每次发布都必须更新版本：
● patch: 增加补丁版本（最后一位），例如从 1.0.0 升级到 1.0.1。
● minor: 增加次版本（中间一位），例如从 1.0.0 升级到 1.1.0。
● major: 增加主版本（第一位），例如从 1.0.0 升级到 2.0.0。




