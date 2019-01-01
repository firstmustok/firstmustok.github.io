---
title:  "Resume"

author: 杨勋华
mail: yangxunhua@qq.com
mobile: 17360262904
qq: 515701734
positions: 高级开发工程师, 架构师

github: firstmustok
blog: https://firstmustok.github.io
note:
 - 有丰富的开发和运维经验
 - 喜欢钻研新技术 善于快速定位解决问题
 - 团队合作意识强 乐于技术分享
 - 能够带领团队进行技术攻关
 - 
 - "Stay foolish, stay hungry."

last_modified_at: 2019-01-01

permalink: resume.html
layout: resume
---

{% assign github = page.github %}

## **{:.section-icon .fa}**基本信息 Basic info**
{:.section}
  - **个人信息:** {{page.author}} / 男 / 1986
  - **毕业院校:** 本科 / 武汉大学 / 计算机科学与技术
  - **工作年限:** 7年
  - **GitHub:** [https://www.github.com/{{github}}](https://www.github.com/{{github}})
{:.basic}

## **{:.section-icon .fa}**技能清单 SKILL**
{:.section}
  - 后端
    - *s*{:.project-circle}编程
      * 5 年`JAVA/web`开发经验，熟悉[`Spring`][Spring], [`SpringBoot`][SpringBoot], [`Hibernate`][Hibernate]等框架。
      * 3 年运维经验，熟悉`Linux`运行环境及常用软件配置维护调优。
      * 3 年`C++`项目经验。 
      * 有[`React Native`][RN]跨平台框架混合开发`APP`经验。
      * [`Golang`][Golang], 喜欢`Golang`高效与编译速度，用`go`语言开发过一些工具。
      * 喜欢脚本[`Python`][Python]/[`Ruby`][Ruby]/[`NodeJS`][Ruby],能使用脚本语言解决实际问题。
      * 熟练使用[`SVN`][SVN]/[`Git`][Git]、[`Ant`][Ant]/[`Maven`][Maven]/[`Gradle`][Gradle]协作开发，能熟练使用设计模式解决项目中问题。

    - *s*{:.project-circle}网络、数据库及性能调优
      * 熟练使用`jstat`, `jmap`, `jstack`等进行系统性能分析及调优。
      * 熟悉`TCP`, `HTTP`等协议, 掌握运用工具`tcpdump`/[`wireshark`][wireshark]进行问题定位。
      * 熟悉[`Apache`][Apache]，[`Tomcat`][Tomcat]/`WebLogic`等软件， 以及搭建[`ELK`][ELK]日志监控方案。
      * 熟悉`SQL`/`NoSQL`，并能熟练使用`Oracle`/`MySQL`/`PostgreSQL`, `Redis`/`MongoDB`。
    {:.project}
  {:.campany}
  - 前端
    - *s*{:.project-circle}
      * 熟悉常用Web技术, `HTML`/`Javascript`/`CSS`/`AJAX`等。
      * 熟悉常用前端库 [`jQuery`][jQuery], [`Ractive`][Ractive], [`Requirejs`][Requirejs]等。
      * 熟悉前端框架库[`React`][React]/[`Angular`][Angular]等技术。
      * 熟练前端常用工具使用, 如[`webpack`][Webpack]/[`gulp`][gulp]。
    {:.project}
  - DevOps
    - *s*{:.project-circle}
      * 熟悉[`Docker`][Docker]环境搭建与使用,了解主流的容器编排[`Kubernetes`][Kubernetes], [`Swarm`][Swarm]技术。
      * 熟悉`Linux`基本命令与`shell`脚本编写，如能熟练使用`awk`及`sed`进行文本处理。
      * 熟悉[`Jenkins`][Jenkins], [`Bamboo`][Bamboo]等持续集成软件使用配置, 能够根据需求快速搭建一套`DevOps`环境。
      * 熟练搭建[`Nagios`][Nagios]环境对线上系统性能及异常监控。
    {:.project}
  {:.campany}

## **{:.section-icon .fa}**项目与工作经验 Experience**
{:.section}
- **京东成都研究院 [2018.04 - 至今]**{:.campany-name}
  - *s*{:.project-circle} **启明星项目**{:.project-title} **(JAVA工程师)**
    * 主要负责后台一，二, 四期后台`API`开发, 期间指导实习生完成三期需求开发。
    * 本项目主要是针对大快消事业群下6大事业部(市场营销部、消费品事业部、全球购业务部、生鲜事业部、美妆业务部)，有针对性的,不同类型的可视化报表，方便其了解各种营销数据，提升效率。
      * 由于数据量大，采用简单分表策略, 减少单表查询时间。
      * 利用[`EhCache`][EhCache]作本地缓存，减少`API`响应时间。
      * 项目中引入[`Swagger`][Swagger]规范化`Restful` `API`, 减少与前端交流成本。同时开发一个[`MyBatis`][MyBatis]插件，完成表结构生成`DTO`并根据表字段注释添加相关文档注解。
      {:.problems}
  - *s*{:.project-circle} **7FRESH项目**{:.project-title} **(AVA工程师)**
    * 参与项目实时订单入库模块优化。
    * `7RFESH`项目主要为京东`7FRESH`运营提供相关的数据分析,实时大屏等功能。
      * 由于业务特殊性导致性能问题，将订单数据从`MongoDB`迁移到`MySQL`,使得查询性能提升4倍。
      * 订单数据入库过程中，减少分布式锁使用，利用`MySQL` **`INSERT ON DUPLICATE KEY UPDATE`**特性解决入库冲突问题，10倍提升了消息消费的性能。
      * 重构订单数据入库流程, 使用得后续各种订单数据接入更容易,标准化。
      {:.problems}
  - *s*{:.project-circle} **京东慧选项目**{:.project-title} **(JAVA工程师)**
    * 参与项目平台化、实时化方案设计。
    * 慧选项目项目主要为京东运营提供选品工具，可以支持对商品属性各种维度的筛选。
      * 由于提供各种维度及模糊查询需求，最后将数据存储在[`Elasticsearch`][Elasticsearch]中。
      * 平台化改造过程中，将业务相关的模块进行抽象改造，通过配置利用工厂模式进行整合，同时采用分库分表设计隔离故障，提升系统可用性; 平台化后大大缩短了新业务线接入的时间，以及减少了重复开发的成本。
      * 为了筛选结果更准确进行实时化改造，接入商品价格，促销等消息。由于上游消息量巨大，但我们关心的商品集很小，利用`Redis`缓存了我们关心商品全量集合做为白名单，过滤掉大量无效的消息。抗住了双11零点巨大流量冲击。
      {:.problems}
  {:.project}
{:.campany}

- **新加坡电信(新加坡) [2015.07 - 2018.03]**{:.campany-name}
  - *s*{:.project-circle} **Phone 8/X 线上抢购项目（mercury）**{:.project-title} **(JAVA工程师)**
    * 主要负责后台`API`开发。
    * 项目为期2个月，需紧急上线，`B/S`项目。功能包括用户兴趣注册，用户线上`iPhone`抢购，用户信息后台管理，邮件及短信发送等。项目采用`Restful`的微服务架构，前后端完全分离。
      * 后端采用基于`SpringBoot`开发的`Restful`无状态`API`。
      * 后端`API`打包成[`AMI(Amazon Machine Images)`][AMI], 部署在[`Amazon EC2(Elastic Compute Cloud)`][EC2]上,可根据实际需要横向扩展，位于`ELB(Elastic Load Balancing)`之后。
      * 数据库使用`PostgreSQL`， `JPA`配合`Hibernate`为数据库访问层。
      * 前端是公司使用的`OSG`（基于[`ractive-foundation`][RactiveFoundaton]) 纯前端浏览器自适应框架。
      * 前端纯静态资源（``CSS``/`JS`/图片等）, 存储于`Amazon S3(Simple Storage Service)`。
      * 使用`Redis`存储集中`Session`信息。
      * 使用[`Amazon SQS(Simple Queue Service)`][SQS]存储`Session`超时事件。
      * 基于`Bamboo`的自动化编译，打包，部署系统。`BUG`修复，代码提交到部署到线上环境只需要`10`分钟。
      {:.problems}

  - *s*{:.project-circle} **Buy flow项目**{:.project-title} **(JAVA工程师)**
    * 负责系统设计, 并带领团队开发实现。
    * 项目提供`Singtel`通用的网上产品，套餐查询与购买功能等。现有项目基于[`Karaf`][Karaf]构建，没办法适应快速的业务变化，难以使用与维护。新项目采用基于`SpringBoot`的`Restful`微服务架构，并复杂配置抽象独立管理，用户可以轻松根据需要灵活配置以适应业务变化。
      * 基于`SpringBoot`开发的`Restful`无状态`API`。
      * `API`打包成`AMI`, 部署在`EC2`上,方便部署与横向扩展
      * 使用[`AWS Lambda`][Lambda]作为任务调度器定时生成报表。
      {:.problems}

  - *s*{:.project-circle}**[MyPortal 门户网站](https://myportal.singtel.com/web/guest/home)**{:.project-title} **(JAVA工程师)**
    * `MyPortal`是新加坡电信（Singtel）的服务整合门户网站，提供类似单点登陆的服务，其中整合了Singtel邮件服务, 云存储服务等。项目采用开源，成熟的企业级门户网站产品 [Liferay][Liferay]。该产品支持模块化开发，热部署，方便开发新功能。
      * 使用Jenkins搭建了一套一键式测试，以及线上部署的环境，提高工作效率并减少机械操作而导致出错。
      * 使用`Nagios`搭建一个监控系统，实时监控服务器的物理状况（`CPU`，内存等的使用情况），应用程序健康情况（`DB`连接，`HTTP`响应，异常日志监控等）,极大提高了系统的可用性。
      * 扩展`Nagios`支持长时间任务，使得`Nagios`可以支持远程服务重启。
      * 基于`React Native`开发一手机`APP`(`NagiosMessager`)，使用`Nagios`提供的`API`获取监控状态。从而更加方便监控和管理应用服务。
      {:.problems}
  {:.project}
{:.campany}

- **成都新电信(NCS)科技有限公司(中国) [2012.11 - 2015.06]**{:.campany-name}
  - *s*{:.project-circle} **Mybill/MCCS/VMB**{:.project-title} **(Unix/Shell工程师)**
    * 系统提供账单生成，查看等功能，后台完成银行间结算等。
      * 主要工作是负责业务系统后台`Shell` `job`新功能开发以及维护。
      * 后台`Job`使用[`Pro*C`][ProC]和`Shell`开发， 工作中开发过多个新`Job`(如账单生成)。
      {:.problems}
  {:.project}
{:.campany}

- **平安科技深圳有限公司 (中国) [2010.7 - 2011.6]**{:.campany-name}
  - *s*{:.project-circle} **车险承保系统**{:.project-title} **(JAVA工程师)**
    * 车险承保系统实现险录单、批改、核保、保费计算、询报价、查询和打印等功能，并提供代理外录单功能，持后援集中核保。系统需要70多台服务器支撑，支持5000人以上同时在线办公。
      * 主要负责公司险承保系统新功能开发以及系统维护，同时还开发实现内部公司内服务器间文件`FTP`同步具。
      * 2011年参与新代险承保系统保费计算核模块开发。新系统采公司内部类似SSH框架构建，持久层使`iBatis`（`Oracle`数据库）。前端采当时流行的`jQuery`库，并以`JSON`作为数据交换格式与服务器进异步通信。
      {:.problems}
  {:.project}
{:.campany}

## **{:.section-icon .fa}**致谢 Acknowledgements**
{:.section}
感谢您花时间阅读我的简历，期待能有机会和您共事。
{:.end}


[Golang]: https://golang.org/ "Golang"

[Webpack]: https://webpack.js.org/ "Webpack"
[gulp]: https://gulpjs.com/ "Gulp"
[Angular]: https://angular.io/ "Angular"
[React]: https://reactjs.org/ "React"
[RN]: https://facebook.github.io/react-native/ "React Native"
[Ractive]: https://ractive.js.org/ "Ractive"
[RactiveFoundaton]: http://ractive-foundation.github.io/ractive-foundation/ "Ractive Foundation"
[jQuery]: https://jquery.com/ "jQuery"
[Requirejs]: http://requirejs.org/ "Requirejs"

[Python]: https://www.python.org/ "Python"
[Ruby]: https://www.ruby-lang.org/en/ "Ruby"
[NodeJS]: https://nodejs.org/en/ "NodeJS"

[Spring]: https://projects.spring.io/spring-framework/ "Spring"
[SpringBoot]: https://projects.spring.io/spring-boot/ "SpringBoot"
[Hibernate]: http://hibernate.org/ "Hibernate"
[Liferay]: https://en.wikipedia.org/wiki/Liferay "Liferay"

[Docker]: https://www.docker.com/ "Docker"
[Nagios]: https://www.nagios.org/ "Nagios"
[Jenkins]: https://jenkins-ci.org/ "Jenkins"
[Bamboo]: https://www.atlassian.com/software/bamboo "Bamboo"
[ELK]: https://www.elastic.co/webinars/introduction-elk-stack "Elasticsearch Logstash Kibana"

[ProC]: https://docs.oracle.com/cd/E11882_01/appdev.112/e10825/toc.htm "Pro*C/C++"

[wireshark]: https://www.wireshark.org/ "Wireshark"

[SVN]: https://subversion.apache.org/ "Subversion"
[Git]: https://git-scm.com/ "Git"
[Maven]: https://maven.apache.org/ "Maven"
[Gradle]: https://gradle.org/ "Gradle"
[Ant]: http://ant.apache.org/ "Ant"

[Apache]: https://httpd.apache.org/ "Apache"
[Tomcat]: http://tomcat.apache.org/ "Tomcat"
[Karaf]: https://karaf.apache.org/ "Karaf"

[AMI]: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html "Amazon Machine Images"
[EC2]: https://aws.amazon.com/ec2/ "Amazon Elastic Compute Cloud"
[SQS]: https://aws.amazon.com/sqs/ "Amazon Simple Queue Service"
[Lambda]: https://aws.amazon.com/lambda/features/ "Amazon Lambda"

[Kubernetes]: https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/ "Kubernetes"
[Swarm]: https://docs.docker.com/engine/swarm/ "Swarm"

[EhCache]: http://www.ehcache.org/ "JAVA’S MOST WIDELY-USED CACHEE"
[MyBatis]: http://www.mybatis.org/mybatis-3/zh/index.html "MyBatis is a first class persistence framework with support for custom SQL, stored procedures and advanced mappings."
[Swagger]: https://swagger.io/ "The Best APIs are Built with Swagger Tools"

[Elasticsearch]: https://www.elastic.co/ "Elasticsearch is a highly scalable open-source full-text search and analytics engine."

