# pandas_tricks

0 数据读取：
	0 datatime 处理方法
	1 useCols 节省内存
	2 skip rows 抽样
		【1】
		df = pd.read_csv(
         		filename,
         		header=0,
         		skiprows=lambda i: i>0 and random.random() > p
		)
		【2】

		import pandas as pd
		import numpy as np

		filename = 'hugedatafile.csv'
		nlinesfile = 10000000
		nlinesrandomsample = 10000
		lines2skip = np.random.choice(np.arange(1,nlinesfile+1), (nlinesfile-nlinesrandomsample), replace=False)
		df = pd.read_csv(filename, skiprows=lines2skip)

	2 exec+ groupby
	3 分层抽样

1 groupby 的使用：
	1 用于去重（一维使用value_counts()）
	2 用于拆分数据
	3 搭配apply处理复杂数据

2 transform 的使用：分组标准化处理

3 map,apply,applymap
	map 一个dict，map一个匿名函数

3 multiIndex + stack + shift 抽取时间滞后项

4 loc 和 iloc的定位和赋值

5 str 函数的使用技巧

6 时间类型数据的读入与处理

7 query 查询

8 nlargest 函数的使用

9 rename 函数

10 reindex 的使用

11 str -> timestamp 方法

12 where

13 to_pickle 加速存储
14 rolling , rolling_apply , expanding 纵向处理，shift拯救世界
