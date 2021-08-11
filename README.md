#### Versões Java e Spring
- Spring 2.5.3 +
- Java 11 +

#### Preparando o Ambiente
Antes de começar os projetos do curso instale databases ***Elasticsearch*** e ***Redis***.

#### Elasticsearch:
- Download: MSI BETA
- Instalação: execute o instalador e vá clicando em next mantendo todas as configurações no padrão.
- O Elasticsearch carregará automaticamente.

#### Redis:
- Download: Redis-x64-3.2.100.msi
- Execute o instalador, aceite os termos e clique em next
- Selecione a opção Add the Redis installation folder to PATH enviroment variable e clique em next.
- Mantenha a porta na configuração default (6379) e clique em next.
- Mantenha a max memory na opção default (100MB) e clique em next.
- Clique em Install e após a finalização da instalação clique em Finish.
- Para testar o Redis abra o Windows power shell ou o prompt de comando, digite ***redis-cli*** e dê enter.
- O prompt exibirá o IP 127.0.0.1:6379
- Digite a palavra ***ping*** e dê enter, o prompt responderá com a palavra ***PONG***.

#### Dependências:
Para cada um dos projetos seguem as dependências que devem ser inseridas nos arquivos **build.gradle**

- [x] config-server:
```
plugins {
 id 'org.springframework.boot' version '2.5.3'
 id 'io.spring.dependency-management' version '1.0.11.RELEASE'
 id 'java'
}
​
group = 'com.dio'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
​
repositories {
 mavenCentral()
}
​
ext {
 set('springCloudVersion', "2020.0.3")
}
​
dependencies {
 implementation 'org.springframework.boot:spring-boot-starter-actuator'
 implementation 'org.springframework.boot:spring-boot-starter-web'
 implementation 'org.springframework.cloud:spring-cloud-config-server'
 implementation 'org.springframework.cloud:spring-cloud-starter-config'
 testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
​
dependencyManagement {
 imports {
  mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
 }
}
​
test {
 useJUnitPlatform()
}
​
```
- [x] gateway:
```
plugins {
 id 'org.springframework.boot' version '2.5.3'
 id 'io.spring.dependency-management' version '1.0.11.RELEASE'
 id 'java'
}
​
group = 'com.dio'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
​
repositories {
 mavenCentral()
}
​
ext {
 set('springCloudVersion', "2020.0.3")
}
​
dependencies {
 implementation 'org.springframework.boot:spring-boot-starter-actuator'
 implementation 'org.springframework.cloud:spring-cloud-starter-config'
 implementation 'org.springframework.cloud:spring-cloud-starter-gateway'
 implementation 'org.springframework.cloud:spring-cloud-starter-bootstrap'
 implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-client'
 testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
​
dependencyManagement {
 imports {
  mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
 }
}
​
test {
 useJUnitPlatform()
}
```
- [x] product-catalog:

```
plugins {
 id 'org.springframework.boot' version '2.5.3'
 id 'io.spring.dependency-management' version '1.0.11.RELEASE'
 id 'java'
}
​
group = 'com.dio'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
​
repositories {
 mavenCentral()
}
​
ext {
 set('springCloudVersion', "2020.0.3")
}
​
​
dependencies {
 implementation 'org.springframework.boot:spring-boot-starter-actuator'
 implementation 'org.springframework.boot:spring-boot-starter-data-elasticsearch'
 implementation 'org.springframework.boot:spring-boot-starter-web'
 implementation 'org.springframework.cloud:spring-cloud-starter-config'
 implementation 'org.springframework.cloud:spring-cloud-starter-bootstrap'
 implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-client'
 testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
​
dependencyManagement {
 imports {
  mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
 }
}
​
test {
 useJUnitPlatform()
}
​
```
- [x] service-discovery:
```
plugins {
 id 'org.springframework.boot' version '2.5.3'
 id 'io.spring.dependency-management' version '1.0.11.RELEASE'
 id 'java'
}
​
group = 'com.dio'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
​
repositories {
 mavenCentral()
}
​
ext {
 set('springCloudVersion', "2020.0.3")
}
dependencies {
 implementation 'org.springframework.cloud:spring-cloud-starter-config'
 implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-server'
 implementation 'org.springframework.cloud:spring-cloud-starter-bootstrap'
 testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
​
dependencyManagement {
 imports {
  mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
 }
}
​
test {
 useJUnitPlatform()
}
​
```

- [x] shopping-cart:

```
plugins {
 id 'org.springframework.boot' version '2.5.3'
 id 'io.spring.dependency-management' version '1.0.11.RELEASE'
 id 'java'
}
​
group = 'com.dio'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'
​
repositories {
 mavenCentral()
}
​
ext {
 set('springCloudVersion', "2020.0.3")
}
​
dependencies {
 implementation 'org.springframework.boot:spring-boot-starter-actuator'
 implementation 'org.springframework.boot:spring-boot-starter-data-redis'
 implementation group: 'redis.clients', name: 'jedis', version: '3.6.3'
 implementation 'org.springframework.boot:spring-boot-starter-web'
 implementation 'org.springframework.cloud:spring-cloud-starter-config'
 implementation 'org.springframework.cloud:spring-cloud-starter-bootstrap'
 implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-client'
 testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
​
dependencyManagement {
 imports {
  mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
 }
}
​
test {
 useJUnitPlatform()
}
​
```

## 👨🏻‍🚀 Sobre mim
<a href="https://www.linkedin.com/in/mateus-macedo-937a32163/">
 <img style="border-radius:50%" width="100px; "src="https://avatars.githubusercontent.com/u/63172367?s=460&u=11fd26ea8a7f5663d7707d7ef254e4f8bfca1b05&v=4"/>
 <p>Mateus Macedo</p>
</a>
