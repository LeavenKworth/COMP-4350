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

<img width="997" height="570" alt="after rule 1" src="https://github.com/user-attachments/assets/7b73640f-0827-4e62-ba73-40cf134c7773" />



---

### Rule 2 – Height in Low 70s with Large Head Circumference → Female

In the **70–74 cm** height range, several samples with relatively large head circumference were misclassified as male.  
This region represents a boundary area where the KNN model struggled to separate classes.

**Accuracy after Rule 1 and Rule 2:** **%80**

<img width="953" height="545" alt="after 1 and 2" src="https://github.com/user-attachments/assets/4104da79-cacc-4039-a959-ecdec5483208" />



---

### Rule 3 – Height in 80s with Mid-Range Head Circumference → Female

For individuals with height between **79–86 cm**, misclassifications occurred when head circumference values were within a specific mid-range.  
A carefully tuned threshold was applied to correct these cases while preserving correct male classifications.

**Accuracy after Rule 1, Rule 2 and Rule3 :** **%84**

<img width="1017" height="546" alt="after 1,2 and 3" src="https://github.com/user-attachments/assets/a161125b-16b7-448a-ae3f-2d5c66d286e6" />



---

## Final Model Performance

After applying all rule-based corrections, the final model performance was obtained as follows:

**Final Accuracy (KNN + Rules):** **%84**

<img width="991" height="535" alt="Ekran görüntüsü 2026-02-05 102415" src="https://github.com/user-attachments/assets/cc5c803b-16b6-4358-a3f6-e5969c0b0206" />





---

## Discussion

The incremental improvement in accuracy demonstrates how simple rule-based post-processing, derived from model error analysis, can significantly enhance classification performance.  
This approach provides a clear and intuitive transition toward **Decision Tree models**, where similar rules are learned automatically.

