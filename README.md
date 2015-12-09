
## Zookeeper客户端

> 基于Maven构建源码，并将日志由log4j改为slf4j。

### 源码参考

> zkclient源码地址 [https://github.com/sgroschupf/zkclient/tree/0.7.0]

### 注意事项

**支持zookeeper版本为3.4.6**

**引用zookeeper-3.4.6包时，如果去掉下面两个组件测试会报错**

```
	   <dependency>
			<groupId>org.apache.zookeeper</groupId>
			<artifactId>zookeeper</artifactId>
			<version>3.4.6</version>
			<exclusions>
				<exclusion>
					<groupId>log4j</groupId>
					<artifactId>log4j</artifactId>
				</exclusion>
				<exclusion>
					<groupId>org.slf4j</groupId>
					<artifactId>slf4j-log4j12</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
```

**下面的测试用例无法通过**

```
zx.soft.zkclient.SaslAuthenticatedTest
```

**如果存在log4j和slf4j-log4j12，则无法输出日志**
