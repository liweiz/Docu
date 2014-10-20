#Goal
A platform to provide infrastructure, service and operation for social media and social network start-ups.

#Client and User
##Business User
**Social Network Application Owner (SNAO)**: The owners or founders of SNA. The platform is to facilitate many aspects of SNA, including creation, development, operation, maintenance and monitoring. It supports many common SNA functions and features out-of-box and offers APIs for SNAO to extend for application specific features.

It offers a easy-to-start environment for new SNA. It significant reduces the time-to-market and the cost of building a new application.

It also offers hosting and takes the burden of operation and maintenance away from SNAOs, so that SNAOs can focus on developing business. 

##End User
**End User (EU)**: Users who uses SNA applications hosted in the platform.

#Model and Services
##User
Each EU is stored as a node. Each node has a set of system attributes, such as account, name, nick name, avatar, email, birth date and location. System attributes are the same across all sites.

Each SO can define extra site attributes for EU who joins the site. Examples of site attributes are userScore, joinedOn (date/time), profile and settings, where profile and settings can be a complex type defined by SO.

SO may specify indexes on certain attributes, so that SO can search on those attributes. E.g., SO may search for top 10 users of highest score or people joined on a certain date for promotion.

Each EU node links to other EU nodes as edges. Edges can have different types, such as friend and follow.

##Docu
*(TODO: suggestions for a better name?)*
The content posted by EU is called Docu. For example, a post describing a product in Wanelo, a post / comment / reply in StackOverflow, etc. 

Each Docu is also stored as a node. Each node has a set of system attributes, such as title, content, poster, postedOn (time).

Each SO can define extra site attributes for Docu in her own site. Example of site attributes are type, votes, status, tags, picture, category, price. Site attributes can be complex type defined by SO as schema. Certain attributes can be indexed to facilitate search.

Docu nodes form a tree relationship. (I hope tree is sufficient) E.g., comments on Docu, answers on questions, and comments on answers.

Docu nodes can have edges to EU nodes. E.g., a Docu saved by an EU, a Docu liked by an EU, etc.

###Life Cycle Events
Life cycle events of a Docu are defined and offered by system:
**Created, Posted, Updated, Closed, Deleted**

##Action
SNAO can define actions for life cycle events.
Actions are defined and offered by system:
**Notify User**: sending notification to user’s mobile app, or emailing user. Email can be configured as aggregation or summary.
**Feed User**: Showing on user’s landing page.
**Message User**: Showing in user’s inbox.

##Others
Social integration similar to Ning 
Member sign-in via Facebook, Twitter, LinkedIn, Google & more
Seamless sharing to social media sites
Smart Phone 和 Tablet app

APIs for SNAO.


#Case Study - Wanelo
https://wanelo.com/
http://en.wikipedia.org/wiki/Wanelo

##Feature List
EU can post a product. EU posts product url, application parses images and price for EU to select and confirm.
EU can post a story. EU types in a story, with or without products.
EU can purchase products following the product URL. The purchase happens completely out of Wanelo.
EU can save a product to self-defined collections. 
EU can view the poster of a product.
EU can view the people who saved a product.
EU can follow other users so that posts from followed users are fed into "*My Feed*" section.

EU can see *My Feed*.
EU can see recommendations (*Magic*) based saved products.
EU can see *Trending* categorized for *Women*, *Men*, *Home*, and/or price ($, $$, $$$)

##Analysis
Imagine Wanelo will be built after the Docu platform is ready. Most features will be out-of-box in platform. Some specific application related features are still required to be implemented, but that can be done either by the SNAO herself or a hired part-time developer. Also, the platform may offer consultants for such customized development.



#Case Study - Stylists411
http://www.stylists411.com/
（注：不是很肯定这是不是我原来看到的网站）
一个提供发型师和他们客户互动的网站。

发型师发布自己的信息。
客户们可以找自己喜欢的。

## AirBnB
发布的是短租房的信息价格。
提供查询和站内短信互动，最终交易。

##其它案例
我曾构想的找nany和小孩接送服务的网站。
Matt的程序。

#机会分析
以上的系统，很大一部分是相似的。把相同的部分，用metadata driven的方式做好，即使不能成为一个hosting platform，也可以为我们以后的项目打好基础。

#系统设计草案

技术的选择只是很早前的倾向。所有的都可能根据具体的需求变化。

数据存储
数据存储倾向于用Graph database。因为用户关系和Docu的关系都是图。具体的Docu可能用Document database。

可能的选择：Titan DB + Mango DB
check out http://www.orientechnologies.com/orientdb/ for Graph database

服务器端
Open。比较倾向于reactive programming的framework。

Messaging
Kafka。

前端
AngularJS。商业用户可以为自己的Docu设计layout，也可以设计自己的Module。