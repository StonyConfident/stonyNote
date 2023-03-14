# LoggingSystem
属于SpringBoot的日志标准，支持的日志框架
![](assets/log加载-a690cbeb.png)
包括java自带和Slf4J两个标准
- LogbackLoggingSystem
配置文件位置，"logback-test.groovy", "logback-test.xml", "logback.groovy", "logback.xml"
以及-spring后缀的;

- Log4J2LoggingSystem
配置文件，"log4j2.yaml", "log4j2.yml"

- JavaLoggingSystem
配置文件位置，logging.properties

# 其他日志框架
一般是在LoggingSystem还没初始化完成前，采用其他日志框架，比如commons-logging，比如spring banner图标的打印;

# LoggingSystem加载过程
以logback框架为例分析
