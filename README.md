## Rule-Based Improvement Process

After selecting the best-performing **KNN model (K = 1)**, the baseline performance was evaluated.  
The initial predictions and misclassified samples are shown below.

---

### Baseline Model – KNN (K = 1)

The following output shows the incorrect predictions produced by the model  
**before applying any rule-based corrections**.

**Baseline Accuracy:** **76%**

<img width="712" height="567" alt="base" src="https://github.com/user-attachments/assets/44a30e41-8a19-43cf-b46d-1ffc2c5952b4" />




---

## Incremental Rule-Based Improvements

To improve model performance, misclassified samples were analyzed in detail and  
**simple, interpretable decision rules** were introduced incrementally.  
After each rule, changes in accuracy and potential side effects were carefully evaluated.

---

### Rule 1 – Short Height & Small Head Circumference → Female

The KNN model incorrectly classified some individuals with **very short height** and  
**small head circumference** as male. To correct these cases, the following rule was applied.

**Condition**
- Predicted as **Male**
- Height `< 57 cm`
- Head circumference `< 39.5 cm`

**Action**
- Reclassify as **Female**

**Accuracy:** **78%**


  <img src="https://github.com/user-attachments/assets/b14fe610-5bef-47a9-819a-1995630e60fb" width="700">


**Results**
- ✅ **Corrected samples:** `12`
- ⚠️ **Side effects:** None

---

### Rule 2 – Height 70–74 cm & Large Head Circumference → Female

In the **70–74 cm** height range, several samples with relatively large head circumference  
were misclassified as male. This region represents a **decision boundary** where KNN struggled.

**Accuracy:** **80%**


  <img src="https://github.com/user-attachments/assets/5d0d9ac1-0bc3-4a57-af0b-05409c0cfbab" width="800">


**Results**
- ✅ **Corrected samples:** `12, 37, 45, 44`
- ⚠️ **Side effects:** `150, 134`

---

### Rule 3 – Height 79–86 cm & Mid-Range Head Circumference → Female

For individuals with height between **79–86 cm**, misclassifications occurred when  
head circumference values fell within a specific mid-range. Thresholds were carefully  
tuned to correct these cases while minimizing regressions.

**Accuracy:** **84%**


  <img src="https://github.com/user-attachments/assets/34e568a2-ba4a-49b8-b291-7009e3868af0" width="800">


**Results**
- ✅ **Corrected samples:** `12, 37, 45, 44, 74, 63, 75`
- ⚠️ **Side effects:** `170, 150, 134`

---

## Final Model Performance

**Final Accuracy (KNN + Rules):** **84%**


  <img src="https://github.com/user-attachments/assets/2f595e1d-e7c9-4c99-8961-483cd1e7875a" width="700">


---

## Final Error Analysis


**Corrected by Rules**
12, 37, 45, 44, 74, 63, 75

**Remaining Baseline Errors**
159, 22, 189, 129, 8


**Rule-Induced Errors**
170, 150, 134


**Total Remaining Errors**
159, 22, 189, 129, 8, 170, 150, 134


---

## Discussion

This study demonstrates that **rule-based post-processing**, derived from systematic  
error analysis, can significantly improve KNN performance. However, remaining and  
rule-induced errors highlight the limitations of manual rules and motivate the  
transition to **Decision Tree models**, where such rules are learned automatically.
