- SpringBoot 的作用
    - 简化 maven 依赖配置
    - 简化被整合的框架配置
        - 基于 Spring Boot 提供了一系列的 starter 构件，这些 starter 中包含了配置相关框架的 bean 的代码
        - 这些 bean 是可被覆盖的，使得开发者能自由使用框架
    - 简化部署运维
        - 内嵌 servlet 服务器，默认打包成可执行 jar
        - 配置项集中在 application.properties/yml 中
        - jar包支持外部配置覆盖内部配置
        - 提供了各种 endpoint 以便运维
- 拓展学习推荐
    - spring in action
    - spring boot 实战
    - https://spring.io/projects/spring-boot#learn

并发安全，默认的 Controller bean 都是单例

参数校验 spring-boot-starter-validation

- 统一处理
    - filter 过滤器 在servlet 前后进行处理
    - interceptor 拦截器 在 handler 前后进行处理
    - Aop 对 Spring Bean 进行增强处理