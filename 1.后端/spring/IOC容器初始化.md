# IOC容器概述
spring容器即IOC容器，bean存放的地方。bean是由IOC容器实例化、组装、管理的对象。spring应用启动，差不多就是容器初始化的过程，主要分为2步，
- bean元数据收集注册
- bean初始化
# bean元数据
### bean元数据注册
bean元数据，即描述一个bean的原始信息，最终以BeanDefinition存在内存。
bean元数据可通过多种方式注册，并由BeanDefinitionRegistry维护
- @ComponentScan + @Component
- @Configuration + @Bean
- @Import
	- 普通类
	- @Configuration类
	- ImportSelector接口
	- ImportBeanDefinitionRegistrar接口
- springboot应用，@EnableAutoConfiguration + spring.factories
- xml配置(已过时)
### BeanDefinition拓展点
在bean元数据收集注册完成后，spring容器提供了额外的口子，可以对BeanDefinition进行修改、新增等操作;
- BeanDefinitionRegistryPostProcessor
- BeanFactoryPostProcessor

对于这些特殊的bean，也会注入spring容器，执行顺序按照PriorityOrdered接口、Ordered接口、未实现排序接口
举例:
AspectJWeavingEnabler
CustomAutowireConfigurer
ConfigurationClassPostProcessor
# bean初始化
spring容器根据BeanDefiniton信息，进行bean的实例化和初始化工作.
### spring bean的生命周期
- 实例化 Instantiation
对应bean自身的构造方法
- 属性赋值 Populate
对应bean自身的getter/setter方法
- 初始化 Initialization
对应bean自身的init-method方法
- 销毁 Destruction
对应bean自身的destroy-method方法
```flow
st=>start: BeanDefinition
e=>end: End
Instantiation=>operation: 实例化
Populate=>operation: 属性赋值
Initialization=>operation: 初始化
Destruction=>operation: 销毁
st->Instantiation->Populate->Initialization->e
```
### bean生命周期拓展点
spring bean的拓展点超级多，这也是spring的扩展性好的原因。主要是一些后处理器PostProcessor，这些接口的实现类独立于bean本身，会注册到Spring容器。在spring容器创建任何bean的时候，这些后处理器都会发生作用

<font color=#0000ff size=5>IOC容器级别拓展</font>
- InstantiationAwareBeanPostProcessor
- SmartInstantiationAwareBeanPostProcessor
- MergedBeanDefinitionPostProcessor
- BeanPostProcessor

<font color=#0000ff size=5>Bean自身拓展</font>

- BeanFactoryAware
- BeanNameAware
- @PostConstruct
- InitializingBean

# 完整生命周期
![](assets/spring-bean生命周期.png)
