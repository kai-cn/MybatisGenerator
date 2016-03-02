# MybatisGenerator

## generatorConfig.xml

Change /Users/TimChen with your location
Change BaiwangTradeshift with your project folder

## ***Mapper.xml

1. replace `jdbcType="OTHER"` with `typeHandler="UUIDTypeHandler"`
2. replace `java.lang.Object` with `UUID`
3. replace `jdbcType=OTHER` with `javaType=UUID,jdbcType=OTHER,typeHandler=UUIDTypeHandler`


## ***Mapper.java

1. Replace `Object` into `UUID` if primary key is UUID type
2. add `@Param("id")` if parameter is UUID.  like
    `int deleteByPrimaryKey(@Param("id") UUID id);`
