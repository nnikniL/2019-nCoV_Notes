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
<tr><td>中国-湖北</td><td>2</td><td>20200329</td><td>在近14日内，过半日期0增长</td><td bgcolor="#00aa88"><font color="white">低风险</font></td><td>67801</td><td>92.2848%</td><td>4.6931%</td><td>0%</td><td>-18.8836%</td></tr>
<tr><td>美国</td><td>1</td><td>20200329</td><td>确诊数增长率18.9309>10% 且 在疗数增长率17.2633>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>124686</td><td>2.0949%</td><td>1.7572%</td><td>18.9309%</td><td>17.2633%</td></tr>
<tr><td>日本</td><td>3</td><td>20200329</td><td>有确诊病例，但情况轻微</td><td>初始</td><td>1799</td><td>22.4569%</td><td>3.0573%</td><td>11.2554%</td><td>12.5105%</td></tr>
<tr><td>欧洲</td><td>-</td><td>20200329</td><td>确诊数增长率11.5907>10% 且 在疗数增长率11.9154>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>367784</td><td>12.1204%</td><td>6.1626%</td><td>11.5907%</td><td>11.9154%</td></tr>
<tr><td>德国</td><td>4</td><td>20200329</td><td>确诊数增长率18.4792>10% 且 在疗数增长率17.6192>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>58101</td><td>14.597%</td><td>0.81582%</td><td>18.4792%</td><td>17.6192%</td></tr>
<tr><td>法国</td><td>6</td><td>20200329</td><td>确诊数增长率13.988>10% 且 在疗数增长率16.9852>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>37575</td><td>15.1697%</td><td>6.1583%</td><td>13.988%</td><td>16.9852%</td></tr>
<tr><td>英国</td><td>7</td><td>20200329</td><td>确诊数增长率14.2372>10% 且 在疗数增长率13.9567>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>19522</td><td>0.69153%</td><td>6.2903%</td><td>14.2372%</td><td>13.9567%</td></tr>
<tr><td>巴西</td><td>8</td><td>20200329</td><td>确诊数增长率14.2523>10% 且 在疗数增长率14.6466>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>3904</td><td>0%</td><td>2.3566%</td><td>14.2523%</td><td>14.6466%</td></tr>
<tr><td>意大利</td><td>9</td><td>20200329</td><td>无悲观指标现有在疗数5日均增长率测算得到-14.3171日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>93051</td><td>13.3088%</td><td>10.7715%</td><td>6.6182%</td><td>5.3335%</td></tr>
<tr><td>韩国</td><td>11</td><td>20200329</td><td>现有在疗数5日均增长率测算得到23.2557日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中-月内清零</font></td><td>9583</td><td>52.5201%</td><td>1.5861%</td><td>1.1078%</td><td>-2.7637%</td></tr>
<tr><td>澳大利亚</td><td>13</td><td>20200329</td><td>无悲观指标现有在疗数5日均增长率测算得到-6.787日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>3809</td><td>3.1242%</td><td>0.42006%</td><td>4.7868%</td><td>4.9115%</td></tr>
<tr><td>西班牙</td><td>14</td><td>20200329</td><td>无悲观指标现有在疗数5日均增长率测算得到-8.2232日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>78797</td><td>15.5907%</td><td>8.2846%</td><td>9.0646%</td><td>10.5227%</td></tr>
<tr><td>荷兰</td><td>18</td><td>20200329</td><td>确诊数增长率26.3048>10% 且 在疗数增长率28.5046>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>10866</td><td>27.1857%</td><td>7.0955%</td><td>26.3048%</td><td>28.5046%</td></tr>
<tr><td>瑞士</td><td>20</td><td>20200329</td><td>无悲观指标现有在疗数5日均增长率测算得到-11.5118日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>14336</td><td>10.6724%</td><td>1.7927%</td><td>8.4992%</td><td>9.6174%</td></tr>
<tr><td>伊朗</td><td>29</td><td>20200329</td><td>无悲观指标现有在疗数5日均增长率测算得到-9.777日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>38309</td><td>32.3449%</td><td>6.8913%</td><td>8.1931%</td><td>9.7398%</td></tr>



</table>