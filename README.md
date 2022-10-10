### General

You have to push your config files in this repository.

Config file name should have next view: `${application}-${profile}.yml`  
For example: `ezchoice-test.yml`

### Set up

To integrate your Spring Boot application with Spring Cloud Configs server you have to:

1. Add dependencies to `pom.xml`:

```xml

<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-dependencies</artifactId>
            <version>${spring-cloud.version}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

```xml

<dependencies>
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>spring-cloud-starter-config</artifactId>
    </dependency>
</dependencies>
```

**Important**  
spring-cloud version defines depends on Spring Boot version which you are using.  
[Choose your version of Spring Cloud here.](https://spring.io/projects/spring-cloud)

2. In your local `yaml` define next properties:

```yaml
spring:
  cloud:
    config:
      uri: http://root:password@localhost:8888
  application:
    name: ${application}
  profiles:
    active: ${profile}
```
    


