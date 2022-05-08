# 프로젝트 생성

사전 준비물

* Java 11
* IDE: IntelliJ 또는 Eclipse

스프링 부트 스타터 사이트로 이동해서 스프링 프로젝트 생성

* https://start.spring.io

프로젝트 선택

![](<../.gitbook/assets/스크린샷 2022-05-08 오후 10.23.23.png>)

* Project: Gradle Project
* Spring Boot: 뒤에 () 가 붙지 않는 최신버전 사
* Language: Java
* Packaging: Jar
* Java: 11

Project Metadata

* GroupId: hello
* artifactId: hello-spring

Dependencies: Spring Web , Thymeleaf

Gradle 전체 설정

* 'build.gradle'

```
plugins {
id 'org.springframework.boot' version '2.3.1.RELEASE'
id 'io.spring.dependency-management' version '1.0.9.RELEASE'
id 'java'
}
group = 'hello'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
repositories {
mavenCentral()
}
dependencies {
implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
implementation 'org.springframework.boot:spring-boot-starter-web'
testImplementation('org.springframework.boot:spring-boot-starter-test') {
exclude group: 'org.junit.vintage', module: 'junit-vintage-engine'
}
}
test {
useJUnitPlatform()
}
```

