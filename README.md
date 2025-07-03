npm init -y
npm i -D vitepress
npx vitepress init

在.vitepress\config.mts里添加
export default defineConfig({
  base:"/",
  outDir:"docs",
})

解释下这个base，outDir的作用
1、修改base为"/ssg/"
打包后的html里的各种资源路径会自动加上"/ssg/"前缀 如：
```html
<link rel="stylesheet" href="/ssg/style.css">
```
2、outDir:"docs"的作用是打包后的文件放在根目录docs中
如果是outDir:"dist/demo" 则打包后的文件放在dist/demo中

然后执行npm run docs:build
会在根目录下生成docs目录，里面就是打包后的文件，这个文件是一定要提交到仓库的
