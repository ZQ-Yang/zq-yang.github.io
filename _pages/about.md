---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

I am a Ph.D. candidate at the Urban Mobility Institute, Tongji University, Shanghai, China. I received my bachelor's degree from Southwest Jiaotong University in 2020.

My research interests include travel behavior analysis and modeling, the relationship between travel and land use, shared micromobility, and transport equity.

I am currently a visiting PhD student at Ghent University.


# 🔥 News
- *2024.11*: &nbsp;🎉🎉 I am awarded the Silver Award at the **[2024 THNS Forum](https://thns.tongji.edu.cn/2024Awards/list.htm)**.
- *2024.10*: &nbsp;🎉🎉 Two papers are accepted by *TRB2025*.
- *2024.07*: &nbsp;🎉🎉 I receive funding support from the **China Scholarship Council (CSC)**.
- *2024.07*: &nbsp;🎉🎉 One paper is accepted by *Sustainable Cities and Society*.

# 📝 Publications 

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">2024</div><img src='images/车1.jpg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Evaluating temporal variations in access to multi-tier hospitals using personal vehicles and public transit: Implications for healthcare equity](https://www.sciencedirect.com/science/article/pii/S2210670724005122)


**Ziqi Yang**, Yuntao Guo, Xi Feng, Yaocheng Zhou, Pengfei Zhou, Xinghua Li, Xinwu Qian
- *Sustainable Cities and Society* 
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">2024</div><img src='images/4.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Factoring in temporal variations of public transit-based healthcare accessibility and equity](https://www.sciencedirect.com/science/article/pii/S2046043024000017)

Xinghua Li, **Ziqi Yang**, Yuntao Guo, Wei Xu, Xinwu Qian
- *International Journal of Transportation Science and Technology* 
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">2023</div><img src='images/fig1.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Investigating the impacts of property walking accessibility on housing affordability and equity: Evidence from Shanghai, China](https://ascelibrary.org/doi/abs/10.1061/JUPDDM.UPENG-4197)

Xinghua Li, **Ziqi Yang**, Xinwu Qian, Yuntao Guo, Chao Yang
- *Journal of Urban Planning and Development* 
</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge">2023</div><img src='images/Coefficient distribution.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Understanding active transportation accessibility's impacts on polycentric and monocentric cities' housing price](https://www.sciencedirect.com/science/article/pii/S0739885923000227)


**Ziqi Yang**, Xinghua Li, Yuntao Guo, Xinwu Qian
- *Research in Transportation Economics* 
</div>
</div>





- Xinghua Li, **Ziqi Yang**, Yuntao Guo, Zhenghan Zhang, Lu Teng, Yue Wang, Examining spatial variations in built environment impact on the bike-sharing usage among older adults. *TRB2025*.
- Maozheng Zhou, Yuntao Guo, **Ziqi Yang**, Lu Teng, Xinghua Li, Analyzing accessibility disparities in shared bike usage across gender and age subgroups: Implications for equity from large-scale trip data. *TRB2025*.
- **Ziqi Yang**, Xinghua Li, Yuntao Guo, Xinwu Qian, Wei Wang, Impacts of property walking accessibility on second-hand property price and rent: Evidence from Shanghai, China. *TRB2022*.




# 🎖 Honors and Awards
- *2024.11* Jingchuan Scholarship 京川奖学金
- *2024.07* China Scholarship Council Scholarship
- *2023.07* Green Seedling Fund 绿苗计划

# 📖 Educations
- *2024.09 – present*, Visiting Student, **Ghent University**, Ghent, Belgium
- *2020.09 – present*, Ph.D. Candidate, **Tongji University**, Shanghai, China
- *2016.09 – 2020.06*, Bachelor of Engineering, **Southwest Jiaotong University**, Chengdu, China


# 💬 Invited Talks
- *2025.03*, City+Talk series 4, Online. 
- *2024.10*, 2024 THNS Forum, Paris, French.

# 💻 Internships
None




<!-- 引入 Leaflet -->
<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<!-- 引入 Leaflet Country Layers -->
<script src="https://unpkg.com/leaflet-countrylayers/dist/leaflet-countrylayers.min.js"></script>

# 🌎 Countries

<div id="world-map" style="height: 400px; margin-bottom: 30px; border-radius: 10px;"></div>

<script>
// 初始化地图
var map = L.map('world-map').setView([20, 0], 2);

// 加载OpenStreetMap底图
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '© OpenStreetMap contributors'
}).addTo(map);

// 创建国家图层
var countries = new L.CountryLayers({
  defaultStyle: {
    color: '#999999',
    weight: 0.5,
    fillColor: '#dddddd',
    fillOpacity: 0.2
  },
  highlightStyle: {
    color: '#3388ff',
    weight: 1,
    fillColor: '#66B2FF',
    fillOpacity: 0.7
  }
}).addTo(map);

// 你去过的国家ISO3代码
var visitedCountries = ['CHN', 'BEL'];

// 遍历国家，高亮你去过的
countries.eachLayer(function(layer) {
  var iso_a3 = layer.feature.properties.ISO_A3;
  if (visitedCountries.includes(iso_a3)) {
    layer.setStyle({
      color: '#3388ff',
      weight: 1,
      fillColor: '#3388ff',
      fillOpacity: 0.7
    });
    layer.bindPopup(layer.feature.properties.ADMIN); // 点击弹出国家名
  }
});
</script>





