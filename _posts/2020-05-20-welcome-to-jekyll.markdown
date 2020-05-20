平台简介
为何选择GitHub Pages
GitHub是一个著名的项目托管平台，其利用Git进行代码版本管理。目前有无数的优秀开源项目托管在GitHub上供人们学习使用。只要保证代码的开源性，你就可以免费享受GitHub提供的服务，这被看做是互联网精神的象征。
GitHub Pages是GitHub提供的一个网站托管部署解决方案。 相比于其他的建站方法，它不需要另外租用网络服务器，也不需要和数据库打交道，甚至不需要对HTML了解得太多。GitHub Pages提供的向导将帮助你得到用来发布的网页。而你需要做的，只是将这些代码放在一个新的仓库（repository）里而已，就像管理你在GitHub上的其他项目一样。一切就是这么简单。而且，它依然是免费的。
在GitHub Pages的官方网站上，你能够看到What is GitHub Pages?主题的介绍视频（YouTube源），并一步一步地教你如何在GitHub上创建自己的第一个网页来向世界问好。

什么是Jekyll
除了简单的HTML页面，GitHub Pages还提供了一个简单的博客形态的静态网站生成器——Jekyll。Jekyll有一个相对确定的模板，利用渲染器Liquid来生成最终的静态网站。它能够识别Markdown语句，Liquid标签以及原始的HTML和CSS。
由于GitHub Pages默认支持Jekyll框架，因此我们就可以轻松地将Jekyll生成的代码直接上传到GitHub上来搭建我们的博客网站，而且是完全免费的。
请访问Jekyll docs，它将详细地告诉你如何搭建和运行你的网站，创建以及管理内容，定制网站的展示和外观，以及在不同的平台上部署你的网站。
如果你不得不承认英文阅读对于你来说是一件巨大的难事，这里还有Jekyllcn中文站来将你解脱苦海。

环境搭建
想要使用Jekyll，你就必须在本地安装Jekyll。
Jekyll是用Ruby语言开发的，所以最简单的安装方式就是使用RubyGems（RubyGems简称gems，是一个用于对Ruby组件进行打包的Ruby打包系统）。
如果你的电脑中已经安装了最新版本的RubyGems，在终端中运行如下命令就可以安装了：
$ gem install jekyll

由于大部分网页模板中都需要安装其他的插件，Bundler就显得很有必要了。它将帮助你打包管理这些插件。因此安装命令变为：
$ gem install jekyll bundler

如果你的电脑里缺少Ruby和RubyGems，请参考Download Ruby和Download RubyGems来获取相应帮助。
需要指出的是，官方不推荐在MS Windows操作系统上安装。除此以外，Mac用户还需要安装Xcode和Command-Line Tools。
Jekyll docs: Installation。
创建站点
有了Jekyll，只需要短短的几行指令就可以得到一个简洁的博客页面：
~ $ gem install jekyll bundler
~ $ jekyll new personal-blog
~ $ cd my-awesome-site
~/my-awesome-site $ bundle exec jekyll serve

然后打开浏览器访问http://localhost:4000，

发布文章
Jeklly 的一个最好的特点是让作者关注blog本身。这是指什么呢？简单的说就是写博客的过程被融入了Jekyll的功能中。你只需简单的管理你电脑中的一个文件夹下的文本文件就可以写文章并方便的在线上发布。
一个基本的 Jekyll 网站的目录结构一般是像这样的：
.
├── _config.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.textile
|   └── 2009-04-26-barcamp-boston-4-roundup.textile
├── _site
├── .jekyll-metadata
└── index.html

Jekyll docs: Directory structure。
其中，_posts目录里放的就是你的文章了。文件格式很重要，必须要符合: YEAR-MONTH-DAY-title.MARKUP。永久链接可以在文章中自己定制，但是数据和标记语言都是根据文件名来确定的。
只需要将新的文章放在目录_posts下，并将文件名改为YYYY-MM-DD-name-of-post.md。你可参考本文的源文件来撰写你自己的博文。将头信息中的内容更改为你需要的，并在之后附上你自己的内容即可。
Jekyll docs: Front Matter以及Jekyll docs: Writing posts。
网站部署
当你的网站在本地编译测试之后，就可以将其部署在GitHub Pages正式上线了！
如果你已经是GitHub的用户了，接下来你将轻车熟路。你只需要按照格式创建一个新的仓库：ghname.github.io，其中ghname指代你的GitHub账号名称。然后，将你本地的网站上传到这个仓库中就可以通过连接https://ghname.github.io 来访问你的网站了。
如果你的电脑已经安装并配置了git，那么就可以在终端中直接上传了。
$ git init
$ git clone http://github.com/ghname/ghname.github.io.git

$ git pull origin master

$ git add --all
$ git commit -m "leave a message"
$ git push origin master
更详细的部署说明请移步Jekyll docs: GitHub Pages。