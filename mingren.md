连接池线程分析

![图例](https://github.com/zuoca/java-apns/blob/mingren/analyse/conneciton_pool.png)


1. 创建ApnsPooledConnection

2. 在execute任务时通过ThreadLocal获取ApnsConnectionImpl对象用于消息发送

3. 每个ApnsConnectionImpl创建一条长连接及一个Monitor线程

4. Monitor线程通过监控Socket的输入流(即响应)判断消息发送是否成功
