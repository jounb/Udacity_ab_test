# Udacity A/B Testing Experiment Analysis  

This project analyzes an **A/B test run by Udacity** as part of their [A/B Testing course](https://www.udacity.com/course/ab-testing--ud257). The numbers have been slightly modified for learning purposes, but the experimental design and patterns are based on a real-world Udacity experiment.  

The experiment tested whether setting **clearer time commitment expectations** before starting a free trial would:  
1. Reduce frustrated students who drop out of the trial early.  
2. Maintain (or improve) the number of students who remain past the trial and eventually pay.  

---

## 📖 Table of Contents  
1. [Background](#background)  
2. [Experiment Overview](#experiment-overview)  
3. [Experiment Design](#experiment-design)  
4. [Data Analysis](#data-analysis)  
5. [Summary & Recommendations](#summary--recommendations)  

---

## 📚 Background  

- Udacity course pages offered two options:  
  1. **Start free trial** – students provide payment info, get 14 days free, then billed automatically.  
  2. **Access course materials** – free access to videos/quizzes without paid benefits.  

- In this experiment, a **new pop-up screen** asked users how much time they had per week:  
  - If **5+ hours/week**, they proceed as normal.  
  - If **<5 hours/week**, a message suggested accessing free materials instead (but students could still proceed).  

**Hypothesis:**  
- **Gross conversion** (enrollments per click) would **decrease**.  
- **Retention** (students paying after free trial) would **increase**.  
- **Net conversion** (paying students per click) would remain **unchanged**.  

---

## 🧪 Experiment Design  

### Invariant Metrics (sanity checks)  
- **Page views** – unique course page visits (dmin = 3000)  
- **Clicks** – “Start free trial” button clicks (dmin = 240)  
- **Enrollments** – students enrolling in trial (dmin = 50)  
- **Click-through probability** – clicks / page views (dmin = 0.01)  

### Evaluation Metrics (hypothesis testing)  
- **Gross conversion (GC)** – Enrollments / Clicks (dmin = 0.01)  
- **Retention** – Payments / Enrollments (dmin = 0.01)  
- **Net conversion (NC)** – Payments / Clicks (dmin = 0.0075)  

### Sample Size & Duration  
- Required sample sizes:  
  - GC: ~645K page views (~32 days)  
  - Retention: ~4.7M page views (~237 days) → impractical, dropped  
  - NC: ~685K page views (~34 days)  
- Experiment ran for ~37 days, sufficient for **GC** and **NC** analysis.  

---

## 📊 Data Analysis  

### Sanity Checks  
- No significant differences in **page views**, **clicks**, or **CTP** between control & experiment groups (p > 0.05). ✅  

### Hypothesis Testing  
- **Gross Conversion**  
  - Significant decrease in experiment group (p < 0.05).  
  - Difference: **-0.0206** (95% CI: -0.0291, -0.0120).  
  - Practical significance confirmed (CI excludes dmin).  

- **Net Conversion**  
  - No statistically significant difference (p = 0.156).  
  - Difference: **-0.0049** (95% CI: -0.0116, 0.0019).  
  - Suggests experiment did not hurt paying conversions.  

---

## ✅ Summary & Recommendations  

### Key Findings  
- **Gross Conversion ↓**: Fewer students enrolled in free trial (expected).  
- **Net Conversion ↔**: Paying student conversion unaffected (supports hypothesis).  
- Results align with hypothesis that setting time expectations filters out low-commitment students without reducing paying customers.  

### Recommendations  
1. **Confirm data quality**: Enrollment column definitions need clarification; wait 14 more days to confirm results.  
2. **Iterate on experiment design**:  
   - Instead of a pop-up, test a **disclaimer under “Start Free Trial”** for less disruption.  
   - Post-enrollment, test **engagement nudges** (e.g., weekly reminders about time commitment).  
3. **Future experiments**: Focus on boosting retention without reducing trial enrollments.  

---
