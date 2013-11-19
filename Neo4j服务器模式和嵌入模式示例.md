Neo4j有两种访问模式：服务器模式和嵌入模式[参考](http://docs.neo4j.org.cn/deployment-scenarios.html)，下面主要讲windows和ubuntu下这两种模式的配置与访问示例

##1.1 Windows下Neo4j服务器模式安装与示例
####安装：

1.下载Neo4j，我下载的版本是：neo4j-community_windows_2_0_0-M06.exe [地址](http://www.neo4j.org/download)；  
2.windows下直接安装即可；  
3.打开 http://localhost:7474 看到图形化界面则安装成功！可以直接进行访问！
####示例：
1.neo4j-community-2.0.0-M06-windows.zip\lib下所有jar包；  
2.自己下载的jar包：  
    com.sun.jersey.jersey-core-1.4.0.jar [地址](http://www.java2s.com/Code/Jar/c/Downloadcomsunjerseyjerseycore140jar.htm);    
    javax.ws.rs.jar[地址](http://www.java2s.com/Code/Jar/j/Downloadjavaxwsrsjar.htm);  
    jersey-client-1.9.jar [地址](http://www.java2s.com/Code/Jar/j/Downloadjerseyclient19jar.htm);  

3.具体代码参考（[ java连接Neo4j服务器--第四部分](http://blog.csdn.net/adam_wzs/article/details/8622250)）  
####参考  
[ java连接Neo4j服务器](http://blog.csdn.net/adam_wzs/article/details/8622250)  

##1.2 Windows下neo4j嵌入模式
####示例：
1.下载neo4j-community-2.0.0-M06-windows.zip[地址](http://www.neo4j.org/download);  
2.解压缩，然后导入其中lib到项目中；  
3.在项目properties->java build path->libraries->add jars->选择lib中的所有jar；  
4.具体示例,参考（[neo4j的入门示例](http://blog.csdn.net/cfeibiao/article/details/6842944)）;
####参考  

[neo4j的入门示例](http://blog.csdn.net/cfeibiao/article/details/6842944)  
##2 Ubuntu下neo4j的服务器模式安装  
1.下载neo4j-enterprise-2.0.0-M06-unix.tar.gz[地址](http://www.neo4j.org/download)；    
2.Ubuntu配置jdk1.7；  
3.解压缩neo4j-enterprise-2.0.0-M06-unix.tar.gz后进入目录；  
4.配置neo4j服务器允许远程访问，[参考](http://blog.fens.me/nosql-neo4j-intro/),具体为修改neo4j-server.peoperties,
```java
vim conf/neo4j-server.peoperties
#取消注释
org.neo4j.server.webserver.address=0.0.0.0
```  
5.运行bin/neo4j start 即可，可以通过http://192.168.0.187:7474/browser/ 访问。
