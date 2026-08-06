<a id="readme-top"></a>

<div align="center">

# log4j2-plus-spring-boot-starter

**Spring Boot Starter for log4j2-plus**

[![Maven Central](https://img.shields.io/maven-central/v/io.github.easy4j/log4j2-plus-spring-boot-starter)](https://github.com/easy-4-java/log4j2-plus-spring-boot-starter)
[![Java](https://img.shields.io/badge/Java-17-orange)](#3-requirements-and-compatibility)
[![License](https://img.shields.io/badge/license-Apache-2.0-green)](https://www.apache.org/licenses/LICENSE-2.0)

[简体中文](./README.zh-CN.md) | [English](./README.md)

[Positioning](#1-positioning) · [Capabilities](#2-core-capabilities) ·
[Dependency](#5-dependency) · [Quick Start](#6-quick-start) ·
[Configuration](#7-configuration-reference) · [Versions](#9-version-lines-and-compatibility) ·
[Build](#10-build-and-test) · [License](#12-license)

</div>

---

> **Current Version**：`1.0.1.RELEASE`<br>
> **JDK Baseline**：`17`<br>
> **Group ID**：`io.github.easy4j`<br>
> **Artifact ID**：`log4j2-plus-spring-boot-starter`<br>
> **License**：Apache License 2.0<br>

## 1. Positioning

**log4j2-plus-spring-boot-starter** is a Spring Boot starter that integrates **log4j2-plus** for applications using log4j2-plus. It provides auto-configuration, property binding, and ready-to-use beans so that applications can consume log4j2-plus capabilities with minimal setup.

| Dimension | Description |
|---|---|
| Type | Spring Boot Starter |
| Consumers | Spring Boot applications using log4j2-plus |
| Core Capabilities | auto-configuration, property binding, ready-to-use beans for log4j2-plus |
| JDK | `17` |
| Coordinates | `io.github.easy4j:log4j2-plus-spring-boot-starter:1.0.1.RELEASE` |
| Config Prefix | `log4j2.plus` |

## 2. Core Capabilities

| Capability | Status | Description |
|---|:---:|---|
| Auto-configuration | ✅ Stable | Registers log4j2-plus beans automatically |
| Property Binding | ✅ Stable | Binds `log4j2.plus.*` to `Log4jJdbcProperties` |
| `Log4jJdbcAppenderTemplate` bean | ✅ Stable | Auto-registered via Log4jJdbcAutoConfiguration |

## 3. Requirements and Compatibility

| Dependency | Minimum | Evidence |
|---|---:|---|
| JDK | `17` | `pom.xml` |
| Spring Boot | `2.0.3.RELEASE` | `pom.xml` parent |
| Maven | `3.6+` | Maven Enforcer |

## 4. Auto-configuration

The starter auto-configures the following beans:

| Bean | Condition | Missing Behavior |
|---|---|---|
| `Log4jJdbcAppenderTemplate` | classpath + property | not created |

Auto-configuration registration:

- `META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports` (Spring Boot 2.7+ / 3.x / 4.x)
- `META-INF/spring.factories` (Spring Boot 2.x legacy)

## 5. Dependency

```xml
<dependency>
    <groupId>io.github.easy4j</groupId>
    <artifactId>log4j2-plus-spring-boot-starter</artifactId>
    <version>1.0.1.RELEASE</version>
</dependency>
```

No additional easy4j component dependencies.

## 6. Quick Start

### 6.1 Add dependency

Add the dependency above to your `pom.xml`.

### 6.2 Configure

```yaml
log4j2.plus:
  enabled: true
```

### 6.3 Use the bean

```java
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

Then inject the auto-configured bean in your code:

```java
@Autowired
private Log4jJdbcAppenderTemplate jdbcAppenderTemplate;
```

## 7. Configuration Reference

### 7.1 Config Prefix

`log4j2.plus`

### 7.2 Configuration Items

| Property | Type | Default | Required | Description | Sensitive |
|---|---|---|:---:|---|:---:|
| `log4j2.plus.enabled` | boolean | `true` | No | Enable the starter | No |
<!-- additional properties below -->

## 8. Version Lines and Compatibility

| Branch | JDK | Spring Boot | Component Version | Status |
|---|---:|---:|---|:---:|
| `2.3.x` / `2.7.x` | `8+` | 2.3.x / 2.7.x | `1.0.x` | Maintenance |
| `3.0.x` ~ `3.5.x` | `17` | 3.x | `2.0.x` | Maintenance |
| `4.0.x` / `4.1.x` | `17+` | 4.x | `3.0.x` | Active |

## 9. Build and Test

```bash
mvn clean verify
mvn -pl log4j2-plus-spring-boot-starter -am test
```

## 10. Troubleshooting

| Symptom | Diagnosis | Resolution |
|---|---|---|
| Bean not created | Check auto-configuration report | Verify `log4j2.plus.enabled=true` and classpath |
| `ClassNotFoundException` | Missing dependency | Add the required module |
| Version conflict | `mvn dependency:tree` | Use BOM for version alignment |

## 11. Contribution

1. Fork the repository.
2. Create a feature branch.
3. Run `mvn clean verify` before submitting.
4. Submit a pull request.

## 12. License

This project is licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

---

<div align="center">

[Back to top](#readme-top) · [Issues](https://github.com/easy-4-java/log4j2-plus-spring-boot-starter/issues) · [Repository](https://github.com/easy-4-java/log4j2-plus-spring-boot-starter)

</div>
