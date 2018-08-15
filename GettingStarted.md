# 环境要求

- Spring Boot 2.0.4.RELEASE
- Java 8 or 9
- Spring Framework 5.0.8.RELEASE or above

## 服务容器

### 内置容器

|   |   |
| - | - |
| Name | Servlet Version |
| Tomcat 8.5 | 3.1 |
| Jetty 9.4 | 3.1 |
| Jetty 9.4 | 3.1 |

部署时，所选容器Servlet版本应为3.1+。
> 以tomcat为例，应为tomcat8.0+
> 官方给出的不同版本的Tomcat所对应的Servlet/JSP规范和JDK版本如下图所示：
> ![tomcat-servlet-version](images\tomcat-servlet-version.png)

## Maven

pom.xml文件中，有两种形式添加springboot依赖。

- parent形式添加依赖

``` xml
<!-- Inherit defaults from Spring Boot -->
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.0.4.RELEASE</version>
</parent>
```

- dependencyManagementx形式添加

``` xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <!-- Import dependency management from Spring Boot -->
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-dependencies</artifactId>
            <version>2.0.4.RELEASE</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

## 版本升级

升级旧版本的springboot时，在pom.xml文件中添加如下依赖，可以在运行时打印需要进行的修改，手动修改完毕后，记得删除该依赖

``` xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-properties-migrator</artifactId>
    <scope>runtime</scope>
</dependency>
```