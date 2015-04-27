---
title: TracEE binding for Spring MVC
category: bindings
layout: binding
menu_name: SpringMVC
order: 140
---


> This tracee module reads the incoming TracEE context for requests to your Spring MVC controllers and generates invocationIds if needed. It adds the TPIC header to your responses as well. - If you don't like to expose the TPIC in your responses (maybe you want to hide it from your users), you should take an individual TracEE configuration.

This module requires Spring 3.1.0 or above.

## Installation

Add `tracee-springmvc` to your application dependencies. That's all! - For example in maven-style projects add the following coordinates to the `pom.xml`:

```xml
<dependencies>
...
    <dependency>
	<groupId>io.tracee.binding</groupId>
	<artifactId>tracee-springmvc</artifactId>
    <version>RELEASE</version> <!-- You should specify a version instead -->
    </dependency>
...
</dependencies>
```

Then you're able to use our `TraceeInterceptor` in two ways:

With Spring JavaConfig:

```java
@Configuration
@EnableWebMvc
public class YourApplicationConfig extends WebMvcConfigurerAdapter {

    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(new io.tracee.binding.springmvc.TraceeInterceptor());
    }

}
```

With XML configuration:

```xml
<mvc:interceptors>
	<bean id="traceeInterceptor" class="io.tracee.binding.springmvc.TraceeInterceptor">
		<property name="profileName" value="default"/> <!-- The profile configuration is optional -->
	</bean>
</mvc:interceptors>
...
```
