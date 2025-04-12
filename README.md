# Team7_LambdaLegends_PythonHackathon_APRIL25 - Numpy Ninja Python Hackathon

# Virtual env
Go to your workspace folder anf execute below to create virtual env to run jupyter code.
python -m venv ./venv
source venv/bin/activate

# Treadmill Maximal Exercise Tests from the Exercise Physiology and Human Performance Lab of the University of Malaga

## Abstract
The present database is an ensemble of the cardiorespiratory measurements acquired during 992 treadmill maximal graded exercise tests (GET) performed in the Exercise Physiology and Human Performance Lab of the University of Malaga. Heart rate, oxygen consumption, carbon dioxide generation, and pulmonary ventilation are measured on a breath-to-breath basis along with the treadmill speed during maximal effort tests. Participants are amateur and professional athletes are of ages ranging from 10 to 63 years old. The age, height, and weight of the participants are provided, as well as the temperature and humidity during the test.

## Background
Cardiac and respiratory data measured during graded exercise tests are key measures to calculate several cardio-respiratory indices used in sport science [1] and medicine [2,3]. All the parts of the oxygen consumption and heart rate dynamics during a GET are of interest: the rate of increase at exercise onset [4], the slope during exercise [5,6], the maximal values [7,8], the dynamics changes at ventilatory thresholds [9,10], the nonlinear dynamics during effort [11–13], and finally the dynamics during recovery [14,15]. The study of each of these segments of the oxygen consumption or heart rate dynamics during effort has led to indices used to characterize and predict health, fitness, or performance, such as ventilatory thresholds, heart resting rate, rate of heart rate increase, deflection point of the performance curve, etc. But comparisons between existing calculation methods for these indices are lacking, and reproducibility of the calculation is sometimes hindered by the lack of available open-source code. The goal of this dataset is then two-fold: To facilitate the publication and diffusion of calculation methods and associated code to analyze cardiorespiratory measurements of maximal exercise tests; To encourage studies comparing different calculation methods of indices derived from the cardio-respiratory measurements acquired during effort tests, such as ventilatory thresholds or heart rate recovery.

## Methods
The measurements were taken between 2008 and 2018. The athletes performed a maximal Graded Exercise Testing (GET) on a PowerJog J series treadmill connected to a CPX MedGraphics gas analyzer system (Medical Graphics, MN, USA) with breath-by-breath measurements of respiratory parameters -including oxygen consumption and pulmonary ventilation- and heart rate collected by a Mortara 12-lead ECG device.

The stress tests consisted of a continuous (ramping) or step-by-step incremental effort. Most of the exercise phases are preceded by a warmup period of walking at 5 km/h. When incremental, the step amplitudes range from 0.5 to 1 km/h. The participants were asked to go beyond exhaustion, and the test was considered maximal if the oxygen consumption was saturated. The effort was then ceased, and to avoid vasovagal syncope, the treadmill speed was set back to the initial 5 km/h speed, and the participant was asked to walk.

Exercise testing was voluntary, and before its initiation, written informed consent was obtained from the participants and the legal guardians of those under 18 years of age. All effort tests were performed under the supervision of a doctor in sport science, and their analysis was carried out according to the principles of the Declaration of Helsinki. The study protocols were approved by the Research Ethics Committee of the University of Málaga.

## Data Description
The dataset contains two files:

* subject-info.csv contains the participant info at the time of the test. The variable ID identifies a participant, whereas the variable ID_test identifies an exercise test. This file contains 992 lines, one for each test. The different variables are described in the table below, with their corresponding amount or median [Inter Quartile Range] value.

| variable | value |
|----------|----------|
| ID_test	 | 992 |
| ID| 857 | 
| Age |27.10 [21.10, 36.32] |
| Weight (kg)	 | 73.00 [66.00, 80.23] |
| Height (cm)	| 175.00 [170.00, 180.00] | 
| Humidity (%) |47.00 [42.00, 54.00] |
|Temperature (°C) | 22.90 [20.80, 24.40] |
|Sex = 1 (Female) (%) | 149 (15.0) |
	
	
	
* test_measure.csv, contains all the cardiorespiratory measurements taken during each effort test. The data is in long format, so the file contains one line for each breath measurement for all of the 992 effort tests, resulting in the 575087 lines present in the file. The time of each measurement is identified by the variable time indicating the seconds elapsed since the effort test start, the exercise test is identified by the ID_test variable, and the variable ID indicates the participant. These effort tests contain a median [Inter Quartile Range] of 580 [484, 673] measures, for a median duration of 1093.00 [978.75, 1208.00] seconds. The variables in this file are:
time	Time since the measurement starts, in seconds
Speed	Speed of the treadmill, in km/h
HR	Heart rate, in beat per min
VO2	Oxygen consumption, in mL/min
VCO2	Carbon dioxide production, in mL/min
RR	Respiration rate, in respiration per minute
VE	Pulmonary ventilation, in L/min
ID	Participant identification
ID_test	Effort test identification
Note that VO2, VCO2, and VE measures are missing for 30 tests.

## Usage Notes
ID_test, the variable identifying the GET, is named from the ID of the participant paired with the GET index. For example, ID_date = 245_3 is the third exercise test of participant ID = 245. An example of calculation in R [16] of simple heart rate recovery and cardiorespiratory index from these files is provided in an associated GitHub repository [17].
