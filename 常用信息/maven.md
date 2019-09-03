## mavne相关
- maven打包把resource目录文件放入jar中
````
<build>
    <resources>
        <resource>
            <directory>src/main/resources</directory>
        </resource>
    </resources>
</build>
````
- maven更新版本号 命令
````
mvn versions:set -DgenerateBackupPoms=false
mvn release:update-versions -DdevelopmentVersion={version}
````
- maven 解决冲突
````
mvn dependency:list 列出当前已解析依赖
mvn dependency:tree 列出依赖树
mvn dependency:analyze 分析当前项目的依赖
mvn -X compile dependency:tree -Dverbose >d:\\aa.log     搜索 omitted for conflict with
````
- maven 跳过test命令
````
mvn clean package -Dmaven.test.skip=true
````
多少岁