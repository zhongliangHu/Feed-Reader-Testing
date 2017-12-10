
## Feed-Reader-Testing项目

### 项目简介
  

### 使用指南
1. 下载该项目所有文件，双击`index.html`,即能显示Jasmine测试的各项结果。
2. **"RSS Feeds"** 第一项测试,其中 **"are linked"** 测试利用正则表达来检测allFeeds对象所有源有链接且有效,因此用`forEach()`对allFeeds数组遍历,`toBeDefined()`查看是否都有链接,`toMatch()`查看链接是否符合有效。
3. **"RSS Feeds"** 测试中 **"have names"** 同样利用forEach()allFeedss数组遍历检测,`toBeDefined()`查看是否都有`name`,用`toBeDefined()`检测`name`是否为空。
4. **"The menu"** 测试单元,**"feed-list is hidden by default"** 利用`toContain()`对body对象的className是否包含`"menu-hidden"`字符来检测菜单默认是否是隐藏的。
5. **"The menu"** 测试单元,**"feed-list could switch to be hidden or be shown"** 先运行`click()`操作，然后同样利用`toContain()`对`body`对象的`className`是否包含`"menu-hidden"`字符来检测菜单是否是隐藏或者可见的。
6. **"Initial Entries"** 测试单元,**"loadFeed is called normally"** 先在`beforeEach()`中运行`loadFeed()`,然后查看`entries.length`是否大于1。
6. **"New Feed Selection"** 测试单元,**"loadFeed has loaded again"** 先在`beforeEach()`中对`"newloadFeed"`进行监测`Spy`,同时安装jasmine的`clock()`,在`afterEach()`中卸载，利用`setTimeout`在`loadFeed(0)`运行后6s后，再运行`newloadFeed()`运行`loadFeed()`,运用jasmine的`toHaveBeenCalled()`来检测一开始没有运行`newloadFeed()`,6s后运行了`newloadFeed()`加载了新源。
----

### 项目使用资源链接
* [Jasmine的各类测试方法的文档](https://jasmine.github.io/2.3/introduction.html)

* [Google Feed API developer's Guide](http://developer.google.com/feed/v1/devguide)
