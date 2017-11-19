
## Feed-Reader-Testing项目

### 使用指南
1. 下载该项目所有文件，双击index.html,即能显示Jasmine测试的各项结果。
2. **"RSS Feeds"** 第一项测试,其中**"are linked"** 测试利用正则表达来检测allFeeds对象所有源有链接且有效,因此用forEach()对allFeedss数组遍历,toBeDefined()查看是否都有链接,toMatch()查看链接是否符合有效。
3. **"RSS Feeds"** 测试中 **"have names"** 同样利用forEach()allFeedss数组遍历检测,toBeDefined()查看是否都有name,用toBeDefined()检测name是否为空。
4. **"The menu"** 测试单元,**"feed-list is hidden by default"** 利用toContain()对body对象的className是否包含"menu-hidden"字符来检测菜单默认是否是隐藏的。
5. **"The menu"** 测试单元,**"feed-list could switch to be hidden or be shown"** 先运行click()操作，然后同样利用toContain()对body对象的className是否包含"menu-hidden"字符来检测菜单是否是隐藏或者可见的。
6. **"Initial Entries"** 测试单元,**"loadFeed is called normally"** 先在beforeEach()中运行loadFeed(),然后查看entries.length是否大于1。
6. **"New Feed Selection"** 测试单元,**"loadFeed has loaded again"** 先在beforeEach()中对"newloadFeed"进行监测Spy,同时安装jasmine的clock(),在afterEach()中卸载，利用setTimeout在loadFeed(0)运行后6s后，再运行newloadFeed()运行loadFeed(),运用jasmine的toHaveBeenCalled()来检测一开始没有运行newloadFeed,6s后运行了newloadFeed()加载了新源。
----

### 项目使用资源链接
* [Jasmine的各类测试方法的文档](https://jasmine.github.io/2.3/introduction.html)

* [Google Feed API developer's Guide](http://developer.google.com/feed/v1/devguide)
