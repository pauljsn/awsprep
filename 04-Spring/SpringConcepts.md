# Spring
Spring Framework: An unorthodox guide: https://www.marcobehler.com/guides/spring-framework

## Spring Aspect
Spring’s Proxy Facilities
Because under the hood, any Spring @Bean method can return you something that looks and feels like (in your case) a UserService, but actually isn’t.

It can return you a proxy.

The proxy will at some point delegate to the UserService you wrote, but first, will execute its own functionality.

spring clig proxies
More specifically, Spring will, by default, create dynamic Cglib proxies, that do not need an interface for proxying to work (like JDK’s internal proxy mechanism): Instead, Cglib can proxy classes through subclassing them on the fly.

Spring AOP Proxy vs AspectJ Proxy
Apart from what others have stated - just to rephrase, `there are two major differences`:

1. One is related to the type of weaving.
2. Another to the joinpoint definition.

**Spring-AOP:** Runtime weaving through proxy using concept of `dynamic proxy if interface exists or cglib library if direct implementation provided.`

**AspectJ:** Compile time weaving through `AspectJ Java Tools(ajc compiler)` if source available or post compilation weaving (using compiled files). Also, load time weaving with Spring can be enabled - it needs the `aspectj` definition file and offers flexibility.

Compile time weaving can offer benefits of performance (in some cases) and also the `joinpoint definition in Spring-aop is restricted to method definition only which is not the case for AspectJ.`

An additional note: **If performance under high load is important, you'll want AspectJ which is 9-35x faster than Spring AOP**. 10ns vs 355ns might not sound like much, but I've seen people using LOTS of Aspects. 10K's worth of aspects. In these cases, your request might hit a thousands of aspects. In that case you're adding ms to that request.
https://stackoverflow.com/questions/1606559/spring-aop-vs-aspectj

```mermaid
graph LR
    A[Spring] --> B[AOP]
    A[Spring] --> C[Aspect J]
```

#### Spring-AOP Pros

- It is simpler to use than  AspectJ, since you don't have to use LTW ([load-time weaving][1]) or the AspectJ compiler.

- It uses the Proxy pattern and the Decorator
  pattern

#### Spring-AOP Cons

- This is proxy-based AOP, so basically you can only use method-execution joinpoints.
- Aspects aren't applied when calling another method within the same class.
- There can be a little runtime overhead.
-  Spring-AOP cannot add an aspect to anything that is not created by the Spring factory

#### AspectJ Pros

- This supports all joinpoints. This means you can do anything.
- There is less runtime overhead than that of Spring AOP.

#### AspectJ Cons

- Be careful. Check if your aspects are weaved to only what you wanted to be weaved.
- You need extra build process with AspectJ Compiler or have to setup LTW (load-time weaving)

[1]: http://www.eclipse.org/aspectj/doc/next/devguide/ltw.html


### Spring Batch
* https://terasoluna-batch.github.io/guideline/5.0.0.RELEASE/en/single_index.html#Ch02_SpringBatchArch_Detail