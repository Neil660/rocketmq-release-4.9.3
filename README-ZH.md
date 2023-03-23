## 模块介绍：
broker: broker 模块（broke 启动进程）

client ：消息客户端，包含消息生产者、消息消费者相关类

example: RocketMQ 示例代码

namesrv：NameServer实现相关类（NameServer启动进程）

store：消息存储实现相关类

## 需要添加的环境变量
IDEA编辑启动类，然后在Environment variables里面添加环境变量。路径不能有空格
#### 1、启动namesrv
启动类：org.apache.rocketmq.namesrv.NamesrvStartup.main

环境变量：ROCKETMQ_HOME=C:\Tools\IJetBrains\projects\rocketmq-release-4.9.3\distribution
#### 2、启动broker
启动类：org.apache.rocketmq.broker.BrokerStartup.main

环境变量：ROCKETMQ_HOME=C:\Tools\IJetBrains\IntelliJ IDEA 2018.3.5\Projects\enterprise\rocketmq-release-4.9.3\distribution

追加C:\Tools\IJetBrains\projects\rocketmq-release-4.9.3\distribution\conf\broker.conf文件：\
 autoCreateTopicEnable=true \
 namesrvAddr=127.0.0.1:9876

idea启动配置添加Program Arguments：-c C:\Tools\IJetBrains\projects\rocketmq-release-4.9.3\distribution\conf\broker.conf
#### 3、启动consumer
启动类：org.apache.rocketmq.example.quickstart.Consumer.main

修改源码设置namesrv地址：consumer.setNamesrvAddr("127.0.0.1:9876");
#### 4、启动producer
启动类：org.apache.rocketmq.example.quickstart.Producer.main

修改源码设置namesrv地址：producer.setNamesrvAddr("127.0.0.1:9876");
