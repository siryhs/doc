### java bean之间的互转
1.简单的约定优于配置的同名属性copy
2.嵌套属性copy
3.flattern（扁平化）支持，要支持N层结构的copy到一层结构。
4.性能
####来源
https://www.iteye.com/blog/xpenxpen-1911605
https://stackoverflow.com/questions/1432764/any-tool-for-java-object-to-object-mapping

|d|描述|是否支持flattern|URL
| :------------ | :------------ | :------------ |
|Commons-BeanUtils|BeanUtils只能同类型同名属性批量copy,PropertyUtils可以用类似ognl表达式copy嵌套的属性,但这个东西的性能被吐槽不好|Y|http://commons.apache.org/proper/commons-beanutils/
|Commons-Lang|ArrayUtils也只是不同类型间的互转|N|http://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/ArrayUtils.html
|Spring framework|PropertyEditors也只是不同类型间的互转|N|
|Dozer|貌似功能比较强大，可通过xml来配置映射，但性能不行|Y|https://github.com/DozerMapper/dozer
|ModelMapper|采用约定优于配置的方式自动映射|Y|http://modelmapper.org
|MapStruct|是一个生成类型安全， 高性能且无依赖的 JavaBean 映射代码的注解处理器||https://mapstruct.org/|
|Orika|一个新秀，比Dozer性能好，可以一试，但没找到配xml的方法|Y|http://orika-mapper.github.io/orika-docs/index.html
|Selma|Compile-time code-generator for mappings||https://
|JMapper|支持annotaion描述映射|N|http://code.google.com/p/jmapper-framework/
|Transmorph|只是不同类型间的互转，和需求相去胜远|N|https://github.com/cchabanois/transmorph
|Commons-Convert|也只是不同类型间的互转,目前在apache的sandbox里|N|http://commons.apache.org/sandbox/commons-convert
|EZMorph|能同类型同名属性批量copy|N|http://sourceforge.net/projects/ezmorph/
|cglib|BeanCopier, BulkBean,BeanMap,FastClass/FastMethod 采用生成字节码的方法，性能相当的高|N|sourceforge.net/projects/cglib
|ognl|ognl表达式肯定功能强大|Y|http://commons.apache.org/proper/commons-ognl/
|mapping4java|国人造的一个轮子，性能不错|N|http://code.google.com/p/mapping4java/

