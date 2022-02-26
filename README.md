#1、操作备注：
使用elasticsearch head插件创建索引、类型、文档：
点击“复合查询”，界面内输入如下内容，提交请求。

get-together/group/1?pretty
{
"name":"Elasticsearch Denver",
"organizer":"Lee"
}

#安装中文分词器，不安装项目执行报错：
1、去github 下载对应的分词插件
https://github.com/medcl/elasticsearch-analysis-ik/releases
根据不同版本下载不同的分词插件

2、到es的plugins 目录创建文件夹
cd your-es-root/plugins/ && mkdir ik

3、解压ik分词插件到ik文件夹，注意ik文件夹下直接是解压后多个文件夹的具体内容，不要包含在一个父亲文件夹内
unzip elasticsearch-analysis-ik-7.2.0.zip

参考网址：https://www.cnblogs.com/gwyy/p/12205257.html

#项目特点：
该项目只提供了文件搜索内容的展示，没有整个文件内容的展示。



# 简介

Elasticsearch 在开源搜索引擎中基本处于垄断地位,也成为Java程序员的必备技能之一。

这个项目的目的是为了让Elasticsearch学习者轻松、愉快的掌握核心知识点。


# 搜索客户端

elasticsearch-rest-high-level-client

# 软件版本

| 名称          | 版本  |
| ------------- | ----- |
| Spring boot   | 2.0.5 |
| Elasticsearch | 7.2.0 |

# 运行方法

1. 启动Elasticsearch

2. 修改application.properties中的配置：

   ```properties
   elastic.search.host=127.0.0.1
   elastic.search.port=9200
   elastic.search.clusterName=elasticsearch
   ```

如果ES的ip、端口和集群名称和你的不一样需要手动修改。

3. 启动
   运行`src/main/java/cn/pan/EsfilesearchApplication.java`中的main方法.
   

   启动时会从  `src/main/java/cn/pan/MyApplicationRunner.java`中初始化索引,把`src/main/resources/files`目录下的文件导入es.

   默认索引名为`userdoc`，类型名`file`，分片数为`3`，副本为`0`.

4. 访问http://localhost:8080

   首页:

   ![](imgs/1.png)
   
   搜索(src/main/resources/files目录下文件名和内容含有的关键词做测试):

   ![](imgs/2.png)
