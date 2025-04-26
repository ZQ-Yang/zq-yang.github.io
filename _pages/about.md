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

<!-- 地图容器 -->

# 🌎 Countries
<div id="map" style="height: 400px; margin-bottom: 30px; border-radius: 10px; overflow: hidden;"></div>

<script>
// 初始化地图
var map = L.map('map').setView([30, 10], 2);

// 加载底图
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '© OpenStreetMap contributors'
}).addTo(map);

// 我去过的国家（用ISO Alpha-3国家代码）
var visitedCountries = ['CHN', 'BEL'];

// 加载世界国家边界（最新标准版GeoJSON）
fetch('https://raw.githubusercontent.com/datasets/geo-countries/master/data/countries.geojson')
  .then(function(response) {
    return response.json();
  })
  .then(function(data) {
    L.geoJSON(data, {
      style: function(feature) {
        var countryCode = feature.properties.ISO_A3; // 注意这里大小写ISO_A3
        if (visitedCountries.includes(countryCode)) {
          return {
            color: "#0066FF",      // 边框蓝色
            weight: 1,
            fillColor: "#66B2FF",   // 填充浅蓝色
            fillOpacity: 0.6
          };
        } else {
          return {
            color: "#888888",      // 边框灰色
            weight: 0.5,
            fillColor: "#DDDDDD",   // 填充浅灰色
            fillOpacity: 0.3
          };
        }
      },
      onEachFeature: function(feature, layer) {
        layer.bindPopup(feature.properties.ADMIN); // 显示国家名字
      }
    }).addTo(map);
  });
</script>






