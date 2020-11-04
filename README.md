# Cardiac CINE MRI Segmentation
 
## Introduction
Analysis of cardiac function plays an important role in clinical cardiology for patient management, disease diagnosis, risk evaluation, and therapy decision. Thanks to digital imagery, the assessment of a set of complementary indices computed from different structures of the heart is a routine task for cardiac diagnostics. Because of its well known capacity for discriminating different types of tissues, Cardiac MRI (CMR) (built from series of parallel short axis slices) is considered as the gold standard of cardiac function analysis through the assessment of the left and right ventricular ejection fractions (EF) and stroke volumes (SV), the left ventricle mass and the myocardium thickness. This requires accurate delineation of the left ventricular endocardium and epicardium, and of the right ventricular endocardium for both end diastolic (ED) and end systolic (ES) phase instances. In clinical practice, semi-automatic segmentation is still a daily practice because of the lack of accuracy of fully-automatic cardiac segmentation methods. This leads to time consuming tasks prone to intra- and inter-observer variability. In this project, I propose a Deep learning (DL)-based algorithm for segmenting myocardium and both the ventricles in cardiac MRI. DL algorithms are good at automatically discovering intricate features from data for object detection and segmentation. These features are directly learned from data using a general-purpose learning procedure and in end to-end fashion. This makes DL-based algorithms easy to apply to other image analysis applications.

In this project I investigate the problem of semantic segmentation of time series of cardiac CINE MRI volumes. I study the segmentation performance of two state-of-the-art neural network architectures 3D Autoencoder(AE) and 3D UNET. The problem is challenging since the datasets are huge and collected from 100 patients with different kind of heart conditions. These patients are also scanned in different MRI scanners with different scanning parameters giving rise to variation in contrast. Overall, the UNET is found to be better performing than AE. The semantic segmentation helps the medical experts to compute ejection fraction of a patient which explains any abnormality in heart functioning.

## Dataset
Dataset

I obtain cardiac MRI data from the MICCAI 2017 ACDC challenge [4]. It consists of cardiac CINE MRI of 100 patients with ground truth segmentation done by experts. The acquisitions were obtained over a 6 year period using two MRI scanners of different magnetic strengths (1.5 T (Siemens Area, Siemens Medical Solutions, Germany) and 3.0 T (Siemens Trio Tim, Siemens Medical Solutions, Germany)). Cine MR images were acquired in breath hold with a retrospective or prospective gating and with a SSFP sequence in short axis orientation. Particularly, a series of short axis slices cover the LV from the base to the apex, with a thickness of 5 mm (or sometimes 8 mm) and sometimes an interslice gap of 5 mm (then one image every 5 or 10 mm, according to the examination). The spatial resolution goes from 1.37 to 1.68 mm2/pixel and 28 to 40 images cover completely or partially the cardiac cycle (in the second case, with prospective gating, only 5 to 10% of the end of the cardiac cycle was omitted), all depending on the patient.

The 100 patients are evenly divided into 5 classes with well-defined characteristics according to physiological parameters. The different subgroups are given hereunder:

NOR: Examination with normal cardiac anatomy and function. The ejection fraction is greater than 50%, the wall thickness in diastole is lower than 12 mm, the LV diastolic volume is below 90 mL/m2 for men and 80 mL/m2 for women.

MINF: Patients with a systolic heart failure with infarction. Subjects have an ejection fraction below 40% and abnormal myocardial contractions. Some subjects have a high diastolic LV volume due to a remodeling of the LV to compensate for the myocardial infarction.

DCM: DCM: Patients with dilated cardiomyopathy have an ejection fraction below 40%, a LV volume greater than 100 mL/m2 and a wall thickness in diastole smaller than 12 mm. As a consequence of dilated LV, some patients of this category have a dilated RV and/or a high LV mass.

HCM: Patients with hypertrophic cardiomyopathy, i.e. a normal cardiac function (ejection fraction greater than 55%) but with myocardial segments thicker than 15 mm in diastole. In this category, patients can present abnormal cardiac mass indices with values above 110 g/m2.

ARV: Patients with abnormal right ventricle have a RV volume greater than 110 mL/m2 for men, and greater than 100 mL/m2 for women, or/and a RV ejection fraction below 40%. Almost every subject in this subgroup has a normal LV.


