
# Title: The influence of mild sleep deprivation and driving environment on the drivers' physiological state, situation awareness and takeover quality in conditionally automated driving

## Code of experiment: Exp4

## Abstract: 

Conditionally automated cars will soon be introduced into road traffic, with the aim of improving road safety. At this specific level of automation, the role played by the driving environment and driver fatigue has not yet been sufficiently addressed. Therefore, the objective of the study is to investigate the influence of the driving environment and driver fatigue on the driver's physiological state, situational awareness, and ability to take over control of the vehicle. A fixed driving simulator study was conducted with 63 participants. Each participant drove in a highly (urban area) and low (rural area) stimulating and stressful driving environment in a random order. Each scenario lasted 30 minutes and drivers were required to regain control of the vehicle at the end. The time of experiment and order of scenarios were controlled. In addition, half of the participants were slightly sleep deprived (less than 6 hours of sleep), in order to observe the effect of mild sleep deprivation added to the monotonous nature of automated driving (30 minutes observing the environment). Physiological signals (electrocardiogram (ECG), electrodermal activity (EDA) and respiration (RESP)) as well as driving data were collected during the whole experiment. Measures of self-reported fatigue, situational awareness, situational trust in the vehicle, and affective state were also collected at different times during the experiment.


## Description of experiment: 

All participants were asked to come in the day before the experiment to collect a sleep tracker (smart watch) and to be given instructions about their sleep (sleep deprived or not). The time of the experiment (10am or 4pm) was controlled to ensure that it did not impact on alertness levels. On the day of the experiment, participants first rated their level of fatigue and affective state (valence and arousal). Then they observed the car driving for 5 minutes, which was considered the baseline phase. Afterwards, the participants were able to test the simulator and learn about the principle of takeover request (TOR). Then, the main driving session consisted of two 30-minute scenarios in each of two environments (urban or rural). The order of the scenarios was controlled: half of the participants started with the rural, and the other half with the urban. Drivers were required to observe the environment, so that the task was monotonous and an increase in drowsiness could be observed. They also had to press a button on the steering wheel when a target (red circle) appeared on the screen every 5 minutes. After each scenario, participants rated their fatigue (before the takeover and after answering all the questions), their emotional state, their situational awareness at the time of the TOR, and their confidence in the car. Finally they rated their experience in the simulator at the end of the experiment. The experiment was conducted in French and German.

More details on the exprimental design and procedure, and material and instruments used can be found in [1].


## Experimental design:

4 Independent Variables (IV):
- Between-subjects factor(s):
	- Sleep deprivation: less than six hours of sleep the night before the experiment vs. more than seven hours : label_sleep
	- Scenario order: driving in rural area first vs. driving in urban area first : label_first_scenario
	- Time of experiment: 10:00am vs. 4:00pm : label_time_exp
- Within-subjects factor(s):
	- Driving environment: Rural area vs. urban area : period


## Experimental procedure: 

- Baseline (5 minutes) : Conditionally automated driving, driver monitors the environment  > label = Baseline
- Training session (5 minutes) : 3 fake takeover requests (TORs) + manual driving until the end of the 5 minutes > label = Training
- Driving session (around 1 hour) : Conditionally automated driving in 2 scenarios
	- A rural environment and a urban one > label = Block1, Block2 


## Material and instruments:

- Physiological signals: Recorded with BioPac Student Lab 3.7.7 software and the BioPac MP36 hardware at a sample rate of 1000 Hz. Lead sets (SS57LA and SS2LB, Biopac) with disposable Ag/AgCl pre-gelled electrodes (EL507 and EL503, Biopac) were, respectively, used to record the EDA and ECG of participants. Electrodes recording the EDA signal were placed on the distal phalanges of the middle and ring fingers of the non-dominant hand of participants. The SS5LB respiratory effort transducer (Biopac) recorded the respiration via chest expansion and contraction.

- Driving simulation: Fixed-base simulator with one car seat, a steering wheel (Logitech G27), and pedals (gas and brake). The driving simulation was displayed on a television screen (65"). The GENIVI software (Yosemite and SanFrancisco scene) was used as simulation software, for both driving and training phases [2]. The scenarios of the driving phase were modified to implement the same takeover situation in both scenes (a dog crossing the road from the right side).

- Questionnaires: 
	- Karolinska Sleepiness Scale (KSS) [3] to measure self-reported fatigue
	- Animated Self Assessment Manikin (AniSAM) [4] to assess the drivers' affective state (valence and arousal)
	- Situation Awareness Rating Technique (SART) [5] to measure the drivers' situation awareness in both takeover situations 
	- The Situational Trust Scale for Automated Driving (STS-AD) [6], to measure trust in the vehicle in both environments
	- User Experience Questionnaire Short version (UEQ-S) [7], to measure user experience in the driving simulator


## Changes to questionnaires: 

Questionnaires translated to Franch and German when no official translation existed.


## Folder and file structure:

/Raw: contains the raw collected data.

	/Physio: contains two folders with physiological data collected during the experiment
		/BioPac: contains the raw files (in .acq format) obtained with BioPac Student Lab 3.7.7 software and the BioPac MP36 hardware.
		/Txt: contains two .txt files for each driver, identified with the code. 
			<code>.txt: contains the raw physiological data extracted from the BioPac Student Lab. Each column contains the raw values collected with sensors for each signal (ECG, EDA. RESP) at a sampling rate of 1000Hz. The file contains metadata in the first 11 rows. Columns are separated with tabs. The first column is the elapsed time in minutes.
			<code>-markers.txt: contains the timestamps for each period of the experiment. Baseline = Baseline phase; Training = Practice phase in the driving simulator; BlockX = One block of the main driving session in conditionally automated driving (1 to 2). 
			Be careful, the timestamps are here in seconds while they are in minutes in the raw data.

	/Driving: contains raw driving data collected from the GENIVI software [2]. There are three files for each driver, identified by the code of the participant: one for the baseline and training phase (<code>_Training.txt), and one each driving scenario (<code>_City/Country.txt). City = Urban area, Country = Rural area.
	
	Metadata:
	Time = Time elapsed since the software was launched (in seconds)
	EngineSpeed = Engine speed (in rpm)
	GearPosActual = Current gear
	GearPosTarget = Next planned gear
	AcceleratorBrakePedalPos = Position of gas/brake pedal. Gas pedal is pressed when the value is between 0 and 1 (maximum acceleration), brake pedal is pressed when the value is between 0 and -1 (maximum braking). 0 means no pedal is pressed.
	SteeringWheelAngle = Steering wheel angle (in degrees)
	VehicleSpeed = Vehicle speed (in mph)
	Position X = Vehicle position along the x-axis in the simulated driving environment
	Position Y = Vehicle position along the y-axis in the simulated driving environment
	Position Z = Vehicle position along the z-axis in the simulated driving environment
	Autonomous Mode (T/F) = Autonomous pilot status. True = autonomous pilot activated, False = autonomous pilot deactivated (driver in control of the car)
	Events: Events that occurred during the driving simulation.
		TOR = visual icon and audio chime triggered to request the driver to take over control of the car (3 times in the training phase, and 1 time in each scenario)
		RT : <float> = Reaction time of the driver to press the steering wheel button after the display of the target on the screen (red circle). Used to assess drivers' vigilance.

	/Questionnaire: contains raw exports of the participants' answers to questionnaires, with one file for each language (German and French) in CSV format.

	/Sleep: contains the file used by experimenter to report the information collected by the sleep tracker. They were retrieved from the desktop fitbit application (Windows) after synchronising the watch.

	Metadata:
	- code: participant code
	- date: date of experiment
	- color_fitbit: color of sleep tracker
	- amount_sleep_hours_fitbit: actual sleep time recorded by the watch (h:mm format)
	- sleep_time: time at which the participant fell asleep according to the sleep tracker (hh:mm:ss format)
	- wake_up_time: time at which the participant woke up according to the sleep tracker (hh:mm:ss format)


/Preprocessed: contains preprocessed data.

	/Physio: contains physiological features processed with the Neurokit library in Python [8] for the main periods of the experiment (baseline, training, driving) and for the takeover situations. Each column corresponds to a physiological indicator. More details on the significance of each indictor can be found in physiological_indicators.xlsx or here: https://neuropsychology.github.io/NeuroKit/. Each indicator contains in its name the signal with which it has been calculated. The HRV indicators are calculated from the ECG, the RRV indicators are calculated from the RESP signal, and the RSA from the combination of the ECG and RESP signals.

		/scenario_type_no_tor: contains features calculated for both environments (Rural and urban areas) before the takeover occurred. The name of each file depends on the segmentation level (segm_1 : features calculated on the whole periods, segm_30 : signals segmented in 30 equal windows and features are calculated for each window). Segmentation levels available : 1, 2, 5, 10, 20, 30. The baseline phase is not segmented and features are always calculated once.

		/windows: contains features calculated for the driving phase, with sliding time windows with varying length and overlap. These datasets were generated on the data collected for each block of the experiment. The size of time window used (60, 180, 300 seconds) and the percentage of overlap with the previous window (0%, 25%, 50%) is specified in each file name.

		/takeover_interval: features calculated for time windows larger than 10 seconds. Each file is identified by the time considered before and after the takeover request (e.g., features_tor_<time_before>_<time_after>.csv)

		Metadata: 
		- subject_id : ID of participant
		- label_sleep : 0 = Not sleep deprived (A = Alert), 1 = sleep deprived (D = Drowsy)
		- label_first_scenario : Countryside (C; rural area) or Urban (U; urban area)
		- label_time_exp : 10 = 10:00am, 16 = 4:00pm
		- period: corresponding period of the experiment (Baseline, City (urban area) or Countryside (rural area))
		- segment_id : id of segment
		- time_start : time marker corresponding to the beginning of the window
		- time_end : time marker corresponding to the end of the window

		Code for indicators : _Bl = values during baseline; _Dr = values during current period; _Dr-Bl = values during current period corrected with baseline (subtraction).

	/Driving: contains takeover metrics for the takeover situation in each scenartio. The features calculated for time windows larger than 10 seconds. Each file is identified by the time considered before and after the takeover request (e.g., features_tor_<time_before>_<time_after>.csv)

		Metadata: 

		- TO_Decision : Decision of the driver for taking over control of the car. 1 = brake, 2 = steer the wheel, 3 = steer the wheel & brake, 4 = other (probably with button), NA = No takeover
		- TO_RT: Time elapsed in seconds between takeover request (TOR in the raw driving data) and actual take over by the driver (Autonomous Mode (T/F) to False in the raw driving data)
		- TO_MaxSWA : Maximum steering wheel angle between the takeover request and the reactivation of the autopilot
		- TO_ReengageTime : Time elapsed in seconds between the takeover request and the reactivation of the autopilot
		- TO_MaxBraking : Maximum value of the brake pedal position between the takeover request and the reactivation of the autopilot (0 = Pedal not pressed, 100 = Full brake)


	/Questionnaire: 
		Exp4_Database.csv: contains the raw data collected from the questionnaires and the tablet, inluding socio-demographic questions, measures of self-reported fatigue, affective state (valence and arousal), situation awareness, situational trust, user experience.
		Exp4_Documentation.xslx: contains a complete documentation for the data contained in the database. It includes terms and abbreviations, the participants to exclude for a statistical analysis (with the reason), and both the data and metadata variables (with variable name, type, description, range and coding)


	/PVT: contains CSV files with the participants' reaction time to targets on the psychomotor vigilance task (PVT). Participants had to press a steering wheel button when a red circle was displayed on the screen (every 5 minutes).
		data_PVT_exp4_scenario_type.csv : raw values of reaction time extracted from driving data (*Events* column), for both environments and for each participant.
		data_PVT_no_outliers_mean_sd.csv : processed values of reaction time where outliers were removed according to the mean and standard deviation of the data distribution (Threshold = Mean +/- 2*SD) [9].
		data_PVT_no_outliers_quantile.csv : processed values of reaction time where outliers were removed according to the 0.05 sample quantile (Lower threshold = q0.05, higher threshold = q0.95) [9].



References:

[1] Meteier, Q., Capallera, M., de Salis, E., Widmer, M., Angelini, L., Abou Khaled, O., Mugellini, E., & Sonderegger, A.. (2022). Influence of Mild Sleep Deprivation and Driving Environment on Driver State in Monotonous Conditionally Automated Driving. Transportation Research Part F: Traffic Psychology and Behaviour.

[2] GENVI Vehicle simulator. https://github.com/GENIVI/genivi-vehicle-simulator.

[3] Åkerstedt, T., & Gillberg, M. (1990). Subjective and objective sleepiness in the active individual. The International journal of neuroscience, 52 1-2, 29-37 .

[4] Sonderegger, A., Heyden, K., Chavaillaz, A., & Sauer, J.S. (2016). AniSAM & AniAvatar: Animated Visualizations of Affective States. Proceedings of the 2016 CHI Conference on Human Factors in Computing Systems.

[5] Taylor, R.M. (2017). Situational Awareness Rating Technique (SART): The Development of a Tool for Aircrew Systems Design.

[6] Holthausen, B.E., Wintersberger, P., Walker, B.N., & Riener, A. (2020). Situational Trust Scale for Automated Driving (STS-AD): Development and Initial Validation. 12th International Conference on Automotive User Interfaces and Interactive Vehicular Applications.

[7] Schrepp, M., Hinderks, A., & Thomaschewski, J. (2017). Design and Evaluation of a Short Version of the User Experience Questionnaire (UEQ-S). Int. J. Interact. Multim. Artif. Intell., 4, 103-108.

[8] Makowski, D., Pham, T., Lau, Z.J., Brammer, J.C., Lespinasse, F., Hung, P.T., Schölzel, C., & Chen, S.A. (2021). NeuroKit2: A Python toolbox for neurophysiological signal processing. Behavior research methods.

[9] Berger, A., & Kiefer, M. (2021). Comparison of Different Response Time Outlier Exclusion Methods: A Simulation Study. Frontiers in Psychology, 12.