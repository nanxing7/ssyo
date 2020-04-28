+++
draft = true
date = 2020-04-29T00:11:04+08:00
title = ""
description = ""
slug = "" 
tags = []
categories = [SpringBoot]
externalLink = ""
series = []

+++

## 官方示例 getting-started

[官方地址](https://docs.spring.io/spring-boot/docs/2.2.6.RELEASE/reference/html/getting-started.html)

### 介绍 Spring Boot

Spring Boot 的主要目标是：

* 完全没有代码生成，也不需要XML配置。
* 为所有 Spring 开发提供根本上更快且无障碍的入门体验。
* 开箱即用

## 开发您的第一个 Spring Boot 程序

介绍如何开发一个简单的 "Hello World!" 的 Web 程序，我们呢将使用 Maven 来构建它

在开始之前，请打开终端并运行以下命令，以确保安装了有效的 Java 和 Maven 版本：

```bash
$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)
```

```bash
$ mvn -v
Apache Maven 3.5.4 (1edded0938998edf8bf061f1ceb3cfdeccf443fe; 2018-06-17T14:33:14-04:00)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation
```

新建一个Spring Boot 项目，这里我用的是阿里提供的 Spring 脚手架搭建的;

下载完毕解压直接拖入 IDEA 中；

### 编写代码

打开 `src/main/java` 下的 Java 文件

编写我们的代码

```java
package com.example.restservice;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.EnableAutoConfiguration;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@SpringBootApplication
public class RestServiceApplication {

    @RequestMapping("/")
    String home(){
        return "Hello World";
    }

    public static void main(String[] args) {
        SpringApplication.run(RestServiceApplication.class, args);
    }

}
```

这里对这几个注解说明一下

`@RestController` : 这被称为构造型注解（英语太菜，翻译不来）,它为阅读代码的人和Spring提供了提示，提示该类起特定作用。在这种情况下，我们的类是一个Web @Controller，因此 Spring 在处理传入的 Web 请求时会考虑使用它。

`@RequestMapping` 提供 “路由” 信息,它告诉 Spring 任何带有 / 路径的 HTTP 请求都应映射到 home 方法

这两个注解都是属于 Spring MVC 的注解



