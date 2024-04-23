RESEARCH POSTER PRESENTATION DESIGN © 2015
www.PosterPresentations.com
The fight against heart disease is a pressing and ongoing battle in
today’s medical community. The ability to recognize and predict
the presence of heart disease early on is critical for preventing
related deaths. Recognizing the importance of the topic, we
trained and evaluated several machine learning models to predict
the presence of heart disease in an individual according to
various medical indicators. All models will be evaluated
according to accuracy, and, for final decision making, recall.
Ultimately, a hyper-tuned Random Forest Classifier will be chosen
to make our final predictions, and these predictions will be
evaluated.
ABSTRACT
Heart Health through Machine Learning:
Predictive Modeling for Heart Disease Detection
Sragvhi Anchaliya, Jack Mitchell, Aditiya Pathak, Jacob Rocque
In searching for datasets for our project, we initially focused on human
health datasets. We were intrigued by the extent to which certain
physical attributes might predict disease presence in individuals. It's
well known that factors like smoking are linked to lung cancer rates,
and similarly, obesity is associated with diabetes. Motivated by this,
we sought to identify the most significant predictive variables for a
prevalent and dangerous disease. Our goal was to determine key
indicators for heart disease, a critical condition where accurate
predictions can have profound implications.
Heart disease is one of the leading causes of mortality worldwide, with
the World Health Organization reporting that it causes nearly 17.9
million deaths every year. That accounts for roughly 32% of all deaths
globally [1]. Heart disease is detrimental but there are also many ways
to prevent it based on physical signs of predisposition. According to
the National Heart, Lung, and Blood Institute, 80% of heart disease is
preventable so being able to predict susceptibility using machine
learning is incredibly important [4].
We found a dataset from Mendeley Data containing about 1000 entries
with 14 variables to use for our project [5]. We ended up using the
variables age, resting blood pressure, gender, chest pain, serum
cholesterol, fasting blood sugar, resting electrocardiogram (EKG)
results, maximum heart rate, EKG oldpeak, EKG peak slope,
number of major blood vessels, and exercise-induced angina. The
primary goal is to utilize these machine learning algorithms to increase
the accuracy of heart disease predictions, thereby aiding healthcare
providers in making informed treatment decisions. We explored
different models to evaluate their performance and reliability, focusing
on their applicability in real-world clinical settings.
INTRODUCTION
A similar study in the realm of predictive analytics for coronary heart
disease is "Effective Heart Disease Prediction Using Machine Learning
Techniques" by Bhatt, C.M., Patel, P., Ghetia, T., & Mazzeo, P.L. (2023),
published on the MDPI platform [2]. This research shares a similar aim
to our project, focusing on enhancing predictive models for coronary
heart disease through the application of machine learning techniques.
Furthermore, the authors of this study explored a variety of machine
learning algorithms to optimize prediction accuracy, including several
techniques that we have also utilized in our work. Their findings offer a
valuable benchmark for assessing the effectiveness of these
algorithms in predictive scenarios. Building on this foundational
research, our project seeks to refine these models further and examine
the impacts of utilizing different datasets. We aim to compare our
results against these established benchmarks to identify potential
improvements in predictive accuracy for models of heart disease.
RELATED WORK
Inspection & Cleaning
We looked for data that contained measurable medical features that
could indicate the presence of heart disease [5]. We started our data
preparation by inspecting our data, we paid attention to data types and
checked for null or invalid values in the data. We did this mainly
through the describe() function to understand their types and values.
Starting with our data cleaning we checked for duplicate values,
missing values, and invalid values/outliers. We did not find any
duplicate values, missing values, or outliers but we did find invalid zero
values where a zero would not make sense based upon the context of
the feature. For example, Serum Cholesterol should not have 0s. For
these values, we imputed the value with the mean of the column as all
invalid zeros were in numerical columns. We then visualized the
distribution of variables using histograms and bar charts to identify
outliers and analyze the data.
Correlation Analysis & Feature Engineering
We calculated correlation coefficients among numerical variables to
identify strong correlations that might influence heart disease
outcomes. We then visualized the correlation matrix using a heatmap
to easily identify highly correlated features, which informed feature
selection and modeling. We used stacked bar charts to show
correlation between variables and the target variable. Overall, every
feature except for patient ID was relevant enough to use for the model.
EKG oldpeak and EKG peak slope seemed especially correlated.
Finally, we scaled all numerical data and encoded all categorical data.
Model Selection
We compared K Nearest Neighbors (KNN), Random Forest, and
Support Vector Machine (SVM) models. We were looking for
algorithms which can handle multiple input variables, are non-linear,
and can perform classification. These models support those
requirements and offer a variety of hyperparameters for tuning. To train
each model, we split our dataset into 70% training and 30% testing.
We hypertuned each model using various parameters. Importantly, we
found optimal values of k and n for KNN and Random Forest
respectively. Each model was evaluated using accuracy and recall
scores to determine their effectiveness in predicting heart disease.
Using both metrics allowed us to strike a balance between overall
accuracy, which is important when medical resources are limited, and
recall, which is important when wanting to minimize false-positives.
METHODOLOGY
KNN & SVM:
The K Nearest Neighbors model demonstrated reasonable accuracy
but was outperformed by the other models even after successful
hypertuning. We eventually got our KNN accuracy up to 0.95 and the
recall up to 0.94. This served as a good baseline for comparing more
complex models. The SVM model offered high accuracy and
robustness against overfitting. Looking at final predictions, it had an
accuracy 0.96 and a recall 0.95.
Random Forest:
The Random Forest model had an accuracy of 0.98 and a recall of
0.98. The optimal number of decision trees was 180, and the other
parameters were set to minimize overfitting after seeing that training
scores were initially higher than testing scores.
This model outperformed the others in terms of accuracy and recall,
making it the most reliable choice for our heart disease prediction
task. Its strength lies in its ability to minimize false negatives, an
important feature in medical diagnostics where missing a diagnosis
can lead to lots of harmful health consequences while also retaining a
high overall accuracy. The model's robustness against overfitting and
its capability to handle large datasets with numerous features made it
particularly suitable for our clinical dataset and confirming its potential
utility in clinical settings.
We can see that training and testing accuracy scores are both very
similar and very high. After several iterations of the model using
hypertuning, training scores were raised to 1 and testing to 0.9757.
Testing scores were initially much lower indicating overfitting. After
simplifying the parameters, we were able to counteract this and bring
the training and testing scores much closer. Final predictions show our
Random Forest model as having a 98% accuracy and recall score.
Additionally, it had a 99% precision score and a 98% F1 score.
When working with medical data, it is imperative to reduce the number
of false negatives as much as possible as it could be detrimental to
missing a positive case. Therefore, we were fortunate to have such a
high recall score along with a high accuracy score.
RESULTS & EVALUATION
IMPACTS
As apparent in the visual above, the most important features in order
of importance are Resting Blood Pressure, ST Segment Slope, and
Blood Vessel Count. This is extremely important and insightful for
medical professionals to be able gauge the importance of certain
symptoms when diagnosing patients and predicting heart disease.
The successful implementation of our predictive model could
positively impact both clinical practices and patients' lives by
enhancing the early detection of heart disease. According to the
Center for Disease Control and Prevention (CDC), early detection and
treatment of cardiovascular conditions can reduce the risk of heart
disease by up to 20% [3]. By providing Healthcare providers with
more accurate diagnostic tools, our model could help facilitate
informed treatment decisions that could lead to improved patient
outcomes and potentially save lives. Patients at risk of heart disease
could receive earlier interventions, potentially preventing the
progression of the condition. Additionally, this model could help
streamline healthcare resources by prioritizing patients based on
risk, thereby improving the efficiency of healthcare delivery.
CONCLUSION
Our project successfully met its primary goal of utilizing machine
learning to enhance the accuracy of heart disease predictions. By
employing and comparing various machine learning models, we
identified the Random Forest model as the most effective in
predicting heart disease with high precision and minimal false
negatives. This achievement is significant, considering that improved
diagnostic accuracy (especially by reducing false negatives) ensures
no patient with heart disease goes undetected. Although focusing on
reducing false negatives may increase healthcare costs due to
additional treatments and testing, this is crucial for saving lives and
preventing the major consequences untreated heart diseases have.
Future work could involve refining the model through integration with
real-time patient data/larger datasets, further testing in clinical trials,
and exploring additional predictive variables to even more accurately
forecast heart disease risk.
[1] World Health Organization. (n.d.). Cardiovascular diseases euro. World Health Organization.
https://www.who.int/europe/health-topics/cancer/cardiovascular-diseases#tab=tab_1
[2] Bhatt CM, Patel P, Ghetia T, Mazzeo PL. Effective Heart Disease Prediction Using Machine
Learning Techniques. Algorithms. 2023; 16(2):88.
[3] Centers for Disease Control and Prevention. (2022, September 8). Heart disease and stroke.
Centers for Disease Control and Prevention.
https://www.cdc.gov/chronicdisease/resources/publications/factsheets/heart-diseasestroke.htm
https://doi.org/10.3390/a16020088
[4] U.S. Department of Health and Human Services. (2023, February 1). Numbers to know for a
healthy heart. National Heart Lung and Blood Institute.
https://www.nhlbi.nih.gov/news/2023/numbers-know-healthyheart#:~:text=Bello%2C%20M.D.%2C%20M.P.H.%2C%20director,is%20preventable%2C%E2%80
%9D%20she%20said
[5] Doppala, B. P. (2021, April 16). Cardiovascular_Disease_Dataset. Mendeley Data.
https://data.mendeley.com/datasets/dzz48mvjht/1
REFERENCES
Class: DS 3000
Group: 17
