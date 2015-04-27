---
title: TracEE backend for Apache Log4J2
category: backends
layout: backend
menu_name: Log4J2
toc:
order: 30
---
> Backend implementation for [log4j2 (2.0+)](http://logging.apache.org/log4j/2.x/)

## Installation

You need exactly one backend provider on your runtime classpath. Add following to your `pom.xml` to add this module to your dependency tree:

```xml
<dependencies>
...
	<dependency>
		<groupId>io.tracee.backend</groupId>
		<artifactId>tracee-log4j2</artifactId>
		<version>RELEASE</version> <!-- You should specify a version instead -->
		<scope>runtime</scope>
	</dependency>
...
</dependencies>
```