# 全球疫情概要

正计划做关于全球疫情的分析(其实早该做了-_-个人需要)

分析思路跟<a href="./SARS疫情与武汉新冠疫情.md">《SARS疫情与武汉新冠疫情》</a>其实大同小异，
<br/>

这次打算分阶段实施，因为国家/地区太多了，需要加入自动化的手段增加效率。

## 输入输出的定义
<br/>
### 输入数据
累计确诊、在疗数、死亡数、治愈数、密接数据（如果可获得）、人口密度（个人觉得可能不会很重要，疫情发展的过程也受到一个区域的文化经济等各种复杂因素影响，所分析的趋势是一种综合影响的结果；暂时不挖因，只分析果）



### 输出报告
各区域曲线聚合（平移），各区域的当前阶段

### 我对阶段的定义（试用版，比较粗糙）
<table align=center>
<tr><td>阶段</td><td>状态定义</td></tr>
<tr><td>未爆发</td><td>该区域无确诊病例</td></tr>
<tr><td>初始</td><td>有确诊病例，但情况轻微</td></tr>
<tr><td>初始-预失控</td><td>累计确诊未达到3500（+-5%），且（近五日均增长率达30%（+-5） OR 死亡率超6%）</td></tr>
<tr><td>失控中</td><td>累计确诊达到3500，且（增长率未降到10%以下 AND 在疗数增长率>0%）</td></tr>
<tr><td>控制中</td><td>在疗数增长率<0%</td></tr>
<tr><td>控制中-月内清零</td><td>现有在疗数5日均增长率测算得到一月内在疗数可清零</td></tr>
<tr><td>清库存</td><td>在疗数占总确诊数10%以内</td></tr>
<tr><td>低风险</td><td>在近14日内的统计窗口中，过半日期0增长</td></tr>
<tr><td>无风险</td><td>近28日内0增长</td></tr>
</table>

### 当前各区域所处阶段
<table align=center>
<tr><td>区域 Area</td><td>GDP 排名/Rank</td><td>日期 Date</td><td>判据 Judgement</td><td>当前阶段 Current Phase</td><td>确诊数</td><td>治愈率 Cured /%</td><td>死亡率</td><td>确诊增长率</td><td>在疗增长率</td></tr>
<tr><td>中国-湖北</td><td>2</td><td>20200330</td><td>在近14日内，过半日期0增长</td><td bgcolor="#00aa88"><font color="white">低风险</font></td><td>67801</td><td>92.7553%</td><td>4.699%</td><td>0%</td><td>-15.7638%</td></tr>
<tr><td>美国</td><td>1</td><td>20200330</td><td>确诊数增长率14.7691>10% 且 在疗数增长率13.2095>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>143101</td><td>3.3997%</td><td>1.7589%</td><td>14.7691%</td><td>13.2095%</td></tr>
<tr><td>日本</td><td>3</td><td>20200330</td><td>有确诊病例，但情况轻微</td><td>初始</td><td>1944</td><td>20.7819%</td><td>2.9835%</td><td>8.06%</td><td>10.597%</td></tr>
<tr><td>欧洲</td><td>-</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-9.885日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>388115</td><td>13.0562%</td><td>6.3989%</td><td>5.528%</td><td>4.0144%</td></tr>
<tr><td>德国</td><td>4</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-9.1724日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>58101</td><td>14.597%</td><td>0.81582%</td><td>0%</td><td>0%</td></tr>
<tr><td>法国</td><td>6</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-8.9495日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>40174</td><td>17.7528%</td><td>6.4868%</td><td>6.9168%</td><td>2.96%</td></tr>
<tr><td>英国</td><td>7</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-4.9683日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>19522</td><td>0.69153%</td><td>6.2903%</td><td>0%</td><td>0%</td></tr>
<tr><td>巴西</td><td>8</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-7.1854日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>4256</td><td>0%</td><td>3.1955%</td><td>9.0164%</td><td>8.0797%</td></tr>
<tr><td>意大利</td><td>9</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-15.4608日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>97689</td><td>13.3382%</td><td>11.034%</td><td>4.9844%</td><td>4.5807%</td></tr>
<tr><td>韩国</td><td>11</td><td>20200330</td><td>现有在疗数5日均增长率测算得到24.2362日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中-月内清零</font></td><td>9661</td><td>54.1145%</td><td>1.6354%</td><td>0.81394%</td><td>-2.7967%</td></tr>
<tr><td>澳大利亚</td><td>13</td><td>20200330</td><td>确诊数增长率11.4466>10% 且 在疗数增长率11.8672>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>4245</td><td>2.8033%</td><td>0.37691%</td><td>11.4466%</td><td>11.8672%</td></tr>
<tr><td>西班牙</td><td>14</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-10.5957日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>85195</td><td>17.2651%</td><td>8.6155%</td><td>8.1196%</td><td>5.2714%</td></tr>
<tr><td>荷兰</td><td>18</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-8.9094日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>11750</td><td>25.1404%</td><td>7.3532%</td><td>8.1355%</td><td>11.0769%</td></tr>
<tr><td>瑞士</td><td>20</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-12.5222日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>14799</td><td>12.3184%</td><td>2.0272%</td><td>3.2296%</td><td>1.012%</td></tr>
<tr><td>伊朗</td><td>29</td><td>20200330</td><td>无悲观指标现有在疗数5日均增长率测算得到-8.6399日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>41495</td><td>29.8614%</td><td>6.3622%</td><td>8.3166%</td><td>13.6867%</td></tr>



</table>