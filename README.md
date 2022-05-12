# dpcq_new_word_find
斗破苍穹小说的新词发现。

# 步骤

- 直接拷贝项目：[Rayarrow/New-Word-Discovery: 新词发现 基于词频、凝聚系数和左右邻接信息熵 (github.com)](https://github.com/Rayarrow/New-Word-Discovery)

- 在命令行输入：

	```python
	python run_discover.py "data/斗破苍穹/斗破苍穹.txt" "reports" --latin 50 0 0 0 --bigram 20 80 0 1.5 --unigram_2 20 40 0 1 --unigram_3 20 41 0 1 --iteration 2 --verbose 2
	```

	其实这里指不指定输入的txt都行，因为在run_discover.py里面已经写死了。

# 结果

以下显示部分的结果：

两个字的：

```
20.0 # 40.0 # 0.0 # 1.0 # 2	tf	agg_coef	max_entropy	min_entropy	left_entropy	right_entropy
萧炎	44477	56.90328	8.34041	4.69988	4.69988	8.34041
令得	2154	66.94484	6.15161	4.03623	4.03623	6.15161
异火	2153	57.93440	6.18367	5.47363	6.18367	5.47363
听得	1970	60.18430	6.24338	2.21533	2.21533	6.24338
紫研	1419	701.13603	6.79713	4.91935	4.91935	6.79713
纳兰	1284	741.42784	4.58498	1.47031	4.58498	1.47031
韩枫	953	1315.95708	7.18807	5.08946	5.08946	7.18807
魂殿	897	103.97270	5.73556	5.54795	5.73556	5.54795
斗皇	892	94.79750	5.45420	3.16312	5.45420	3.16312
苏千	842	558.08755	6.47207	4.06888	4.06888	6.47207
药鼎	704	90.21435	5.00712	3.87745	5.00712	3.87745
斗尊	696	43.95327	5.33022	3.23932	5.33022	3.23932
```

三个字的：

```
20.0 # 41.0 # 0.0 # 1.0 # 2	tf	agg_coef	max_entropy	min_entropy	left_entropy	right_entropy
小医仙	1346	173967.58092	6.96497	3.31052	3.31052	6.96497
云岚宗	1340	236637.51952	6.26222	6.15050	6.26222	6.15050
妖凰族	361	132785.11397	4.81515	1.47622	1.47622	4.81515
大斗师	325	2382.22258	5.67791	4.85402	5.67791	4.85402
焚炎谷	260	27615.13220	5.34474	4.38391	5.34474	4.38391
斗之气	256	301.44918	4.83565	4.00525	4.83565	4.00525
莫天行	241	23245.22139	6.26152	4.24955	4.24955	6.26152
乌坦城	219	5169614.68463	4.97398	4.61440	4.97398	4.61440
凤清儿	215	299254.34290	5.53344	4.35765	4.35765	5.53344
自萧炎	141	53.93642	4.29877	3.81674	4.29877	3.81674
慕青鸾	134	1772983.90008	5.51582	3.17790	3.17790	5.51582
天冥宗	132	17017.90161	4.85124	4.71653	4.85124	4.71653
东龙岛	130	262964.66995	5.09240	4.50574	5.09240	4.50574
```

总体的：

```
20.0 # 80.0 # 0.0 # 1.5 # 2	tf	agg_coef	max_entropy	min_entropy	left_entropy	right_entropy
望着	6429	88.62492	5.76639	3.29693	3.29693	5.76639
让得	3282	158.42311	6.05628	5.00367	5.00367	6.05628
薰儿	2655	1075.93292	7.36769	4.51719	4.51719	7.36769
等人	2225	115.64243	6.58301	5.25368	5.25368	6.58301
炼药师	2011	1434.44947	5.70378	5.21238	5.70378	5.21238
盯着	1620	95.54733	5.73287	3.40279	3.40279	5.73287
脸庞上	1601	139.93660	4.99613	4.53856	4.99613	4.53856
天空上	1383	151.95689	4.15316	3.98112	4.15316	3.98112
瞧得	1221	221.02698	6.17956	3.80053	3.80053	6.17956
不知道	1217	136.84007	7.17930	4.82474	4.82474	7.17930
今曰	1162	789.58121	6.29225	3.81237	3.81237	6.29225
略微有些	977	170.57313	7.90198	5.99135	5.99135	7.90198
海波东	964	2441.88382	6.54657	4.26189	4.26189	6.54657
不可能	948	262.75909	6.60016	4.68069	4.68069	6.60016
曰后	927	136.89882	6.12798	3.93988	3.93988	6.12798
灵魂力量	927	351.64736	5.96322	4.66934	4.66934	5.96322
加玛帝国	919	1892.04722	5.86381	5.65998	5.65998	5.86381
纳兰嫣然	881	2016.11251	7.21520	4.36805	4.36805	7.21520
并没有	868	197.49401	7.48791	5.03779	5.03779	7.48791
感觉到	865	243.88611	5.36146	4.61834	4.61834	5.36146
章 	846	1917.97647	9.09531	6.75345	6.75345	9.09531
小医仙	844	1443.15544	6.06024	3.63423	3.63423	6.06024\
```

# 补充

Q：如何训练自己的数据集？

A：可以借鉴discover_utils.py下的get_dpcq()函数返回的documents

Q：为什么需要进行迭代？

A：每次迭代会将新发现的词加入到原始的词典中，这样进行下一次迭代的时候就可以根据这些词再发现新词。

Q：如何进行新词发现的？

A：基于凝固度、频率、熵。具体可以搜索相关的介绍。

Q：只能发现两个字和三个字的词语吗？

A：可以根据自己的情况进行修改。

# 感谢

这里只是将[Rayarrow/New-Word-Discovery: 新词发现 基于词频、凝聚系数和左右邻接信息熵 (github.com)](https://github.com/Rayarrow/New-Word-Discovery)的代码clone下来后试了一下。并理解下新词发现，感谢他们的代码。



