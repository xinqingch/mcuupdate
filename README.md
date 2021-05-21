# mcuupdate
一个通过远程安卓APP更新固件的程序

# 服务端
SQL表
<pre>
CREATE TABLE `scm_ver` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `type` tinyint(1) DEFAULT '1' COMMENT '升级类型：1主板，2驱动，3其它',
  `vernum` smallint(4) NOT NULL DEFAULT '1' COMMENT '版本数值',
  `vername` varchar(10) DEFAULT NULL COMMENT '版本号',
  `filename` varchar(100) DEFAULT NULL COMMENT '文件名',
  `content` text COMMENT '更新说明',
  `detail` longtext NOT NULL COMMENT '16进制更新数据',
  `state` tinyint(1) DEFAULT '0' COMMENT '发布状态0未发布，1发布',
  `md5` varchar(32) NOT NULL COMMENT 'MD5',
  `inputtime` int(11) DEFAULT NULL COMMENT '发布时间',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8 COMMENT='固体版本';
</pre>

接口

