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
<tr><td>中国-湖北</td><td>2</td><td>20200402</td><td>在近14日内，过半日期0增长</td><td bgcolor="#00aa88"><font color="white">低风险</font></td><td>67802</td><td>93.6123%</td><td>4.7181%</td><td>0%</td><td>-11.7693%</td></tr>
<tr><td>美国</td><td>1</td><td>20200402</td><td>确诊数增长率14.285>10% 且 在疗数增长率13.7303>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>216722</td><td>4.0014%</td><td>2.3703%</td><td>14.285%</td><td>13.7303%</td></tr>
<tr><td>日本</td><td>3</td><td>20200402</td><td>有确诊病例，但情况轻微</td><td>初始</td><td>2526</td><td>15.9937%</td><td>2.8108%</td><td>1.4458%</td><td>1.6353%</td></tr>
<tr><td>欧洲</td><td>-</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-12.5591日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>497335</td><td>13.9498%</td><td>7.0512%</td><td>8.2106%</td><td>6.0197%</td></tr>
<tr><td>德国</td><td>4</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-10.9805日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>73522</td><td>11.5353%</td><td>1.186%</td><td>9.1381%</td><td>10.3451%</td></tr>
<tr><td>法国</td><td>6</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-8.9417日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>56989</td><td>19.1879%</td><td>7.075%</td><td>9.3251%</td><td>7.3057%</td></tr>
<tr><td>英国</td><td>7</td><td>20200402</td><td>确诊数增长率14.3991>10% 且 在疗数增长率13.6177>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>33718</td><td>0.40038%</td><td>8.663%</td><td>14.3991%</td><td>13.6177%</td></tr>
<tr><td>巴西</td><td>8</td><td>20200402</td><td>确诊数增长率19.5732>10% 且 在疗数增长率19.5613>0%</td><td bgcolor="#ff0055"><font color="white">失控中</font></td><td>6836</td><td>0%</td><td>3.5255%</td><td>19.5732%</td><td>19.5613%</td></tr>
<tr><td>意大利</td><td>9</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-26.6243日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>110574</td><td>15.236%</td><td>11.897%</td><td>4.5202%</td><td>3.7831%</td></tr>
<tr><td>韩国</td><td>11</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到78.844日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>9976</td><td>55.8039%</td><td>1.6941%</td><td>0.90017%</td><td>2.0457%</td></tr>
<tr><td>澳大利亚</td><td>13</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-13.5685日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>5133</td><td>2.3183%</td><td>0.44808%</td><td>5.6173%</td><td>5.7191%</td></tr>
<tr><td>西班牙</td><td>14</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-13.2852日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>110238</td><td>20.5437%</td><td>9.074%</td><td>7.9326%</td><td>-1.0029%</td></tr>
<tr><td>荷兰</td><td>18</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-7.3548日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>14697</td><td>20.0993%</td><td>9.1107%</td><td>7.955%</td><td>9.6659%</td></tr>
<tr><td>瑞士</td><td>20</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-14.3025日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>18267</td><td>9.9797%</td><td>2.3649%</td><td>6.5815%</td><td>7.1897%</td></tr>
<tr><td>伊朗</td><td>29</td><td>20200402</td><td>无悲观指标现有在疗数5日均增长率测算得到-13.0337日内在疗数可清零</td><td bgcolor="#00aa88"><font color="white">控制中</font></td><td>50468</td><td>33.1121%</td><td>6.2614%</td><td>6.0408%</td><td>5.2022%</td></tr>



</table>