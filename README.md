## Rule-Based Improvement Process

After selecting the best-performing KNN model with **K = 1**, the baseline performance of the model was evaluated. The initial predictions and misclassified samples are shown below.

### Baseline Model (KNN with K = 1)

The following output shows the incorrect predictions produced by the KNN model before applying any rule-based corrections.



Baseline Accuracy: **%76**

---

## Incremental Rule-Based Improvements

To improve the model performance, misclassified samples were analyzed and simple decision rules were introduced incrementally. After each rule was added, the change in accuracy was observed and recorded.

---

### Rule 1 – Short Height and Small Head Circumference → Female

The KNN model incorrectly classified some individuals with very short height and small head circumference as male.  
To correct these cases, samples predicted as male with **height below 57 cm** and **head circumference below 39.5 cm** were reclassified as female.

**Accuracy after Rule 1:** **%78**



---

### Rule 2 – Height in Low 70s with Large Head Circumference → Female

In the **70–74 cm** height range, several samples with relatively large head circumference were misclassified as male.  
This region represents a boundary area where the KNN model struggled to separate classes.

**Accuracy after Rule 1 and Rule 2:** **%80**



---

### Rule 3 – Height in 80s with Mid-Range Head Circumference → Female

For individuals with height between **79–86 cm**, misclassifications occurred when head circumference values were within a specific mid-range.  
A carefully tuned threshold was applied to correct these cases while preserving correct male classifications.

**Accuracy after Rule 1, Rule 2 and Rule3 :** **%84**



---

## Final Model Performance

After applying all rule-based corrections, the final model performance was obtained as follows:

**Final Accuracy (KNN + Rules):** **XX.XX**



---

## Discussion

The incremental improvement in accuracy demonstrates how simple rule-based post-processing, derived from model error analysis, can significantly enhance classification performance.  
This approach provides a clear and intuitive transition toward **Decision Tree models**, where similar rules are learned automatically.

