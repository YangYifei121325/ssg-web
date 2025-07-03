npm init -y
npm i -D vitepress
npx vitepress init

在.vitepress\config.mts里添加
export default defineConfig({
  base:"/github仓库名称/",
  outDir:"docs",
})

解释下这个base，outDir的作用
1、如果你的仓库名称是ssg，修改base为"/ssg/"
打包后的html里的各种资源路径会自动加上"/ssg/"前缀 如：
```html
<link rel="stylesheet" href="/ssg/style.css">
部署后的请求则是
https://用户名.github.com/ssg/style.css
如果为"/" 则，部署后的请求css路径就是
https://用户名.github.com/style.css
```
如果是"/" 则，部署后的请求css路径就是

2、outDir:"docs"的作用是打包后的文件放在根目录docs中
如果是outDir:"dist/demo" 则打包后的文件放在dist/demo中

然后执行npm run docs:build
会在根目录下生成docs目录，里面就是打包后的文件，这个文件是一定要提交到仓库的
