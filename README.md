# 🏆 Nobel Prize API Data Analysis

[![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)](https://www.r-project.org/)
[![API](https://img.shields.io/badge/API-Nobel_Prize-gold?style=for-the-badge&logo=api&logoColor=white)](https://api.nobelprize.org/)
[![tidyverse](https://img.shields.io/badge/tidyverse-1A162D?style=for-the-badge&logo=tidyverse&logoColor=white)](https://www.tidyverse.org/)

> 🌍 **Uncovering global patterns in Nobel Prize recognition through comprehensive API data analysis spanning five decades (1975-2025)**

---

## 📖 Project Overview

This project leverages the Nobel Prize API to conduct an in-depth analysis of laureate demographics, geographic distributions, institutional affiliations, and award patterns. Through strategic data extraction, transformation, and visualization, this analysis reveals compelling insights about scientific recognition, continental representation shifts, and the evolving landscape of Nobel Prize achievements.

### 🎯 Project Goals

- 🌐 Map continental shifts in Nobel Prize recognition over 50 years
- 📊 Track demographic trends including age patterns across categories
- 🤝 Analyze collaboration dynamics (individual vs. shared prizes)
- 🎓 Identify top-producing research institutions globally
- 🌟 Discover youngest laureates by geographic region
- 📈 Compare prize distribution across six Nobel categories

---

## 🛠️ Technologies & Tools

### Core Technologies
```r
library(httr)         # API requests and HTTP operations
library(jsonlite)     # JSON parsing and data extraction
library(tidyverse)    # Data manipulation and visualization
library(lubridate)    # Date/time calculations
library(ggplot2)      # Advanced data visualization
library(scales)       # Scale functions for plots
```

### Data Source
- **API**: [Nobel Prize API v2.1](https://api.nobelprize.org/)
- **Endpoint**: `/laureates` with pagination support
- **Coverage**: Complete laureate dataset (1901-2025)
- **Analysis Period**: 1975-2025 (50 years)

---

## 📂 Project Structure
```
nobel-prize-analysis/
│
├── 📄 nobel_prize_analysis.Rmd        # Main R Markdown document
├── 📊 nobel_prize_analysis.html       # Rendered HTML output
├── 📋 README.md                       # This file
│
├── 📁 visualizations/
│   ├── nobel_continental_area_chart.png
│   ├── nobel_continental_trend_lines.png
│   ├── median_age_by_category_decade.png
│   ├── nobel_prize_sharing_by_decade.png
│   ├── nobel_institutions_simple.png
│   └── nobel_categories_by_decade.png
│
└── 📁 data/
    └── nobel_laureates_raw.json       # Raw API data (if cached)
```

---

## 🔍 Research Questions

This analysis addresses six compelling questions about Nobel Prize patterns:

### 1️⃣ Geographic Distribution
**How has the distribution of Nobel Prize winners shifted across continents over the past 50 years?**

🔑 **Key Findings:**
- 📉 **Europe's Decline**: Dropped from 49.5% (1975-1984) to ~35-40% (recent decades)
- 📈 **Asia's Rise**: Increased 6-fold from 3% (1975-1984) to 18% (2015-2024)
- 🇺🇸 **North America's Stability**: Maintained consistent 39-48% throughout all decades
- 🌍 **Persistent Inequality**: Africa, South America, and Oceania remain underrepresented (<5% combined)

### 2️⃣ Age Trends
**How has the median age of laureates changed in the past 50 years?**

🔑 **Key Findings:**
- 📊 **Scientific Categories**: Pronounced upward trajectories, especially in Physics
- ⏰ **Recognition Delay**: Peak recognition now occurs 10-20 years later than in the 1970s
- 🧬 **Complexity Factor**: Growing validation requirements for breakthrough discoveries
- 📚 **Literature & Economics**: Moderate increases with field-specific volatility

### 3️⃣ Collaboration Patterns
**What percentage of prizes are shared among 2-3 winners versus awarded to individuals?**

🔑 **Key Findings:**
- 🤝 **Collaboration Dominance**: Shared prizes outnumber individual prizes since 1995
- 📈 **Increasing Trend**: Collaborative work continues to dominate modern Nobel recognition
- 🔬 **Scientific Complexity**: Reflects team-based nature of contemporary research

### 4️⃣ Institutional Excellence
**Which universities and research institutions have produced the most Nobel laureates in the last 30 years?**

🔑 **Methodology Note:**
- Counts affiliations at time of award (not PhD institution or research location)
- Different methodologies produce different rankings
- Top 15 institutions identified and visualized

### 5️⃣ Young Achievers
**Who were the youngest Nobel Prize winners from each major geographic region?**

🔑 **Key Findings:**
- 🌟 **Global Youngest**: Malala Yousafzai (Asia/Pakistan) at age 17 - Peace Prize 2014
- 🕊️ **Peace Prize Dominance**: 5 of 6 youngest regional winners in Peace category
- 📊 **Age Disparity**: Range from 17 (Asia) to 58 (South America) years old
- 🔬 **Scientific vs. Humanitarian**: Earlier recognition for humanitarian work

### 6️⃣ Category Distribution
**Which Nobel Prize categories have awarded the most prizes?**

🔑 **Key Findings:**
- 🥇 **Physics Leads**: 129 total prizes (most consistent output)
- 🥈 **Medicine Second**: 119 prizes (steady distribution)
- 🥉 **Chemistry Third**: 114 prizes (gradual growth pattern)
- 📊 **Economic Sciences**: 90 prizes (strong growth as newer category)
- 🕊️ **Peace**: 72 prizes (consistent patterns)
- 📚 **Literature**: 51 prizes (fewest awards)

---

## 📊 Sample Visualizations

### Continental Distribution Over Time
```
1975-1984              2015-2024
Europe     ████████████████████ 49.5%  →  Europe     ██████████████ 35.8%
N.America  ████████████████ 39.5%      →  N.America  ████████████████ 40.2%
Asia       ██ 3.0%                     →  Asia       ████████ 18.1%
```

### Median Age Trends
```
Category          1975-1984    2015-2024    Change
Physics           56 years  →  63 years     +7 years
Chemistry         58 years  →  65 years     +7 years
Medicine          57 years  →  62 years     +5 years
Peace             62 years  →  65 years     +3 years
Literature        68 years  →  70 years     +2 years
Economics         67 years  →  67 years      0 years
```

### Prize Sharing Evolution
```
Individual Prizes    ███████████░░░░░░░░░  1975-1984: 45%
                     ██████░░░░░░░░░░░░░░  2015-2024: 28%

Shared Prizes        ████████████░░░░░░░░  1975-1984: 55%
                     ████████████████████  2015-2024: 72%
```

---

## 🚀 Running the Analysis

### Prerequisites
```r
# Install required packages
install.packages(c("httr", "jsonlite", "tidyverse", 
                   "lubridate", "ggplot2", "scales"))
```

### Execution Steps

1. **Clone or download the project**
```bash
git clone https://github.com/yourusername/nobel-prize-analysis.git
cd nobel-prize-analysis
```

2. **Open in RStudio**
```r
# Open the R Markdown file
file.edit("nobel_prize_analysis.Rmd")
```

3. **Run the analysis**
```r
# Knit to HTML
rmarkdown::render("nobel_prize_analysis.Rmd")
```

### API Data Extraction
The analysis includes pagination logic to fetch all laureate records:
- Fetches 100 records per batch
- Automatically handles pagination
- Combines all batches into comprehensive dataset
- Typical execution: ~10-15 API calls for complete dataset

---

## 📈 Key Insights Summary

### 🌍 Geographic Trends
- **Shifting Power Centers**: Traditional European dominance declining as Asian representation surges
- **American Consistency**: U.S. institutions maintain steady output across all decades
- **Global Inequality**: Persistent underrepresentation from Southern Hemisphere

### 👥 Demographic Patterns
- **Aging Recognition**: Scientific breakthroughs take longer to gain consensus
- **Collaboration Era**: Team science dominates modern Nobel awards
- **Youth Potential**: Peace Prize recognizes younger changemakers vs. decades-long scientific careers

### 🎓 Institutional Leadership
- **U.S. Dominance**: American universities dominate top 15 institutions
- **Research Excellence Clusters**: Geographic concentration in traditional research hubs
- **Affiliation Complexity**: Methodology matters when counting institutional contributions

### 📊 Category Evolution
- **Scientific Growth**: Physics, Chemistry, and Medicine show increasing prize volumes
- **Economics Maturation**: Economic Sciences establishing consistent recognition pattern
- **Literature Stability**: Most conservative category with minimal variation

---

## 💡 Business Applications

This analysis demonstrates skills relevant to:

### 🎬 **Content & Entertainment (Netflix, etc.)**
- Trend analysis and pattern recognition
- Demographic insights for content strategy
- Geographic market analysis
- Temporal pattern identification

### 📊 **Data Science & Analytics**
- API integration and data extraction
- Large-scale data transformation
- Statistical analysis and visualization
- Insight generation from complex datasets

### 🔬 **Research & Academia**
- Bibliometric analysis capabilities
- Citation and impact tracking
- Institutional benchmarking
- Longitudinal trend analysis

---

## 🎨 Visualization Highlights

### Design Principles
- 🎨 **Pastel Color Palette**: Professional, accessible color schemes
- 📊 **Multiple Chart Types**: Area charts, line graphs, stacked bars, horizontal bars
- 📝 **Clear Annotations**: Descriptive titles, subtitles, and captions
- 🎯 **Data-Ink Ratio**: Minimal clutter, maximum insight
- 📐 **Consistent Theming**: Unified visual language across all plots

### Chart Types Used
- **Stacked Area Charts**: Continental distribution over time
- **Multi-Line Graphs**: Age trends by category
- **Stacked Bar Charts**: Prize sharing and category distribution
- **Horizontal Bar Charts**: Institutional rankings
- **Faceted Visualizations**: Multi-dimensional comparisons

---

## 🔮 Future Enhancements

### Potential Extensions
- [ ] 🌐 **Gender Analysis**: Track female representation across categories and decades
- [ ] 🔗 **Network Analysis**: Map collaboration networks between laureates
- [ ] 🏛️ **Institutional Mobility**: Track career paths and institutional movements
- [ ] 📚 **Citation Analysis**: Integrate with publication databases for impact metrics
- [ ] 🤖 **Machine Learning**: Predict future laureate characteristics
- [ ] 🗺️ **Interactive Dashboard**: Shiny app for dynamic exploration
- [ ] 📖 **Literature Analysis**: Text mining of laureate biographies
- [ ] 💰 **Economic Impact**: Analyze prize monetary value adjustments over time

---

## 📚 Data Source & Attribution

### Official API Documentation
- **API Homepage**: https://www.nobelprize.org/about/developer-zone-2/
- **API Base URL**: https://api.nobelprize.org/2.1/
- **Endpoint Used**: `/laureates`
- **Rate Limits**: Standard fair-use policy
- **Data License**: Public API for educational and research purposes

### Citation
```
Nobel Prize API. (2025). Nobel Prize laureate data [Dataset]. 
The Nobel Foundation. https://api.nobelprize.org/
```

---

## 🎓 Academic Context

**Course**: DATA 607 - Data Acquisition and Management  
**Institution**: CUNY School of Professional Studies  
**Program**: Master of Science in Data Science  
**Semester**: Fall 2024

### Learning Objectives Demonstrated
- ✅ API integration and RESTful data extraction
- ✅ JSON parsing and nested data structure handling
- ✅ Data cleaning and transformation (tidyverse)
- ✅ Exploratory data analysis (EDA)
- ✅ Advanced data visualization (ggplot2)
- ✅ Statistical trend analysis
- ✅ Reproducible research with R Markdown
- ✅ Professional documentation and communication

---

## 👩‍💻 Author

**Candace Grant**  
🎓 MS Data Science Candidate | CUNY School of Professional Studies  
👩‍🏫 Multi-Subject Teacher | Biology, Chemistry, Physics, Coding  
📧 [Your Email]  
💼 [LinkedIn Profile]  
🔗 [Portfolio Website]  
🐙 [GitHub Profile]

---

## 🙏 Acknowledgments

- 🏆 **The Nobel Foundation** for maintaining the comprehensive laureate API
- 📊 **Hadley Wickham & RStudio** for tidyverse ecosystem
- 📚 **Project Gutenberg** for democratizing literature access
- 👨‍🏫 **CUNY SPS Faculty** for guidance and mentorship
- 🌐 **Open Source Community** for R packages and documentation

---

## 📝 License

This project is created for educational purposes as part of graduate coursework in Data Science. Data sourced from the publicly accessible Nobel Prize API is used in accordance with fair use principles for academic research and analysis.

---

## 🔗 Related Projects

- 📚 [Sentiment Analysis: A Tidy Approach](../sentiment-analysis/)
- 📊 [Time Series Forecasting: ATM Cash Withdrawals](../time-series-forecasting/)
- 🎬 [Corporate Annual Report Sentiment Analysis](../corporate-sentiment/)

---

<div align="center">

### ⭐ If you found this analysis insightful, please star this repository! ⭐

**Made with 💛 and R**

![API Integration](https://img.shields.io/badge/API%20Integration-Expert-brightgreen)
![Data Visualization](https://img.shields.io/badge/Data%20Viz-Advanced-blue)
![Exploratory Analysis](https://img.shields.io/badge/EDA-Professional-orange)
![R Programming](https://img.shields.io/badge/R-Advanced-276DC3)

---

### 📊 Analysis Stats

![Total Laureates](https://img.shields.io/badge/Laureates%20Analyzed-1000+-gold)
![Time Period](https://img.shields.io/badge/Years%20Covered-50-blue)
![Visualizations](https://img.shields.io/badge/Visualizations-6-green)
![Categories](https://img.shields.io/badge/Categories-6-purple)

</div>
