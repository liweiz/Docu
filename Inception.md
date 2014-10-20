#Goal
A platform to provide infrastructure, service and operation for social media and social network start-ups.

#客户对象
##商业用户 (Site Owner: SO)

为小型社交网站的公司通过hosting。 为社交网站创建初期提供prototype和试运行。

##终端用户 (End User: EU)

使用社交网站的个人用户。

#服务内容
##管理个人用户关系

Each EU is stored as a node. Each node has a set of system attributes, such as account, name, nick name, avatar, email, birth date and location. System attributes are the same across all sites.

Each SO can define extra site attributes for EU who joins the site. Examples of site attributes are userScore, joinedOn (date/time), profile and settings, where profile and settings can be a complex type defined by SO.

SO may specify indexes on certain attributes, so that SO can search on those attributes. E.g., SO may search for top 10 users of highest score or people joined on a certain date for promotion.

Each EU node links to other EU nodes as edges. Edges can have different types, such as friend and follow.

##管理个人用户发布内容。个人用户发布的一个内容暂称为Docu。(Docu 类似于Matt说的物， 比如Wanelo的商品就是一个带链接和产品介绍的post）

Each Docu is also stored as a node. Each node has a set of system attributes, such as title, content, poster, postedOn (time).

Each SO can define extra site attributes for Docu in her own site. Example of site attributes are type, votes, status, tags, picture, category, price. Site attributes can be complex type defined by SO as schema. Certain attributes can be indexed to facilitate search.

Docu nodes form a tree relationship. (I hope tree is sufficient) E.g., comments on Docu, answers on questions, and comments on answers.

Docu nodes can have edges to EU nodes. E.g., a Docu saved by an EU, a Docu liked by an EU, etc.

商业用户可以定义Docu life cycle triggered event 的对应的action。
Lifecycle events are defined and offered by system:

**Created, Posted, Updated, Closed, Deleted**

Actions are defined and offered by system:

**Notify User**: sending notification to user’s mobile app, or emailing user. Email can be configured as aggregation or summary.

**Feed User**: Showing on user’s landing page.

**Message User**: Showing in user’s inbox.

##Others

类似Ning的 Social integration Member sign-in via Facebook, Twitter, LinkedIn, Google & more Seamless sharing to social media sites Smart Phone 和 Tablet app

为商业用户提供扩展的API。

#案例分析

##Wanelo

Wanelo的创立者没有编程background，几经波折才建立起一个团队。 https://wanelo.com/

终端用户发布产品信息，类别，照片和价格。 终端用户可以follow其他用户。 终端用户可以购买产品。

##Stylists411

http://www.stylists411.com/ （注：不是很肯定这是不是我原来看到的网站） 一个提供发型师和他们客户互动的网站。

发型师发布自己的信息。 客户们可以找自己喜欢的。

##AirBnB

发布的是短租房的信息价格。 提供查询和站内短信互动，最终交易。

##其它案例

我曾构想的找nany和小孩接送服务的网站。 Matt的程序。

#机会分析
以上的系统，很大一部分是相似的。把相同的部分，用metadata driven的方式做好，即使不能成为一个hosting platform，也可以为我们以后的项目打好基础。

#系统设计草案
技术的选择只是很早前的倾向。所有的都可能根据具体的需求变化。

数据存储 数据存储倾向于用Graph database。因为用户关系和Docu的关系都是图。具体的Docu可能用Document database。

可能的选择：Titan DB + Mango DB check out http://www.orientechnologies.com/orientdb/ for Graph database

服务器端 Open。比较倾向于reactive programming的framework。

Messaging Kafka。

前端 AngularJS。商业用户可以为自己的Docu设计layout，也可以设计自己的Module。
