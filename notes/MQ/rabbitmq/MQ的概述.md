# MQ的概述

- [MQ的优势](#mq的优势)
- [劣势](#劣势)
    - [系统可用性降低](#系统可用性降低)
    - [系统复杂度提高](#系统复杂度提高)
    - [一致性问题](#一致性问题)
- [RabbitMQ的工作模式](#rabbitmq的工作模式)
- [JMS](#jms)

## MQ的优势
- 应用解耦
- 异步提速
- 削峰填谷

## 劣势
- 系统可用性降低
- 系统复杂度提高
- 一致性问题

### 系统可用性降低
系统引入的外部依赖越多，系统稳定性越差。一旦MQ宕机，就会对业务造成影响。如何保证MQ的高可用？

### 系统复杂度提高
MQ的加入大大增加了系统的复杂度，以前系统间是同步的远程调用，现在是通过MQ进行异步调用。如何保证消息没有被重复消费？怎么处理消息丢失情况？那么保证消息传递的顺序性？

### 一致性问题
A系统处理完业务，通过MQ给B，C，D三个系统发消息数据，如果B系统、C系统处理成功， D系统处理失败。如何保证消息数据处理的一致性？

## RabbitMQ的工作模式
https://www.rabbitmq.com/getstarted.html

RabbitMQ提供了7种工作模式:
1. 简单模式 (Hello World!)
2. Work Queues
3. Publish/Subscribe 发布与订阅模式 
4. Routing 路由模式
5. Topics 主题模式
6. RPC 远程调用模式
7. Publisher Confirm

## JMS
JMS即Java消息服务(JavaMessage Service)应用程序接口，是一个Java平台中关于面向消息中间件的API。JMS是JavaEE规范中的一种，类比JDBC。

很多消息中间件都实现了JMS规范，例如: ActiveMQ，**RabbitMQ官方没有提供JMS的实现包**，但是开源社区有。
