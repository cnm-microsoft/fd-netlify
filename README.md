# fd-netlify
配合netlify反代，加速网站访问，可以反代huggingface域名
LINUX DO
【教程】受够了cf反代hf站点的龟速？来用自己的cdn吧！
开发调优
开发调优, Lv1
配置优化
真诚、友善、团结、专业，共建你我引以为荣之社区。《常见问题解答》
❤️ 再忍不住，也不要做这种事啊 ❤️
【教程】受够了cf反代hf站点的龟速？来用自己的cdn吧！ 
开发调优
开发调优, Lv1
配置优化

返回

天哥在写bug
chengtx
文化宣导员

2
1月 30 日
image
因为hf不能直接自定义space的域名，cf worker优选反代高峰期根本用不了
琢磨了一会，套上了自己的亚太cdn :tieba_047:
教程来了：
0.Github创建仓库并创建反代代码
Github创建新仓库，名字随意
创建好后新建文件netlify.toml 代码如下

[[redirects]]
  from = "/*"
  to = "https://xxxxx.hf.space/:splat"
  status = 200
把里面的xxxxx.hf.space换成你的hf链接

1.到netlify部署

app.netlify.com
Netlify
Start building the best web experiences in record time

进入netlify，右上角github登录
进到控制台后导入仓库

image
image
image
image
导入后滑到最下面部署
image
部署完成后进入项目控制面板，在左侧找到自定义域名并添加，然后正常套cdn回源到netlify即可
Q&A：
Q1.为什么不用vercel？
A1:实测下来vercel反代会有些问题，会直接跳转到hf的域名，于是放弃
