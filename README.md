# MybatisGenerator

## 1#Config the generatorConfig.xml

1. Change `/Users/TimChen` with your location
2. Change `BaiwangTradeshift` with your project folder
3. Add columOverride in the table section to handle the UUID. sample as below:
 
```xml
   <table tableName="temporary_access_control" domainObjectName="TemporaryAccessControl"
          enableCountByExample="false" enableUpdateByExample="false"
          enableDeleteByExample="false" enableSelectByExample="false"
          selectByExampleQueryId="false" >
       <columnOverride column="tenant_id" javaType="java.util.UUID" typeHandler="UUIDTypeHandler" />
       <columnOverride column="token_key" javaType="java.util.UUID" typeHandler="UUIDTypeHandler" />
       <columnOverride column="expire_time" javaType="java.sql.Timestamp"/>
   </table>
```
## 2#Run the generator command.
    `mvn mybatis-generator:generate`
## 3#Modify the generated **Mapper.java file.
1. add `@Param("id")` if parameter is UUID.  like
    `int deleteByPrimaryKey(@Param("id") UUID id);`

## 4#Modify the generated Entity file.
extends the father class: BaseEntity.
remove  `createTime` `updateTime`  `createBy` `updateBy` in the entity file.

