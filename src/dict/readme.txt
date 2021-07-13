文件说明：

1、base_dic_full.dic
hash索引 -- 字典带有词频和词性标志。

2、words_addons.dic
s 开头的表示停止词 u 后缀词（地名后缀、数学单位等） n 前导词（姓、汉字数词等） a 后导词(地区,部门等)

3、 not-build/base_dic_full.txt
没编译过的词典源码

4、重新编译词典的方法：

<?php

header('Content-Type: text/html; charset=utf-8');

require_once('phpanalysis.class.php');

$pa = new PhpAnalysis('utf-8', 'utf-8', false);
$pa->MakeDict( sourcefile,  16 , 'dict/base_dic_full.dic');

echo "OK";

?>
5、词性
n	普通名词	f	方位名词	s	处所名词	t	时间名词
nr	人名	ns	地名	nt	机构团体名	nw	作品名
nz	其他专名	v	普通动词	vd	动副词	vn	名动词
a	形容词	ad	副形词	an	名形词	d	副词
m	数量词	q	量词	r	代词	p	介词
c	连词	u	助词	xc	其他虚词	w	标点符号
专名识别缩略词含义
PER	人名	LOC	地名	ORG	机构名	TIME	时间