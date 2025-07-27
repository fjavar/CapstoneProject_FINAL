#### PELSE SEE FINAL PROJECT DELIVERY SECTION BELOW FOR IMPROVEMENT STARTS ON LINE 46

### Cybersecurity Data Analysis

**Frank Javar**

#### Executive summary
Cybersecurity threats have been on the rise, with hackers employing increasingly sophisticated tactics and advanced tools, including Artificial Intelligence, to cause harm to individuals, financial systems, and critical infrastructure. To counter these evolving challenges, Machine Learning has emerged as a powerful solution for quickly detecting malware and preventing attacks before they occur. This project focuses on utilizing unsupervised machine learning techniques to identify, classify, and analyze anomalies that could signal potential security threats by examining patterns in network traffic. Specifically, the goal is to explore approaches such as clustering algorithms and dimensionality reduction methods to uncover hidden patterns and improve threat detection capabilities.  
#### Rationale
Cybercrime was projected to cost the global economy $8 trillion in 2023, according to Cybersecurity Ventures, with this figure expected to rise to $10.5 trillion annually by 2025, solidifying cybercrime as one of the most significant economic threats worldwide. Additionally, ransomware attacks alone were estimated to cost businesses over $20 billion in 2023, a sharp increase from $11.5 billion in 2019. Implementing more robust methodologies, combined with proactive traffic monitoring and pattern recognition to detect threats before an attack occurs, could prove to be a highly effective strategy for significantly reducing these losses.

#### Research Question
Using “Unsupervised Learning” ML techniques to detect/identify and classify potential threats/anomalies by analyzing patterns in network traffic. 

#### Data Sources
What data will you use to answer you question?
https://www.unb.ca/cic/datasets/index.html
#### Methodology
Exploring techniques such as clustering (e.g., K-means and DBSCAN) or dimensionality reduction (e.g., Principal Component Analysis) to identify patterns in network traffic. For the model several steps completed incldeuing:
 1. Combined four data sets into one and selected most relevant rows thatfor this analysis.
 2. Cleaned up the te data set incuding eliminating Duplicates, NAN, rows with missing values (not a lot of rows elimited here)
 3. Check the outliers (IQR)
 4. Check the data distribution for skewness
 5. Tried to select the right features - This did not work well right now. Left for te final delivery.
 6. Based on my own experiance as a security engineer, I identified columns that can potentially be used by hackers ans used them as Feature columns vs teh  Label column as Target.
 7. Developed the first model based on the Logestic Regression.
 8. For the final delivery, I will develope a Random Forest Model and will compare the results with the Logistic Regression model. 

#### INITIAL Results
In general, there are several results inclduing:  
Detection of malicious activities - Identify unusual traffic patterns, Detect unauthorized attempts, Spot signs of exploitation
o Identify anatomies - Identify spikes in network traffic, Spot traffic using unusual or rarely used protocols, identify traffic occurring at unusual times
o Threat attribution - Pinpoint the origin of malicious traffic, Determine the type of attack, Link malicious activity to known threat actors or groups
o In particule the inititial results indicat that:
 1. The model is created with Logistic Regression:
    a. Classified types of attacks.
    b. Tabulted metrics inclduing Precesion, Recall, F1-Score, and Support.
    c. Created the confusion Metrix summary of perfroamnce of teh classifications.
 


#### Next steps
o Build other models inclding Random Forst Model and determine best perfroamnce model fo rthis analysis.


#### FINAL PROJECT DELIVERY         #### FINAL PROJECT DELIVERY     #### FINAL PROJECT DELIVERY
Resolved the warning shown during the initial delivery:
    ISSUE: "UndefinedMetricWarning" which was caused by the Logistic Regression model's inability to predict
    Resolution: I replaced the LogisticRegression model with a RandomForestClassifier. This model is often more effective in handling imbalanced data.

Model Imporvement: The overall accuracy has increased to 97%, representing a significant improvement.
Improved Precision and Recall: Precision and recall scores for most classes have also improved considerably.
Ongoing Issue with "Web Attack – Brute Force": The model continues to struggle with identifying this particular attack type, as indicated by a very low recall of 5%. This suggests that, although the model rarely misclassifies other attacks as "Web Attack – Brute Force," it is still missing the majority of actual instances of this attack.

##### MODEL IMPORVEMENT
To enhance the model’s features, I added three additional columns of "PSH Flag Count" (correlation: 0.25), "Packet Length Variance" (correlation: 0.24), and "Bwd Packet Length Std" (correlation: 0.24)—as shown in the correlation table above.
    After incorporating the three additional features, the model’s overall performance improved significantly. The updated model achieved higher accuracy, and the macro averages for precision, recall, and F1-score all increased substantially. This indicates that the model is now much more effective at accurately classifying all types of attacks.

        - "Web Attack � Brute Force" Detection: The most significantimprovement is in the detection of the "Web Attack � Brute Force" class. The recall for this class has jumped from a mere 5% to 88%! This means the model is now able to correctly identify most of the "Web Attack � Brute Force" instances.
        - Precision-Recall Balance: The new model has a much better balance between precision and recall, as indicated by the higher f1-score.

##### ADDING HYPERPARAMETER
    The performance of the tuned model is almost identical to the model with the default parameters. It seems that the default hyperparameters of the Random Forest Classifier were already quite good for this dataset.

##### IMPROVE IMBALANCE
To improve Imbalance "Web Attack � Brute Force" classifier, ran two algorithms of "RandomOverSampling" and "SMOTE".
    RANDOMOVERSMAPLING:
        "Web Attack � Brute Force" Recall: The recall for the "Web Attack � Brute Force" class is now 100%! This is a great improvement and means that the model is now able to correctly identify all instances of this attack.
        Precision-Recall Trade-off: However, this improvement in recall has come at the cost of a decrease in precision for the "Web Attack � Brute Force" class (from 69% to 24%). This means that the model is now more likely to misclassify other attacks as "Web Attack � Brute Force".
        Overall Performance: The overall accuracy of the model has decreased slightly, and the macro averages for precision and f1-score are also lower.
    SMOTE:
        RandomOverSampler and SMOTE, have produced very similar results. Both significantly improve the recall for the "Web Attack � Brute Force" class to 100%, but at the cost of a lower precision (24%).
    ** CONCLUSION**:
        I want to minimize false positives, even if it means missing a few instances of "Web Attack � Brute Force". As such, I am happy with the previous model and its overall performance.

##### THIRD MODEL (LIGHTGBM)
Searching for teh best model, and I selected LightGBM. After running the model, the results:
    The LightGBM model performs very similar to Random Forest model. The comparison analysis indicates:

    - Accuracy: Both models achieve an impressive 99% accuracy.
    - Precision, Recall, and F1-score: The scores for both models are almost identical across all classes.
    This tells me that for this dataset, both Random Forest and LightGBM are good choices. Since their performance is so similar, I can confidently choose either one.

##### Contact and Further Information
Frank Javar
fjavar@mitre.org