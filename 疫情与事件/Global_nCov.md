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
<tr><td>中国-湖北</td><td>2</td><td>20200328</td><td>在近14日内，过半日期0增长</td><td bgcolor="#00aa88"><font color="white">低风险</font></td><td>67801</td><td>91.5886%</td><td>4.6858%</td><td>0%</td><td>-12.7461%</td></tr>
<tr><td>美国</td><td>1</td><td>20200328</td><td>确诊数增长率22.133>10% 且 在疗数增长率21.9525>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>104839</td><td>0.85274%</td><td>1.632%</td><td>22.133%</td><td>21.9525%</td></tr>
<tr><td>日本</td><td>3</td><td>20200328</td><td>有确诊病例，但情况轻微</td><td>初始</td><td>1617</td><td>23.0056%</td><td>3.3395%</td><td>7.5848%</td><td>8.9661%</td></tr>
<tr><td>欧洲</td><td>-</td><td>20200328</td><td>确诊数增长率13.1448>10% 且 在疗数增长率9.4044>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>329583</td><td>12.4679%</td><td>6.0522%</td><td>13.1448%</td><td>9.4044%</td></tr>
<tr><td>德国</td><td>4</td><td>20200328</td><td>确诊数增长率13.4873>10% 且 在疗数增长率12.1086>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>49039</td><td>14.1357%</td><td>0.65866%</td><td>13.4873%</td><td>12.1086%</td></tr>
<tr><td>法国</td><td>6</td><td>20200328</td><td>确诊数增长率13.0647>10% 且 在疗数增长率12.2518>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>32964</td><td>17.2916%</td><td>6.0521%</td><td>13.0647%</td><td>12.2518%</td></tr>
<tr><td>英国</td><td>7</td><td>20200328</td><td>确诊数增长率45.1665>10% 且 在疗数增长率44.0908>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>17089</td><td>0.78998%</td><td>5.9629%</td><td>45.1665%</td><td>44.0908%</td></tr>
<tr><td>巴西</td><td>8</td><td>20200328</td><td>确诊数增长率17.2213>10% 且 在疗数增长率17.16>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>3417</td><td>0%</td><td>2.6924%</td><td>17.2213%</td><td>17.16%</td></tr>
<tr><td>意大利</td><td>9</td><td>20200328</td><td>无悲观指标现有在疗数5日均增长率测算得到-13.5758日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>87275</td><td>12.5465%</td><td>10.6078%</td><td>7.5756%</td><td>7.2163%</td></tr>
<tr><td>韩国</td><td>11</td><td>20200328</td><td>现有在疗数5日均增长率测算得到22.4313日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中-月内清零</font></td><td>9478</td><td>50.7597%</td><td>1.5193%</td><td>1.5645%</td><td>-3.0439%</td></tr>
<tr><td>澳大利亚</td><td>13</td><td>20200328</td><td>确诊数增长率21.7755>10% 且 在疗数增长率22.705>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>3635</td><td>3.2737%</td><td>0.38514%</td><td>21.7755%</td><td>22.705%</td></tr>
<tr><td>西班牙</td><td>14</td><td>20200328</td><td>确诊数增长率12.7835>10% 且 在疗数增长率3.9992>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>72248</td><td>17.0039%</td><td>7.8757%</td><td>12.7835%</td><td>3.9992%</td></tr>
<tr><td>荷兰</td><td>18</td><td>20200328</td><td>无悲观指标现有在疗数5日均增长率测算得到-10.9349日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>8603</td><td>29.0596%</td><td>6.3466%</td><td>0%</td><td>-31.0289%</td></tr>
<tr><td>瑞士</td><td>20</td><td>20200328</td><td>无悲观指标现有在疗数5日均增长率测算得到-12.9713日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>13213</td><td>11.5795%</td><td>1.7786%</td><td>11.8703%</td><td>-1.7086%</td></tr>
<tr><td>伊朗</td><td>29</td><td>20200328</td><td>无悲观指标现有在疗数5日均增长率测算得到-10.2316日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>35408</td><td>32.9841%</td><td>7.1086%</td><td>9.5138%</td><td>12.7039%</td></tr>



</table>