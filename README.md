# 🔥 Fire Intelligence Dashboard (Power BI)

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=24&duration=3000&color=F75C7E&center=true&vCenter=true&width=700&lines=Satellite+Fire+Analytics+with+Power+BI;DAX+%7C+Geospatial+Insights+%7C+Interactive+Dashboard" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Power%20BI-yellow?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Analytics-DAX-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Data-Geospatial-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />
</p>

---

## 📌 Project Overview

This project focuses on building an **interactive Power BI dashboard** to analyze **satellite-detected fire incidents** using VIIRS data.  
The dashboard helps identify **high-intensity fire zones**, **landcover patterns**, and **fire anomalies** using advanced analytics.

✨ Designed to reduce manual monitoring and enable **data-driven risk assessment**.

---

## 🎯 Key Objectives

- Identify **high-risk fire regions** using intensity-based analytics  
- Detect **fire anomalies** using statistical measures  
- Enable **fast, interactive exploration** through dynamic visuals  
- Reduce **manual data analysis effort** using automated insights  

---

## 🚀 Features

✔ Interactive KPIs and slicers  
✔ Narrative maps for spatial analysis  
✔ Advanced DAX calculations  
✔ Automated ranking of fire-prone zones  
✔ Clean, analytics-ready data model  

---

## 🧠 DAX Highlights

```DAX
Fire_ZScore = 
VAR MeanFRP =
    CALCULATE ( AVERAGE ( 'fires_viirs_24_25'[frp] ), ALL ( 'fires_viirs_24_25' ) )
VAR StdFRP =
    CALCULATE ( STDEV.P ( 'fires_viirs_24_25'[frp] ), ALL ( 'fires_viirs_24_25' ) )
RETURN
DIVIDE ( 'fires_viirs_24_25'[frp] - MeanFRP, StdFRP )
