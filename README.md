# MybatisGenerator

## generatorConfig.xml

1. Change `/Users/TimChen` with your location
2. Change `BaiwangTradeshift` with your project folder
3. Add columOverride in the table section to handle the UUID. sample as below:
   
<table tableName="temporary_access_control" domainObjectName="TemporaryAccessControl"
       enableCountByExample="false" enableUpdateByExample="false"
       enableDeleteByExample="false" enableSelectByExample="false"
       selectByExampleQueryId="false" >
    <columnOverride column="tenant_id" javaType="java.util.UUID" typeHandler="UUIDTypeHandler" />
    <columnOverride column="token_key" javaType="java.util.UUID" typeHandler="UUIDTypeHandler" />
    <columnOverride column="expire_time" javaType="java.sql.Timestamp"/>
</table>

## **Mapper.java
1. add `@Param("id")` if parameter is UUID.  like
    `int deleteByPrimaryKey(@Param("id") UUID id);`

## Entity
remove  `createTime` `updateTime`  `createBy` `updateBy`
instead extends BaseEntity

