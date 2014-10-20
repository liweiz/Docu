#Goal
A platform to provide infrastructure, service and operation for social media and social network start-ups.

#�ͻ�����
##��ҵ�û� (Site Owner: SO)
ΪС���罻��վ�Ĺ�˾ͨ��hosting��
Ϊ�罻��վ���������ṩprototype�������С�

##�ն��û� (End User: EU)
ʹ���罻��վ�ĸ����û���

#��������
##��������û���ϵ
Each EU is stored as a node. Each node has a set of system attributes, such as account, name, nick name, avatar, email, birth date and location. System attributes are the same across all sites.

Each SO can define extra site attributes for EU who joins the site. Examples of site attributes are userScore, joinedOn (date/time), profile and settings, where profile and settings can be a complex type defined by SO.

SO may specify indexes on certain attributes, so that SO can search on those attributes. E.g., SO may search for top 10 users of highest score or people joined on a certain date for promotion.

Each EU node links to other EU nodes as edges. Edges can have different types, such as friend and follow.

##��������û��������ݡ������û�������һ�������ݳ�ΪDocu��(Docu ������Matt˵��� ����Wanelo����Ʒ����һ�������ӺͲ�Ʒ���ܵ�post��
Each Docu is also stored as a node. Each node has a set of system attributes, such as title, content, poster, postedOn (time).

Each SO can define extra site attributes for Docu in her own site. Example of site attributes are type, votes, status, tags, picture, category, price. Site attributes can be complex type defined by SO as schema. Certain attributes can be indexed to facilitate search.

Docu nodes form a tree relationship. (I hope tree is sufficient) E.g., comments on Docu, answers on questions, and comments on answers.

Docu nodes can have edges to EU nodes. E.g., a Docu saved by an EU, a Docu liked by an EU, etc.

��ҵ�û����Զ���Docu life cycle triggered event �Ķ�Ӧ��action��
Lifecycle events are defined and offered by system:
**Created, Posted, Updated, Closed, Deleted**

Actions are defined and offered by system:
**Notify User**: sending notification to user��s mobile app, or emailing user. Email can be configured as aggregation or summary.
**Feed User**: Showing on user��s landing page.
**Message User**: Showing in user��s inbox.

##Others
����Ning�� Social integration
Member sign-in via Facebook, Twitter, LinkedIn, Google & more
Seamless sharing to social media sites
Smart Phone �� Tablet app

Ϊ��ҵ�û��ṩ��չ��API��


#��������

##Wanelo
Wanelo�Ĵ�����û�б��background���������۲Ž�����һ���Ŷӡ�
https://wanelo.com/

�ն��û�������Ʒ��Ϣ�������Ƭ�ͼ۸�
�ն��û�����follow�����û���
�ն��û����Թ����Ʒ��


##Stylists411
http://www.stylists411.com/
��ע�����Ǻܿ϶����ǲ�����ԭ����������վ��
һ���ṩ����ʦ�����ǿͻ���������վ��

����ʦ�����Լ�����Ϣ��
�ͻ��ǿ������Լ�ϲ���ġ�

## AirBnB
�������Ƕ��ⷿ����Ϣ�۸�
�ṩ��ѯ��վ�ڶ��Ż��������ս��ס�

##��������
�����������nany��С�����ͷ������վ��
Matt�ĳ���

#�������
���ϵ�ϵͳ���ܴ�һ���������Ƶġ�����ͬ�Ĳ��֣���metadata driven�ķ�ʽ���ã���ʹ���ܳ�Ϊһ��hosting platform��Ҳ����Ϊ�����Ժ����Ŀ��û�����

#ϵͳ��Ʋݰ�

������ѡ��ֻ�Ǻ���ǰ���������еĶ����ܸ��ݾ��������仯��

���ݴ洢
���ݴ洢��������Graph database����Ϊ�û���ϵ��Docu�Ĺ�ϵ����ͼ�������Docu������Document database��

���ܵ�ѡ��Titan DB + Mango DB
check out http://www.orientechnologies.com/orientdb/ for Graph database

��������
Open���Ƚ�������reactive programming��framework��

Messaging
Kafka��

ǰ��
AngularJS����ҵ�û�����Ϊ�Լ���Docu���layout��Ҳ��������Լ���Module��
