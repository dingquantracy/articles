## Progeressive Web App入门指南

    本文翻译来自https://www.smashingmagazine.com/2016/08/a-beginners-guide-to-progressive-web-apps/。 有兴趣的同学可以点击[阅读原文](https://www.smashingmagazine.com/2016/08/a-beginners-guide-to-progressive-web-apps/)

Progressive web app(PWA)的出现对于移动web开发来说是一件大事。自从Google在2015年推出以来，由于相对简单的开发过程以及在应用的用户体验方面的优势，PWA已经吸引了很多的关注。

PWA使用最新的技术，结合了web和移动应用的各自优势。其实可以想象成使用web技术开发的一个站点但是使用起来却又像个原生的应用。得益于浏览器自身的新特性，service worker提供的功能以及Cache和Push API，开发者可以为PWA应用带来一些强大的功能，比如在主屏幕上安装web应用，接收推送的消息，甚至可以离线运行。

相比于应用市场上的原生app，开发和维护一个web站点会来的更加简单，同时还能拥有更加庞大的web生态系统，各种成熟的插件以及活跃的开发社区的支持。如果你有移动应用和web的开发经验，你就会了解构建一个站点所需要花费的时间更少，同时不用考虑API的向下兼容(所有用户运行的都是相同版本的网站代码，而不像原生应用一样有不同的版本)，而且通常来说这样的web应用更容易发布和维护。

### 为什么要选择Progeressive Web App

有项研究表明，平均来说，在用户从接触一个app到开始使用这个app之前的每一个步骤都会使该app损失20%的用户。用户首先必须从应用市场找到这个app，然后下载，安装，最后打开。然而，当用户找到你开发的PWA应用时，他可以立即开始使用，省去了不必要的下载和安装的过程。当用户返回到应用的时候，会提示他安装该应用，并且可以使用全屏操作来提升体验。

当然，原生应用并不是一无是处。拥有消息推送功能的移动应用比没有推送功能的拥有高达三倍的留存率，也就是说相比于一个站点，用户有三倍的可能性会去重新打开一个移动应用。除此之外，精心设计的移动应用会将一些资源常驻设备，使其使用更少的数据，运行更流畅。

一个PWA应用就利用了移动应用这些好的特性，提升了用户的留存率和应用的性能，同时又不会引入维护一个移动应用的复杂性。

#### 案例

什么时候你需要开发一个PWA应用呢？通常开发原生app是希望用户能够频繁回到app中，其实PWA应用也可以实现同样的效果。[Flipkart](http://www.flipkart.com/)下著名的电子商务平台Flipkart Lite就是一个PWA应用，同样的还有[Air Berlin](https://flights.airberlin.com/en-DE/progressive-web-app)开发的PWA应用，用来作为在线登记流程，允许用户在没有网络的情况下也能查看他们的机票。

当决定下一个应用应该是PWA，web站点或者原生应用时，你首先应该了解并确定对用户来说最重要的操作是什么。要做到“progressive”，一个PWA应用要能保证在所有浏览器中运行，同时当用户的浏览器升级引入新的特性和API的时候，用户体验也能得到提升。

因此，与传统的web站点相比，PWA应用没有在用户体验上作出妥协，但是，你可能要决定哪些功能需要离线支持，你需要提供更方便的导航(记住在独立模式下，用户是无权操作后退按钮的)。如果你的站点已经拥有了原生应用类似的界面，使用progressive web app的理念会使它更加完美。

如果某些功能点对于重要的用户操作是不可或缺的，但是目前又缺少跨浏览器支持的话，开发一个原生的移动应用或许是个更好的选择，这样能保证对于所有用户来说都有相同的用户体验。

### Progeressive Web App的特点

在我们接触具体的代码之前，我们需要了解一下PWA应用拥有的以下这些特点：

**渐进加强(Progressive)**

定义里已经阐述了，一个PWA应用必须保证能在所有的设备上运行，同时根据用户设备和浏览器的特性实现功能的渐进增强。

**可搜索性(Discoverable)**

因为PWA应用本质上是一个web站点，所以可以被搜索引擎搜索到。原生应用在可搜索性上是落后web站点的，这是PWA应用的一个很大的优势。

**可链接化(Linkable)**

这是继承自web站点的另一个特点，设计良好的站点应该使用URI来表示应用当前的状态。当用户将当前web应用保存为书签或者着分享这个URL的时候，该应用可以保持或者重载当前的状态。

**响应式(Responsive)**

PWA应用必须能够适配不同的设备和屏幕尺寸。

**类原生应用(App-like)**

PWA应用应该拥有和原生app类似的界面和体验，同时基于application shell model构建，尽可能减少页面的刷新。

**不依赖网络(Connectivity-independent)**

能够在较差的网络连接或者完全离线状态下运行(最受欢迎的特性)。

**多次使用(Re-engageable)**

原生应用的用户可愿意多次使用他们的app，PWA应用通过使用消息推送等功能也可以达到相同的目的。

**可安装(Installable)**

PWA应用可以安装在设备的主屏上，使其可以随时被使用。

**持续更新(Fresh)**

当新内容发布并且用户处于网络连接状态，app能够实时获取这些内容。

**安全性(Safe)**

因为PWA应用提供了更加亲密的用户体验，并且所有的网络强求都可以被service worker拦截，因此应用必须通过HTTPS访问来防止网络层攻击。

### 开始写代码吧

我们的第一个PWA应用，Sky High，将会模拟机场的到达时间表。用户首次打开app，我们会从接口获取并展示即将到达的航班信息。如果用户在无网络连接的情况下重新加载了我们的web应用，我们希望能展示上一次有网络连接时加载的航班到达时间表。

![](./images/1.png)

#### 基础

PWA应用的第一个特点就是它必须保证在所有的设备和浏览器上能够运行，同时在条件允许的情况下进行功能增强。因此，我们使用传统的HTML5和Javascript来构建界面，同时通过从一个模拟的接口获取数据来展示航班到达信息。在我们的应用中，我们使用了轻量级的Javascript框架Knockout，来处理Model-View-ViewModel (MVVM)绑定操作，将我们的Javascript模型和HTML视图进行绑定。我们之所以使用Knockout是因为它相对容易理解，而且不会使代码变得混乱；当然，你也可以选择其他的框架，比如React或者AngularJS。

我们的站点遵循Google提出的[material design](https://material.io/guidelines/)，这是一套用来规范设计和交互的准则和指南。material design不仅可以用来作为不同应用和设备统一的视觉交互规范，同时也为设计赋予了含义。我们在Sky High的航班到达界面就使用了material design，使我们的应用看起来和使用起来更接近原生应用的体验。

最后，我们对app进行测试，确保它有较好的性能，不会出现丢帧现象，滚动也非常流畅顺滑。无丢帧渲染已经被证明会提高用户对app的使用率。我们的目标就是保证每秒渲染60帧。

在这个示例中，我们只是从静态的JSON文件获取数据，并没有使用真正的接口。这仅仅是为了简化我们的示例app。在真实的使用场景，你需要通过请求接口或者WebSockets来获取数据。

`index.html`

    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Sky-High Airport Arrivals</title>
        <link async rel="stylesheet" href="./css/style.css">
        <link href="https://fonts.googleapis.com/css?family=Roboto:300,600,300italic,600italic" rel="stylesheet" type="text/css">
    </head>

    <body>
        <header>
            <div class="content">
                <h3>Arrivals</h3>
            </div>
        </header>
        <div class="container">
            <div id="main" class="content">
                <ul class="arrivals-list" data-bind="foreach: arrivals">
                    <li class="item">
                        <span class="title" data-bind="html: title"></span>
                        <span class="status" data-bind="html: status"></span>
                        <span class="time" data-bind="html: time"></span>
                    </li>
                </ul>
            </div>
        </div>
        <script src="./js/build/vendor.min.js"></script>
        <script src="./js/build/script.min.js"></script>
    </body>

    </html>


index.html是标准的html文件。我们创建了一个列表，并且使用Knockout框架，通过添加`data-bind="foreach: arrivals"`属性，将视图模型arrivals绑定到该列表上。视图模型arrivals在page.js文件中进行声明，并且暴露到了Page模块下，具体代码如下。在HTML文件中，对于arrivals数组中的每一项，我们都将title，status和time属性绑定到了HTML视图上。

`page.js`

    (var Page = (function() {

        // declare the view model used within the page
        function ViewModel() {
            var self = this;
            self.arrivals = ko.observableArray([]);
        }

        // expose the view model through the Page module
        return {
            vm: new ViewModel(),
            hideOfflineWarning: function() {
                // enable the live data
                document.querySelector(".arrivals-list").classList.remove('loading')
                // remove the offline message
                document.getElementById("offline").remove();
                // load the live data
            },
            showOfflineWarning: function() {
                // disable the live data
                document.querySelector(".arrivals-list").classList.add('loading')
                    // load html template informing the user they are offline
                var request = new XMLHttpRequest();
                request.open('GET', './offline.html', true);

                request.onload = function() {
                    if (request.status === 200) {
                        // success
                        // create offline element with HTML loaded from offline.html template
                        var offlineMessageElement = document.createElement("div");
                        offlineMessageElement.setAttribute("id", "offline");
                        offlineMessageElement.innerHTML = request.responseText;
                        document.getElementById("main").appendChild(offlineMessageElement);
                    } else {
                        // error retrieving file
                        console.warn('Error retrieving offline.html');
                    }
                };

                request.onerror = function() {
                    // network errors
                    console.error('Connection error');
                };

                request.send();
            }
        }

    })();


page.js对外暴露了我Page模块，包含了我们定义的视图模型`vm`以及两个函数`hideOfflineWarning`和`showOfflineWarning`。`ViewModel`是Javascript中的简单构造函数，用来创建视图模型对象实例。实例属性`arrivals`是Knockout中的`observableArray`，能自动将我们的HTML视图和Javascript中的数组进行绑定，当我们对数组进行push或者pop操作，页面的HTML视图会自动更新。

调用`hideOfflineWarning`和`showOfflineWarning`两个方法可以更新我们应用的界面，向用户展示当前app是否处于网络连接状态。`showOfflineWarning`方法会为`arrivals-list`节点添加名为`loading`的class，隐藏列表的同时会异步获取offline.html文件。如果文件获取成功(response.status === 200)，我们将文件内容添加到页面。当然，如果我们没有使用service worker并且应用当前处于离线状态，就无法获取offline.html的内容了，这时用户就只能看到浏览器的无法连接网络页面。

具体的业务逻辑代码，包括如何从接口获取数据并将其绑定到视图模型和试图，都可以在arrival.js文件中找到，我们只是使用了Knockout框架提供的标准MVVM的相关功能。在arrival.js文件中，我们简单地初始化应用需要使用的服务和视图模型，并对外暴露函数`Arrivals.loadData()`，用来获取数据并绑定视图模型。

#### 创建web应用的Manifest文件
 
 In addition, Chrome on Android will proactively suggest that the user install the web app, via a web app install banner. To display the installation prompt, your web app needs to:

have a valid web app manifest file,
be served over HTTPS,
have a valid service worker registered,
have been visited twice, with at least five minutes between each visit.


让我们的web应用更像原生应用吧。web应用的manifest文件事遵循[W3C]规范的简单JSON文件。添加该文件后，web应用可以像单独的应用一样在全屏模式下运行；当应用安装之后可以为其设置一个应用图标；也可以为应用设置主题和背景色。除此之外，安卓上的Chrome浏览器还会通过banner提示，主动建议用户安装当前的web应用。如果想出现这样的安装提示，你的web应用需要：

-   添加正确的manifest文件
-   必须通过HTTPS访问
-   注册了正确的service worker
-   五分钟之内至少有两次被访问

![](./images/2.png)

`manifest.json`

    {
        "short_name": "Arrivals",
        "name": "Arrivals at Sky High",
        "description": "Progressive web application demonstration",
        "icons": [
            {
                "src": "launcher-icon.png",
                "sizes": "48x48",
                "type": "image/png"
            },
            {
                "src": "launcher-icon-96.png",
                "sizes": "96x96",
                "type": "image/png"
            },
            {
                "src": "launcher-icon-144.png",
                "sizes": "144x144",
                "type": "image/png"
            },
            {
                "src": "launcher-icon-192.png",
                "sizes": "192x192",
                "type": "image/png"
            },
            {
                "src": "launcher-icon-256.png",
                "sizes": "256x256",
                "type": "image/png"
            }
        ],
        "start_url": "./?utm_source=web_app_manifest",
        "display": "standalone",
        "orientation": "portrait",
        "theme_color": "#29BDBB",
        "background_color": "#29BDBB"
    }

让我们来分析下这个manifest文件：

-   `short_name`是一个用户可读应用名称。通过安卓手机的Chrome安装到主屏的应用会展示成该名称。

-   `name`同样是一个用户可读应用名称。该名称用在安装对话框中，Extension的管理界面。

-   `description`简单描述了该web应用。

-   `icons`定义了一组不同尺寸的图片作为应用的图标集。在安卓手机使用Chrome时，图标在启动屏，主屏和任务管理器中使用。

-   `start_url`是应用的启动URL

-   `display`定义了web应用默认的运行模式：`fullscreen`，`standalone`，`minimal-ui`或者`browser`。

-   `orientation`定义了web应用默认展示的方向：`portrait`或者`landscape`。

-   `theme_color`是应用默认的主题色。安卓上的状态栏会被设置成该颜色。

-   `background_color`定义了web应用的背景色。同时也定义了应用启动屏的背景色。

-   `related_applications`在我们的例子中并没有设置，该属性用来描述在应用市场可选的相关原生应用。

在index.html文件的head标签中添加manifest.json文件的引用：

    <link rel="manifest" href="./manifest.json">

当用户将web应用安装到主屏之后，用户就可以直接进入应用，而不需要先打开浏览器了。你会发现这比书签的作用更加强大。

#### Service Workers

PWA应用更加让人兴奋的一个特点是可以离线运行。使用service worker，可以展示应用在上一个会话中获取的数据(使用IndexdDB)，或者说表现的更像原生的app，并且可以在用户失去网络连接的时候进行提示(就像我们在示例中看到的一样)。当用户重新连接网络之后，应用可以重新从服务端获取最新的数据。

使用service workers可以实现上面提到的所有功能，service worker本身也是Javascript编写，基于事件驱动的脚本，可以监听当前域下的事件，比如网络请求。我们可以使用service worker来缓存所有的静态资源，这会大大减少网络请求数，提高应用的性能。

#### 应用外壳(Application Shell)

应用外壳是应用的用户界面需要的最基本的HTML、CSS 和 JavaScript，原生应用会将其作为安装包的一部分进行分发，而网站通常使用网络请求来获取。PWA应用会将应用外壳所需的资源文件缓存在浏览器中，从而尽量和原生app保持一致。在我们的应用Sky High中，我们的应用外壳包含了顶部的header，以及需要的字体和样式文件。

使用service worker，我们首先需要在根目录下创建一个Javascript文件sw.js。

`sw.js`

    // Use a cacheName for cache versioning
    var cacheName = 'v1:static';

    // During the installation phase, you'll usually want to cache static assets.
    self.addEventListener('install', function(e) {
        // Once the service worker is installed, go ahead and fetch the resources to make this work offline.
        e.waitUntil(
            caches.open(cacheName).then(function(cache) {
                return cache.addAll([
                    './',
                    './css/style.css',
                    './js/build/script.min.js',
                    './js/build/vendor.min.js',
                    './css/fonts/roboto.woff',
                    './offline.html'
                ]).then(function() {
                    self.skipWaiting();
                });
            })
        );
    });

    // when the browser fetches a URL…
    self.addEventListener('fetch', function(event) {
        // … either respond with the cached object or go ahead and fetch the actual URL
        event.respondWith(
            caches.match(event.request).then(function(response) {
                if (response) {
                    // retrieve from cache
                    return response;
                }
                // fetch as normal
                return fetch(event.request);
            })
        );
    });

仔细看一下我们创建的service worker。首先我们定义了一个变量`cacheName`。用来决定是否需要改变我们缓存的文件。对于这个例子来说，我们使用固定的名字，表明我们缓存的文件内容不会改变，也不需要更新。

    self.addEventListener('install', function(e) {
        // declare which assets to cache
    }

`install`事件只有在serivce worker第一次安装成功的时候才会触发。所以，刷新页面并不会再次触发该事件。service worker安装后，我们可以声明哪些资源文件需要被缓存。上面的例子中，我们缓存了一个CSS文件，两个Javascript文件，字体文件，离线使用的HTML模板，当然还有应用访问的根路径。`self.skipWaiting()`会强制让waiting状态的service worker变为active。

至此，我们已经创建好了service worker文件，但是如果想要让其真正工作，还需要在Javascript代码中使用它。我们的应用在main.js注册了该service worker。

    // Register the service worker if available.
    if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('./sw.js').then(function(reg) {
            console.log('Successfully registered service worker', reg);
        }).catch(function(err) {
            console.warn('Error whilst registering service worker', err);
        });
    }

    window.addEventListener('online', function(e) {
        // Resync data with server.
        console.log("You are online");
        Page.hideOfflineWarning();
        Arrivals.loadData();
    }, false);

    window.addEventListener('offline', function(e) {
        // Queue up events for server.
        console.log("You are offline");
        Page.showOfflineWarning();
    }, false);

    // Check if the user is connected.
    if (navigator.onLine) {
        Arrivals.loadData();
    } else {
        // Show offline message
        Page.showOfflineWarning();
    }

    // Set Knockout view model bindings.
    ko.applyBindings(Page.vm);

我们同样注册了两个事件监听器来检查当前应用状态是否从在线变成离线，或者是相反的过程。事件处理函数会调用不同的方法，使用`Arrivals.loadData()`来获取数据，同时使用`Page.showOfflineWarning`和`Page.hideOfflineWarning`分别来显示和隐藏离线信息。同时我们的应用还会使用`navigator.onLine`来检查当前用户是否处于网络连接状态，从而确定是否需要展示离线警告信息。在main.js的最后一行，我们使用Knockout绑定视图模型`Page.vm`。

第一次加载我们的应用(打开Chrome Developer Tools)，一切都没有什么不同。然后，刷新重载的时候，我们会看到有一些网络资源是从service worker中获取到的。这就是我们的应用外壳。

![](./images/3.png)

#### 离线测试

如果用户在没有网络连接的情况下运行该应用(假设此时应用已经打开了)，就只能看到我们的应用外壳和离线警告，这和Chrome本身的离线警告页面相比，有了明显的体验提升。只要用户一连接上网络，我们会隐藏警告信息并且获取并展示最新的数据。

![](./images/4.png)

#### 推送消息

推送消息允许用户可以选择是否要及时更新信任的应用，帮主他们再次使用应用，与其互动。在web应用推送消息，即使浏览器关闭，依然可以让用户感知到。

![](./images/5.png)

Push API在Chrome，Opera和三星手机的浏览器上均已被支持，Firefox和微软Edge浏览器也会陆续支持。不幸的是，没有迹象表明Safari会支持该API的功能。

#### 性能

使用service worker的最明显的好处就是，我们几乎只做了很小的改动就能大大提升应用的性能。站点没有使用service worker，页面加载的时候需要获取超过200KB的资源文件，现在减少到了13KB。在普通的3G网络情况下，页面的加载时间从3.5秒减少到了500毫秒。

这些性能的提升是非常明显的，因为我们的应用本身很小，功能很简单。然而，通过正确使用缓存，可以显著地提升应用的性能和用户体验，特别是对于网络状况不太好的用户。

#### Lighthouse

Google的Chrome团队推出了一个工具来测试PWA应用。[Lighthose](https://github.com/GoogleChrome/lighthouse)可以在Node.js环境运行，或者直接食用Chrome提供的插件，你可以在Github上找到该开源项目。

如果想要使用Lighthoust进行测试，你的站点必须是线上可访问的，意味着你无法在本地通过localhost进行测试。

开始测试之前，你需要先下载相应的npm模块：

    npm install -g GoogleChrome/lighthouse

安装好之后，运行Chrome(版本号至少为52)：

    npm explore -g lighthouse -- npm run chrome
    lighthouse https://incredibleweb.github.io/pwa-tutorial/

L运行的结果会展示在命令行，Lighthouse会根据PWA的功能点以及你的实现情况进行打分，比如你是否添加了manifest.json文件或者你的页面是否可以离线访问。

### 总结

改文章仅仅是对于progressive web app的入门指导。不管是使用Push API支持消息推送，使用户更好地和应用互动，或者使用IndexedDB和后台同步来提升应用的离线体验，我们还可以做更多的工作来打造用户喜欢的真正和原生app体验一致的应用。

#### 浏览器支持情况

Progressive web app的发展才刚刚起步，浏览器的支持情况也不是很乐观，特别是在Safari和Edge中。然后，微软已经公开表示会在将来完全支持Progressive web app。


-   `Service worker和Cache API`

Chrome，Firefox，Opera和三星手机浏览器均已支持。微软Edge也会陆续支持，目前还在开发中。Safari还在考虑是否要支持。

-   `Add to home screen`

Chrome，Firefox，Opera和三星手机浏览器均已支持。微软暗示PWA应用将会出现在应用商店中。Safari目前没有计划支持。

-   `Push API`

Chrome，Firefox，Opera和三星手机浏览器均已支持绝大多数API。微软Edge也会陆续支持。Safari目前没有计划支持。

如果有更多的开发者使用progressive web app提供的各种新特性，这些特性相对来说比较容易实现而且能带来显著的效果，就会有更多的用户会选择使用支持的浏览器去访问这些web应用，希望这样会让其他浏览器厂商都来支持progressive web app。

如果

#### 源码

本文提到示例的完整源代码可以在[Github](https://github.com/IncredibleWeb/pwa-tutorial)上找到，也可以前往[GitHub Page](https://incredibleweb.github.io/pwa-tutorial/)查看demo效果。