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
<tr><td>区域</td><td>日期</td><td>判据</td><td>当前阶段</td></tr>
<tr><td>中国-湖北</td><td>20200315</td><td>现有在疗数5日均增长率测算得到10.5549日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中-月内清零</font></td></tr>
<tr><td>欧洲</td><td>20200315</td><td>确诊数增长率24.7177>10% 且 在疗数增长率23.376>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td></tr>
<tr><td>德国</td><td>20200315</td><td>确诊数增长率56.1116>10% 且 在疗数增长率56.4276>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td></tr>
<tr><td>伊朗</td><td>20200315</td><td>无悲观指标</td><td bgcolor="#00aa88"><font color="white">控制中</font></td></tr>
<tr><td>意大利</td><td>20200315</td><td>确诊数增长率20.4417>10% 且 在疗数增长率19.445>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td></tr>
<tr><td>韩国</td><td>20200315</td><td>无悲观指标</td><td bgcolor="#00aa88"><font color="white">控制中</font></td></tr>
<tr><td>西班牙</td><td>20200315</td><td>确诊数增长率22.1904>10% 且 在疗数增长率14.3002>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td></tr>
<tr><td>法国</td><td>20200315</td><td>确诊数增长率22.9172>10% 且 在疗数增长率22.493>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td></tr>

</table>