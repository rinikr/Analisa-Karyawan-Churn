# Analisa Untuk Memprediksi Karyawan yang Keluar (Churn)

## Final Project
Project ini merupakan persyaratan kelulusan pada bootcamp yang saya ikuti. Dengan judul "Analisa Untuk Memprediksi Karyawan yang Keluar (Churn)", project ini saya kerjakan dengan mengidentitikasi faktor-faktor yang paling berpengaruh terhadap keluar/berhentinya seorang karyawan.

## Data
Data yang digunakan bersumber pada:
* Kaggle: https://www.kaggle.com/datasets/ninopadilla13/employee-churn

Dataset ini mengandung 14249 baris dan 10 kolom dengan detail nama kolom:
avg_monthly_hrs,department,filed_complaint,last_evaluation,n_projects,recently_promoted,salary,satisfaction,status,tenure.

## DEEP DIVE EDA
1. Berapa rata rata, median, maksimum, minimum lama bekerja dan Bagaimana distribusi lama bekerja karyawan
![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/33625fb4-b557-4743-9eb6-8a7e997b8c40)

2. Berapa jumlah karyawan yang masih aktif dan berhenti
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/9ba5f0d2-26c4-4339-9814-8184715a7819)

3. Bagaimana distribusi jam kerja bulanan untuk karyawan yang churn/left dan employed berdasarkan departemennya
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/c20a7b9d-ba85-4dda-84b6-ac5f4110bb10)

4. Bagaimana tingkat kepuasan karyawan yang left/churn dan yang employed
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/d4341328-5a45-47cc-b4b9-a51e477b0060)

5. mencari rata rata tenure dari employee yang berhenti (churn) dan dan tidak churn
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/aeca9506-4c56-483d-83d5-1b56cb9a4b39)

6. Bagaimana distribusi karyawan yang churn/left dan employed berdasarkan tenure di departemen
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/23d3ba18-6bd1-41ac-b6b8-83b89e8008c6)

7. Bagaimana distribusi karyawan yang churn/left dan employed di departemen berdasarkan proyek
   ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/073510f8-0197-48f3-a2a1-76fb688945a6)

9. Perbandingan jumlah karyawan yang churn dan masih aktif berdasarkan departemen.

## Library

- import numpy as np
- import pandas as pd
- import seaborn as sns
- import matplotlib.pyplot as plt
- from sklearn.model_selection import GridSearchCV
- from sklearn.model_selection import KFold
- from sklearn.model_selection import cross_validate, StratifiedKFold, RandomizedSearchCV, cross_val_score
- from sklearn import svm,tree
- from sklearn import ensemble
- from sklearn.linear_model import LogisticRegression
- from sklearn.tree import DecisionTreeClassifier
- from sklearn.neighbors import KNeighborsClassifier
- from sklearn.naive_bayes import GaussianNB
- from sklearn.svm import SVC
- from sklearn.ensemble import RandomForestClassifier
- from sklearn import metrics
- from sklearn.metrics import confusion_matrix
- from sklearn.metrics import auc,roc_auc_score
- from sklearn.metrics import roc_auc_score, roc_curve, RocCurveDisplay, precision_recall_curve, PrecisionRecallDisplay
- from sklearn.model_selection import train_test_split as tts
- from sklearn import model_selection

### Machine Learning

#### Model Comparison Classifier
  ![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/98821e0f-0d76-45c6-8131-165d5009d164)
Random Forest:
Algoritma Random Forest memiliki kinerja yang paling tinggi di antara semua algoritma yang
dievaluasi . Ini ditunjukkan dengan nilai ROC AUC_Mean sebesar 97.44, yang menandakan bahwa model ini memiliki
kemampuan yang sangat baik dalam membedakan antara kelas positif dan negatif . Selain itu , F1 score_Mean yang
mencapai 93.31 menunjukkan bahwa model ini mencapai keseimbangan yang baik antara recall dan precision.

#### Evaluation For Data Test
![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/9fc6a95e-cc97-4efd-9997-5199a5c4cb93)
![image](https://github.com/rinikr/Analisa-Karyawan-Churn/assets/153416198/e72d852f-30b3-42f4-ab5b-4ca97c4dd5b6)
True Positive (TP)
adalah 1943, yang merupakan jumlah karyawan
yang diprediksi aktif dan kenyataannya masih aktif . True Negative (TN)
adalah 2100, yang merupakan jumlah karyawan yang diprediksi
berhenti (churn) dan kenyataannya churn . False Positive (FP) adalah
200, yang merupakan jumlah karyawan yang diprediksi aktif , tetapi
sebenarnya tidak aktif (churn). False Negative (FN) adalah 38, yang
merupakan jumlah karyawan yang diprediksi tidak aktif
(churn kenyataannya aktif)


