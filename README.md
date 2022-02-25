#操作备注：
使用elasticsearch head插件创建索引、类型、文档：
点击“复合查询”，界面内输入如下内容，提交请求。

get-together/group/1?pretty -d
{
"name":"Elasticsearch Denver",
"organizer":"Lee"
}



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
