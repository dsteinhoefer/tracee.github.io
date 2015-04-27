---
title: TracEE backend for Logging Frameworks without MDC
category: backends
layout: backend
menu_name: ThreadLocal
toc:
order: 100
---
> Native backend implementation. Messages on `TraceeLogger` with loglevel WARN and ERROR are redirected to stderr. All other messages are discarded.
  
## Installation

You need exactly one backend provider on your runtime classpath. Add following to your `pom.xml` to add this module to your dependency tree: 

```xml
<dependencies>
...
	<dependency>
		<groupId>io.tracee.backend</groupId>
		<artifactId>tracee-threadlocal-store</artifactId>
		<version>RELEASE</version> <!-- You should specify a version instead -->
		<scope>runtime</scope>
	</dependency>
...
</dependencies>
```
