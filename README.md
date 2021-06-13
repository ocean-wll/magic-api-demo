# magic-api-demo

magic-api 项目demo

magic-api github地址：https://github.com/ssssssss-team/magic-api
类似项目还有 https://github.com/alenfive/rocket-api

magic-api是一个基于Java的接口快速开发框架，编写接口将通过magic-api提供的UI界面完成，自动映射为HTTP接口，无需定义Controller、Service、Dao、Mapper、XML、VO等Java对象。

但性能方面会有一些问题。

```sql
CREATE TABLE `magic_api_file`
(
    `id`           bigint(255) NOT NULL AUTO_INCREMENT,
    `file_path`    varchar(255) DEFAULT NULL,
    `file_content` text,
    PRIMARY KEY (`id`)
);

CREATE TABLE `pms_brand`
(
    `id`                    bigint(20) NOT NULL AUTO_INCREMENT,
    `big_pic`               varchar(255) DEFAULT NULL,
    `brand_story`           varchar(255) DEFAULT NULL,
    `factory_status`        bit(1)       DEFAULT NULL,
    `first_letter`          varchar(255) DEFAULT NULL,
    `logo`                  varchar(255) DEFAULT NULL,
    `name`                  varchar(255) DEFAULT NULL,
    `product_comment_count` int(11) DEFAULT NULL,
    `product_count`         int(11) DEFAULT NULL,
    `show_status`           bit(1)       DEFAULT NULL,
    `sort`                  int(11) DEFAULT NULL,
    PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8mb4;
```

新增语句
```java
return db.table('pms_brand').insert(body);
```

根据id查询语句
```java
return db.table('pms_brand')
    .where()
    .eq('id',path.id)
    .selectOne();
```