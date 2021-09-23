- 数据库连接池简介
    - Java中的数据源就是 javax.sql.DataSource, DataSource 的创建可以有不同的实现。DataSource 通常被称为数据源，它包含连接池和连接池管理两个部分，习惯上也经常把 DataSource 称为连接池
- 数据库连接池原理
    - 在系统初始化的时候，将多个数据库连接作为对象存储在内存中
    - 当用户需要访问数据库时，并非建立一个新的连接，而是从连接池中取出一个已建立的空闲连接对象
    - 优点
        - 资源重用
        - 更快的系统反应速度
        - 统一的连接管理，避免数据库连接泄漏

数据库连接池配置
```
#数据库连接地址
spring.datasource.url
#数据库用户名
spring.datasource.username
#数据库密码
spring.datasource.password
#数据库驱动
spring.datasource.driver-class-name
#最大活动的连接数
spring.datasource.tomcat.maxActive
#初始化连接数
spring.datasource.tomcat.initialSize=1
#从池中取连接到最大等待时间，单位ms
spring.datasource.tomcat.maxWait=60000
#最小空闲连接
spring.datasource.tomcat.minIdle=10
#最大空闲连接
spring.datasource.tomcat.maxIdle=15
```

- 数据库事务简介
    - 数据库事务 database transaction, 是指作为单个逻辑工作单元执行的一系列操作，要么完全地执行，要么完全地不执行

- MyBatis 简介
    - MyBatis 它是一种持久层框架
    - 与 ORM 框架不同的是，它将 SQL 映射成 java 方法，而不是将表映射成 java 对象
    - 手动 jdbc
    - 半自动 mybatis
    - 全自动
        - hibernate
        - spring data jpa
    - MyBatis 基本要素
        - configuration.xml 全局配置文件
            - 数据源的配置
            - 事务配置
            - 映射文件的配置
        - mapper.xml 核心映射文件
            - 映射关系 resultMap 的定义
            - 动态的 sql 描述
        - sqlSession接口
            - 提供调用 sql 的 API

- ORM
    - 即 object-relational Mapping 对象关系映射，它的作用是在关系型数据库和业务实体对象之间作一个映射，这样，我们在具体的操作业务对象的时候，就不需要再去和复杂的 SQL 语句打交道，只需简单的操作对象的属性和方法

- JPA 简介
    - JPA 是 Java Persistence API 的简介，中文名 JAVA 持久层 API，是 JDK 5.0 注解或 XML 描述对象 - XML描述对象 - 关系表的映射关系，并将运行期实体对象持久化到数据库中。
        - 功能
            - 映射元数据: JPA 支持 XML 和 JDK 5.0 注解两种元数据的形式
            - API: 用来操作实体对象，执行 CRUD 操作
            - 查询语言: 使用面向对象而非面向数据库的查询语言查询数据，即 JPQL

- Spring Data 简介
    - Spring Data, Spring 的一个子项目，用于简化数据访问，支持NoSql和关系数据库存储，主要目标是使数据访问变得方便快捷

```
@Entity
标识是一个实体bean
@Table
用来定义entity主表的name，catalog，schema等属性
@Column 
Column 元数据定义了映射到数据库的列的所有属性；列名，是否唯一，是否允许为空，是否允许更新等
@Id
声明当前field为映射表中的主键列
@Transient
Transient用来注释entity的属性，指定的这些属性不会被持久化，也不会为这些属性建表
```