**一条神奇的sql** <br> 
        个人有一个习惯，喜欢在查询的时候把sql也打印出来去数据库执行一下，看是否预期一致。

本次问题环境：
 mysql5.7 php7.3.4nts thinkphp5.1 redis5.0.5
    
出现的问题现象：
    
可还原数据支持

CREATE TABLE `xn_my_enum` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT COMMENT 'ID',
  `username` varchar(30) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '' COMMENT '名字',
  `type` enum('2','3','9','6') COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '2' COMMENT 'type',
  `createtime` int(10) unsigned DEFAULT '0' COMMENT '时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci COMMENT='神奇的sql测试表';

SELECT * FROM `xn_my_enum` WHERE  `type` IN (1,2);

INSERT into `xn_my_enum`(username,type) VALUES('VBA','2'),('VBA333','3'),('VBA6','6'),('VBA9','9');

解决问题的过程

解决方案

总结||大家的一些唠叨