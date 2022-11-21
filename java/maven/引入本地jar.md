# 引入本地jar
1. 把jar文件放入resources/lib文件夹
2. 修改pom
```java
<dependencys>
    <dependency>
        <groupId>com.xsgo</groupId>
        <artifactId>app</artifactId>
        <version>0.01</version>
        <scope>system</scope>
        <systemPath>${project.basedir}/src/main/resources/lib/app-0.01.jar</systemPath>
    </dependency>
</dependencys>

<build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <!--将本地jar打包-->
                <configuration>
                    <includeSystemScope>true</includeSystemScope>
                </configuration>
            </plugin>
        </plugins>
    </build>
```