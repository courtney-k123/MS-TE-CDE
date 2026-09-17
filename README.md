# MS-TE-CDE
Treatment Effect Neural Controlled Differential Equation (TE-CDE) was adapted from (Seedat et al., 2022) for use in multiple sclerosis. TE-CDE was chosen because of its handling irregularly spaced longitudinal data with treatment-confounder feedback.

The model was initially developed on cancer tumor volume data, looking at growth under different treatment options for the past 55 days, and then predicting for the following 5 days. Since in MS clinically relevant outcomes are longer-term, and patients will have longer disease durations pre-treatment, and longer time periods without any disease activity being recorded (i.e. no relapses or disability worsening), pre- and post-baseline time periods were divided into 3-monthly intervals. 

Up to 5 years of pre-treatment history was included (pre-baseline), and up to 5 years of on-treatment activity was included (post-baseline). The model was therefore adjusted to account for 20 prior time steps and predict across 20 future timesteps. Patients with less than either were handled by including a variable ‘active entries’ which is coded as either 1 for actively being followed or 0 for not being follow up.  

<img width="868" height="481" alt="image" src="https://github.com/user-attachments/assets/242e898a-6ade-4beb-a553-dc407c946a7e" />


Additionally, the model needed to be adjusted to include more predictors: from 2 (cancer volume and patient type) to 6 (age, sex, disease duration, number of lesions, EDSS, relapses).

The root mean squared error (RMSE) was also adjusted, as it no longer needed to be normalised by cancer tumour volumes. 
