[TOC]

### scp-eureka描述:

`scp-eureka` SpringCloud项目Eureka中心
### 基础软件:

1. `github`
2. `jdk1.8`

 

#### local profile配置文件:

```yaml
server:
  port: 9009

spring:
  application:
    name: SCP-EUREKA

eureka:
  instance:
    hostname: [高可用模式下写其他Eureka服务名]
    #hostname: localhost
  client:
    register-with-eureka: false # 不向自己注册/高可用模式下修改为true活着去掉默认为true
    fetch-registry: false # 不检索服务/高可用模式下修改为true活着去掉默认为true
    serviceUrl:
      defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/
      #defaultZone: http://localhost:8761/eureka/
logging:
  level:
    com.lv.cloud: debug
```



####    高可用:
```yaml
本地新建application-peer1.yml,application-peer2.yml多个文件互相配置自己注册到对方

 
```
#### spring-Boot命令启动:

```markdown
java -jar scp-eureka-1.0.0-SNAPSHOT.jar --spring.profiles.active=peer1
```

  



