# lmaven
learn 2 maven
编译 compile
测试 test
打包 package
运行 run
部署 install
编译插件
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-compiler-plugin</artifactId>
	<configuration>
		<source>1.8</source>
		<target>1.8</target>
	</configuration>
</plugin>
设置主程序插件
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-shade-plugin</artifactId>
	<version>1.2.1</version>
	<executions>
		<execution>
			<phase>package</phase>
			<goals>
				<goal>shade</goal>
			</goals>
			<configuration>
				<transformers>
					<transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
						<mainClass>com.huawei.myapp.helloworld.HelloWorld</mainClass>
					</transformer>
				</transformers>
			</configuration>
		</execution>
	</executions>
</plugin>
http://www.cnblogs.com/LeoBoy/p/6022402.html
http://www.cnblogs.com/tonychai/p/4538683.html
http://www.cnblogs.com/hafiz/p/5360195.html
直接搭建项目骨架
mvn archetype:generate
项目兼容eclipse
mvn eclipse:eclipse 

groupId:定义当前maven项目隶属的实际项目
artifactId:定义当前的maven项目
version:当前的版本 SNAPSHOT(快照)
packaging:maven项目的打包方式
classifier:定义构建输出的附属构件（sources,javadoc）
