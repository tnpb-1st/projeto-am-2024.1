# Overview

The dataset represents ten years (1999-2008) of clinical care at 130 US hospitals and integrated delivery networks. Each row concerns hospital records of patients diagnosed with diabetes, who underwent laboratory, medications, and stayed up to 14 days. The goal is to determine the early readmission of the patient within 30 days of discharge. The problem is important for the following reasons. Despite high-quality evidence showing improved clinical outcomes for diabetic patients who receive various preventive and therapeutic interventions, many patients do not receive them. This can be partially attributed to arbitrary diabetes management in hospital environments, which fail to attend to glycemic control. Failure to provide proper diabetes care not only increases the managing costs for the hospitals (as the patients are readmitted) but also impacts the morbidity and mortality of the patients, who may face complications associated with diabetes.

O conjunto de dados representa dez anos (1999-2008) de atendimento clínico em 130 hospitais e redes de atendimento integradas nos EUA. Cada linha refere-se a registros hospitalares de pacientes diagnosticados com diabetes, que passaram por exames laboratoriais, receberam medicações e permaneceram internados por até 14 dias. O objetivo é determinar a readmissão precoce do paciente dentro de 30 dias após a alta. **O problema é importante pelas seguintes razões: apesar das evidências de alta qualidade que mostram melhores resultados clínicos para pacientes diabéticos que recebem diversas intervenções preventivas e terapêuticas, muitos pacientes não as recebem. Isso pode ser parcialmente atribuído à gestão arbitrária do diabetes em ambientes hospitalares, que não atendem ao controle glicêmico. A falta de um cuidado adequado com o diabetes não apenas aumenta os custos de gestão para os hospitais (já que os pacientes são readmitidos), mas também impacta a morbidade e mortalidade dos pacientes, que podem enfrentar complicações associadas ao diabetes.**

# Dataset Info
What do the instances in this dataset represent?
- The instances represent hospitalized patient records diagnosed with diabetes.

- Are there recommended data splits?
- No recommendation. The standard train-test split could be used. Can use three-way holdout split (i.e., train-validation-test) when doing model selection.

Does the dataset contain data that might be considered sensitive in any way?
- Yes. The dataset contains information about the age, gender, and race of the patients.

**Additional Information**

The dataset represents ten years (1999-2008) of clinical care at 130 US hospitals and integrated delivery networks. It includes over 50 features representing patient and hospital outcomes. Information was extracted from the database for encounters that satisfied the following criteria.
1.	It is an inpatient encounter (a hospital admission).
2.	It is a diabetic encounter, that is, one during which any kind of diabetes was entered into the system as a diagnosis.
3.	The length of stay was at least 1 day and at most 14 days.
4.	Laboratory tests were performed during the encounter.
5.	Medications were administered during the encounter.

The data contains such attributes as patient number, race, gender, age, admission type, time in hospital, medical specialty of admitting physician, number of lab tests performed, HbA1c test result, diagnosis, number of medications, diabetic medications, number of outpatient, inpatient, and emergency visits in the year before the hospitalization, etc.

Has Missing Values?
- Yes 

# Columns Description

| Variable Name                  | Role    | Type       | Demographic         | Description                                                                                                                | Units | Missing Values |
|---------------------------------|---------|------------|---------------------|----------------------------------------------------------------------------------------------------------------------------|-------|----------------|
| encounter_id                   | ID      |            |                     | Unique identifier of an encounter                                                                                           |       | no             |
| patient_nbr                    | ID      |            |                     | Unique identifier of a patient                                                                                              |       | no             |
| race                            | Feature | Categorical | Race                | Values: Caucasian, Asian, African American, Hispanic, and other                                                             |       | yes            |
| gender                          | Feature | Categorical | Gender              | Values: male, female, and unknown/invalid                                                                                    |       | no             |
| age                             | Feature | Categorical | Age                 | Grouped in 10-year intervals: [0, 10), [10, 20), ..., [90, 100)                                                           |       | no             |
| weight                          | Feature | Categorical |                     | Weight in pounds.                                                                                                          |       | yes            |
| admission_type_id              | Feature | Categorical |                     | Integer identifier corresponding to 9 distinct values, e.g., emergency, urgent, elective, newborn, and not available    |       | no             |
| discharge_disposition_id        | Feature | Categorical |                     | Integer identifier corresponding to 29 distinct values, e.g., discharged to home, expired, and not available               |       | no             |
| admission_source_id             | Feature | Categorical |                     | Integer identifier corresponding to 21 distinct values, e.g., physician referral, emergency room, and transfer from a hospital |       | no             |
| time_in_hospital                | Feature | Integer      |                     | Integer number of days between admission and discharge                                                                       |       | no             |
| payer_code                      | Feature | Categorical |                     | Integer identifier corresponding to 23 distinct values, e.g., Blue Cross/Blue Shield, Medicare, and self-pay              |       | yes            |
| medical_specialty               | Feature | Categorical |                     | Integer identifier of a specialty of the admitting physician, corresponding to 84 distinct values, e.g., cardiology      |       | yes            |
| num_lab_procedures              | Feature | Integer      |                     | Number of lab tests performed during the encounter                                                                           |       | no             |
| num_procedures                  | Feature | Integer      |                     | Number of procedures (other than lab tests) performed during the encounter                                                  |       | no             |
| num_medications                 | Feature | Integer      |                     | Number of distinct generic names administered during the encounter                                                           |       | no             |
| number_outpatient                | Feature | Integer      |                     | Number of outpatient visits of the patient in the year preceding the encounter                                              |       | no             |
| number_emergency                 | Feature | Integer      |                     | Number of emergency visits of the patient in the year preceding the encounter                                                |       | no             |
| number_inpatient                 | Feature | Integer      |                     | Number of inpatient visits of the patient in the year preceding the encounter                                               |       | no             |
| diag_1                          | Feature | Categorical |                     | The primary diagnosis (coded as first three digits of ICD9); 848 distinct values                                             |       | yes            |
| diag_2                          | Feature | Categorical |                     | Secondary diagnosis (coded as first three digits of ICD9); 923 distinct values                                              |       | yes            |
| diag_3                          | Feature | Categorical |                     | Additional secondary diagnosis (coded as first three digits of ICD9); 954 distinct values                                     |       | yes            |
| number_diagnoses                | Feature | Integer      |                     | Number of diagnoses entered to the system                                                                                   |       | no             |
| max_glu_serum                   | Feature | Categorical |                     | Indicates the range of the result or if the test was not taken. Values: >200, >300, normal, and none if not measured        |       | no             |
| A1Cresult                       | Feature | Categorical |                     | Indicates the range of the result or if the test was not taken. Values: >8, >7, normal, and none if not measured           |       | no             |
| metformin                       | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| repaglinide                     | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| nateglinide                     | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| chlorpropamide                  | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glimepiride                     | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| acetohexamide                   | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glipizide                       | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glyburide                       | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| tolbutamide                     | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| pioglitazone                    | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| rosiglitazone                   | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| acarbose                        | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| miglitol                        | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| troglitazone                    | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| tolazamide                      | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| examide                         | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| citoglipton                     | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| insulin                         | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glyburide-metformin             | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glipizide-metformin             | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| glimepiride-pioglitazone       | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| metformin-rosiglitazone        | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| metformin-pioglitazone         | Feature | Categorical |                     | Indicates whether the drug was prescribed or there was a change in dosage. Values: up, down, steady, and no                 |       | no             |
| change                          | Feature | Categorical |                     | Indicates if there was a change in diabetic medications. Values: change and no change                                      |       | no             |
| diabetesMed                     | Feature | Categorical |                     | Indicates if there was any diabetic medication prescribed. Values: yes and no                                                |       | no             |
| readmitted                      | Target  | Categorical |                     | Days to inpatient readmission. Values: <30 if the patient was readmitted in less than 30 days,
---
# Useful Links
- [Dataset Source](https://archive.ics.uci.edu/ml/datasets/Diabetes+130-US+hospitals+for+years+1999-2008)
- [Dataset Source II](https://www.openml.org/search?type=data&sort=runs&id=4541&status=active)
- [Kaggle Disscusion](https://www.kaggle.com/discussions/general/37013#214415)
- [Kaggle Dataset](https://www.kaggle.com/brandao/diabetes)