# orm
orm by go

### ORM框架的需求
#### 对象到表结构映射
1. 创建表
`orm.CreateTable(&User{})`
2. 保存数据到表中
`orm.Save(&User{"Tom", 18})`
3. 查询数据到切片
`orm.Find(&users)`

##### 以上这些功能都需要能够支持所有对象和所有类型 
如何解决：使用反射
- `reflect.ValueOf()` 获取指针对应的反射值。
- `reflect.Indirect()` 获取指针指向的对象的反射值。
- `(reflect.Type).Name()` 返回类名(字符串)。
- `(reflect.Type).Field(i)` 获取第 i 个成员变量。

#### 多数据库适配
支持mysql，sqlite，PostgreSQL
#### 数据表结构自动更新，数据库自动迁移
1. 数据表创建
2. 数据表删除
3. 数据表迁移
#### 钩子
1. 在某种事件发生时触发钩子
#### 事务
数据库事务
