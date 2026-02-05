## Rule-Based Improvement Process

After selecting the best-performing KNN model with **K = 1**, the baseline performance of the model was evaluated. The initial predictions and misclassified samples are shown below.

### Baseline Model (KNN with K = 1)

The following output shows the incorrect predictions produced by the KNN model before applying any rule-based corrections.


Baseline Accuracy: **%76**

<img width="818" height="590" alt="Ekran görüntüsü 2026-02-05 102400" src="https://github.com/user-attachments/assets/fd255598-0848-44af-a006-bc5ede60ae3f" />


---

## Incremental Rule-Based Improvements

To improve the model performance, misclassified samples were analyzed and simple decision rules were introduced incrementally. After each rule was added, the change in accuracy was observed and recorded.

---

### Rule 1 – Short Height and Small Head Circumference → Female

The KNN model incorrectly classified some individuals with very short height and small head circumference as male.  
To correct these cases, samples predicted as male with **height below 57 cm** and **head circumference below 39.5 cm** were reclassified as female.

**Accuracy after Rule 1:** **%78**

<img width="945" height="631" alt="Rule1" src="https://github.com/user-attachments/assets/700326d6-d082-4979-b82a-44f347643d3f" />

Corrected samples: 12


---

### Rule 2 – Height in Low 70s with Large Head Circumference → Female

In the **70–74 cm** height range, several samples with relatively large head circumference were misclassified as male.  
This region represents a boundary area where the KNN model struggled to separate classes.

**Accuracy after Rule 1 and Rule 2:** **%80**

<img width="952" height="651" alt="Rule1 and Rule2" src="https://github.com/user-attachments/assets/4807eb1f-5f55-4e47-9773-2b3f78784c2a" />

Corrected samples: 12, 37, 45, 44


---

### Rule 3 – Height in 80s with Mid-Range Head Circumference → Female

For individuals with height between **79–86 cm**, misclassifications occurred when head circumference values were within a specific mid-range.  
A carefully tuned threshold was applied to correct these cases while preserving correct male classifications.

**Accuracy after Rule 1, Rule 2 and Rule3 :** **%84**

<img width="1005" height="657" alt="Rule1, Rule2 and Rule3" src="https://github.com/user-attachments/assets/62bf88fc-bea9-421a-8600-31f4621710ff" />

Corrected samples: 12, 37, 45, 44, 74, 63, 75



---

## Final Model Performance

After applying all rule-based corrections, the final model performance was obtained as follows:

**Final Accuracy (KNN + Rules):** **%84**

<img width="767" height="541" alt="Final" src="https://github.com/user-attachments/assets/2f595e1d-e7c9-4c99-8961-483cd1e7875a" />

**Corrected Samples After Rules**

The following samples were incorrectly classified by the KNN (K=1) model but were successfully corrected after applying the rule-based post-processing:

**Corrected samples:**
12, 37, 45, 44, 74, 63, 75

For these samples, the final predictions match the true gender labels.

**Remaining Misclassified Samples**

Despite applying all defined rules, the following samples remain incorrectly classified:

Remaining samples:
159, 22, 189, 129, 8


---

## Discussion

The incremental improvement in accuracy demonstrates how simple rule-based post-processing, derived from model error analysis, can significantly enhance classification performance.  
This approach provides a clear and intuitive transition toward **Decision Tree models**, where similar rules are learned automatically.

