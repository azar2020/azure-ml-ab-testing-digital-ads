# azure-ml-ab-testing-digital-ads

# 📊 Facebook Ad A/B Testing Analysis
### Statistical A/B Testing & Automated ML Pipeline using Azure ML

<img width="2973" height="2352" alt="executive_dashboard_ab" src="https://github.com/user-attachments/assets/d3680c24-c014-4dbb-bfc7-d2643b80a1df" />


## 📋 Project Overview
This end-to-end data analytics project performs a rigorous 
statistical A/B test on real Facebook ad campaign data to 
determine whether Campaign B outperforms Campaign A, and 
includes an **automated Azure ML pipeline** that runs the 
analysis automatically.

**Platform:** Microsoft Azure Machine Learning  
**Dataset:** Facebook Ad Campaign Dataset (Kaggle — 1,143 ads)  
**A/B Test Size:** 108 ads (54 per group, balanced)

---

## 🎯 Business Question
> *"Does Campaign B (Treatment) generate significantly more 
> conversions than Campaign A (Control)? Should we roll it 
> out to all users?"*

---

 ---

## 🔬 Methodology

### Step 1: Data Preparation
- Loaded Facebook ad campaign dataset (1,143 rows)
- Calculated key marketing metrics:
  - **CTR** (Click Through Rate)
  - **Conversion Rate**
  - **CPC** (Cost Per Click)
  - **ROAS** (Return on Ad Spend)
- Removed Campaign C — focused on true A/B test
- Balanced groups via downsampling (54 ads each)

### Step 2: Statistical Testing
| Test | Metric | P-value | Significant? |
|---|---|---|---|
| T-test | CTR | 0.504 | ❌ No |
| T-test | Conversion Rate | 0.446 | ❌ No |
| T-test | ROAS | 0.882 | ❌ No |
| Chi-square | Conversions | 0.573 | ❌ No |

### Step 3: Sample Size Analysis
- Required sample size per group: **347,759**
- Current sample size: **54 per group**
- Conclusion: **Insufficient data to declare winner**

### Step 4: Azure ML Automation
- Built automated pipeline using Azure ML SDK v2
- Pipeline loads data, runs tests, saves results to JSON
- Demonstrates production-ready MLOps practices

---

## 📊 Key Findings

| Metric | A - Control | B - Treatment | Difference |
|---|---|---|---|
| CTR | 0.0180% | 0.0183% | +1.7% |
| Conversion Rate | 0.0137% | 0.0274% | +100.5% |
| ROAS | 0.194 | 0.144 | -25.8% |
| Ad Spend | $150 | $2,893 | +1,829% |

---

## 💡 Business Recommendations

1. **Do NOT declare B as winner yet**
   - Results are not statistically significant (all p > 0.05)
   - Need 347,759 samples per group for reliable conclusions

2. **B shows promising conversion lift (+100.5%)**
   - Worth continuing the test with more data
   - Monitor closely as spend scales up

3. **A has significantly better ROAS (0.194 vs 0.144)**
   - A is more cost-efficient per conversion
   - Keep A running while collecting more data

4. **Target 30-34 age group**
   - Highest conversions in both campaigns
   - Prioritize budget allocation to this segment

5. **Focus on male audience**
   - Higher conversion volume across both groups
   - Consider gender-specific ad creatives

---

## 📈 Visualizations

### Campaign Overview
<img width="2973" height="1764" alt="campaign_overview (1)" src="https://github.com/user-attachments/assets/659a77bd-0497-4268-9e15-8b9bef1ced8f" />


### Performance Deep Dive
<img width="2973" height="882" alt="performance_deep_dive" src="https://github.com/user-attachments/assets/5346ee3f-38e2-437e-bda8-31bf67488a87" />


### Statistical Test Results
<img width="2373" height="1033" alt="statistical_results_balanced" src="https://github.com/user-attachments/assets/d65ebc43-0707-45f8-a1a2-2bf8e8a5b7cf" />


### Executive Dashboard
<img width="2973" height="2352" alt="executive_dashboard_ab" src="https://github.com/user-attachments/assets/6002c64a-0367-4604-93f4-30409b322f17" />


---

## ☁️ Azure ML Features Used

| Feature | Usage |
|---|---|
| **Notebooks** | Full analysis & visualization |
| **Compute Instance** | Cloud-based Python execution |
| **Command Jobs** | Automated pipeline execution |
| **Experiments** | Job tracking & monitoring |
| **Environments** | Reproducible dependencies |

---

## 🤖 Automation

Built an **Azure ML automated pipeline** that:
- Loads the latest ad campaign data
- Calculates all marketing metrics automatically
- Runs statistical significance tests
- Saves results to `automated_results.json`

 
## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| **Cloud Platform** | Microsoft Azure ML |
| **Language** | Python 3.10 |
| **Data Analysis** | pandas, numpy |
| **Statistics** | scipy (t-test, chi-square) |
| **Visualization** | matplotlib, seaborn |
| **ML Platform** | Azure ML SDK v2 |
| **Authentication** | Azure DefaultAzureCredential |

---

## 📐 Statistical Concepts Demonstrated
- A/B Testing methodology
- T-test for continuous metrics
- Chi-square test for categorical outcomes
- Sample size & statistical power analysis
- Confidence intervals
- P-value interpretation
- Practical vs statistical significance

---

## 👤 Author
**Azar Taheri**  
📧 aazartaheri@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/aazartaheri)  

 
