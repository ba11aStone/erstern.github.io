---
layout: post
title:  "使用「Github Pages」和「Jekyll」搭建 Blog 的過程及所遇到的問題"
date:   2014-10-21
categories: jekyll update
---
上篇是應邀對二廣的日誌文章作出評論，這篇敘述一下搭建的過程，安裝時的問題和經驗，既是分享，也是備忘。

本就打算用 Markdown 寫，而企鵝空間不支持，那就要再找個地方寫了再回覆鏈接。

簡單的標記語言文檔，在線編輯可行，但感覺不夠正式且難以長久保存，於是就選了 github pages + Jekyll。這個想法早已有了，兩年前就用 [Octopress](http://octopress.org/) 搭過，當是還是用的獨立域名：`yuanchen.me`。一直疏於管理，加上對 git 的理解不夠、對前端寫得也不好，發了兩篇白底黑字的短文就擱置了。前段時間，維護的重心放在微信公衆平臺上，也發現公衆號的文字編輯框功能不夠強大，二廣同學催評論的時候，就想到重新用 Github Pages 搭一個。

Github Pages 官網的簡介是：`Websites for you and your projects.`長一點的解釋是：`GitHub Pages are public web pages for users, organizations, and repositories, that are freely hosted on GitHub's github.io domain or on a custom domain name of your choice. GitHub Pages are powered by Jekyll behind the scenes, so in addition to supporting regular HTML content, they're also a great way to host your Jekyll-powered website for free.`

用來做網站或個人博客的話，好處是無限流量、免費、不用審核，還能綁定域名；缺點我就不展開了。

看！人家臉上都寫了，Pages，那就相當於給了一張空白卷子，怎麼寫答案就看你自己了。可我的語文是語文老師教的，不是前端工程師教的，默認不帶漢字轉 `<html>漢字</html>` 技能，怎麼辦？是時候召喚 Jekyll 了！

維基百科上解釋 Jekyll 說：`Jekyll is an open source program, written in Ruby by Tom Preston-Werner, GitHub's co-founder. Jekyll is a simple, blog-aware, static site generator for personal, project, or organization sites. It is a file-based CMS; instead of using databases, Jekyll takes the content, renders Markdown or Textile and Liquid templates, and produces a complete, static website ready to be served by Apache HTTP Server, Nginx or another web server. Jekyll is the engine behind GitHub Pages, a GitHub feature that allows users to host websites based on their GitHub repositories.`


原來這就是專門爲 Github Pages 打造的啊！Github Pages 提供了紙，Jekyll 劃好了各種框架，默認還支持 Markdown，我等用戶就只剩下關注文字和內容了。


那就開始安裝吧。


人家也說了，Jekyll 是用 Ruby 寫的，那麼先裝一個 ruby 環境吧，我現在用的平臺是 [openSUSE](http://www.opensuse.org/zh-cn/) 13.1，當初 DVD 安裝，有 ruby。竊喜……


然後是 gem，不管是叫 gem 或是 rubygems 或其他名字，總之安裝 ruby 有關的軟件少不了它。


接下來安裝 bundler 和 jekyll，分別是 `gem install bundler` 和 `gem install jekyll`

但是到這裏十有八九會出錯，除了權限的問題，還會撞牆。解決的辦法就是找牆內鏡像。第一次看見鏡像地址是 `http://ruby.taobao.org/` 的時候我還以爲是作者用網購的鏈接作例子，沒想到吧，這真的是真的，

RubyGems 鏡像哪家好？gem sources -a 輸淘寶！

這裏參數 -a 表示添加，-r 是 delete，-l 是把現有的 list 出來。


親身經歷告誡并備自己忘，一定記得權限！Ruby 的安裝、gem install 和 gem sources 都是要對應的，說多了都是血淚……


我在安裝的時候還遇到一個問題，屬於粗心大意想當然，以爲 gcc 和 make 這等編譯環境都是預先安裝好的；還有 NodeJS 的支持，這些在安裝不成功時會有提示，也容易解決，同時不一定是每個人都會遇到，不多說了。


接下來開始使用。

輸入 `jekyll new blog` 可以生成一個名叫 blog 的文件夾，含有（沒有的話輸入 jekyll serve）默認的 jekyll 模板，推送到 username.github.io 這一項目的主分支即可。注意項目名稱必須是用「在 github 的 username」+「.github.io」的格式，否則無效；當然，也可以自己綁定另外的域名，但項目名稱的格式不能變。

關於 Jekyll 的自定義等，網上有教程，我也在學習中。暫不詳述。
