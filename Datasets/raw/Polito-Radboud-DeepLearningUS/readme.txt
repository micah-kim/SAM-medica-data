This readme.txt file was generated on 2021-07-05 by Francesco Marzola

Uploaded by: Kristen M. Meiburger
Date: July 2021

Users are free to download and use this database and code, but if you use this data for your own work, please cite the original paper where results from the study are published: 

Francesco Marzola, Nens van Alfen, Jonne Doorduin, Kristen M. Meiburger, Deep learning segmentation of transverse musculoskeletal ultrasound images for neuromuscular disease assessment, Computers in Biology and Medicine, 2021, 104623, ISSN 0010-4825, https://doi.org/10.1016/j.compbiomed.2021.104623.

GENERAL INFORMATION

1. Title of Dataset: Deep learning segmentation of transverse musculoskeletal ultrasound images for neuromuscular disease assessment

2. Author Information
	A. Principal Investigator Contact Information
		Name: Kristen M. Meiburger
		Institution: Biolab, PolitoBIOMedLab, Department of Electronics and Telecommunications, Politecnico di Torino, Turin, Italy
		Address: Corso Duca degli Abruzzi, 24, 10129 Torino ITALY
		Email: kristen.meiburger@polito.it

	B. Co-investigator Contact Information
		Name: Francesco Marzola
		Institution: Biolab, PolitoBIOMedLab, Department of Electronics and Telecommunications, Politecnico di Torino, Turin, Italy
		Address: Corso Duca degli Abruzzi, 24, 10129 Torino ITALY
		Email: francesco.marzola@polito.it

	C. Co-investigator Contact Information
		Name: Nens van Alfen
		Institution: Department of Neurology, Donders Institute for Brain, Cognition and Behavior, Radboud University Medical Center, Nijmegen, The Netherlands
		Address: Houtlaan 4, 6525 XZ Nijmegen, The Netherlands
		Email: Nens.vanAlfen@radboudumc.nl

	D. Co-investigator Contact Information
		Name: Jonne Doorduin
		Institution: Department of Neurology, Donders Institute for Brain, Cognition and Behavior, Radboud University Medical Center, Nijmegen, The Netherlands
		Address: Houtlaan 4, 6525 XZ Nijmegen, The Netherlands
		Email: Jonne.Doorduin@radboudumc.nl

3. Date of data collection (single date, range, approximate date) : 2003-

4. Geographic location of data collection <latitude, longiute, or city/region, State, Country, as appropriate>: Radboud University Medical center, Nijmegen, The Netherlands

5. Information about funding sources that supported the collection of the data: /


SHARING/ACCESS INFORMATION

1. Licenses/restrictions placed on the data: Open Access, MIT licence on shared code

2. Links to publications that cite or use the data: https://doi.org/10.1016/j.compbiomed.2021.104623.

3. Links to other publicly accessible locations of the data: /

4. Links/relationships to ancillary data sets: /

5. Was data derived from another source? no

6. Recommended citation for this dataset: Francesco Marzola, Nens van Alfen, Jonne Doorduin, Kristen M. Meiburger, Deep learning segmentation of transverse musculoskeletal ultrasound images for neuromuscular disease assessment, Computers in Biology and Medicine, 2021, 104623, ISSN 0010-4825, https://doi.org/10.1016/j.compbiomed.2021.104623.


DATA & FILE OVERVIEW

1. File List: 
	- BB, GM, TA (folders):
		- Healthy:
			-Images: .png files of original US images from healthy subjects
			-Masks: .png files of manual segmentations, binary masks
			-characteristics.xlsx : subjects informations (ID, age, length, weigth, sex)

		- Pathological:
			-Images: .png files of original US images from pathological subjects
			-Masks: .png files of manual segmentations, binary masks
			-characteristics.xlsx : subjects informations (ID, age, length, weigth, sex)

	- Results:
		- Att_Unet_resnet50, FPN_resnet50_DiceLoss, Unet_resnet50_DiceLoss, UnetPlusPlus_resnet50_DiceLoss (folders):
			- Test_output, Train_output, Val_output : outputs of the specific network in the specified subset, binary masks
			- best_model.pth : best performing model on the validation set

		- U-Upp-FPN-Att: 
			- Train_output, Val_output, Test_output: Averaged output of the 4 models, binary masks
			- Train_output_processed, Val_output_processed, Test_output_processed: Averaged output of the 4 models, post processed with post_process_muscleNet.m, binary masks
			- Train_overlay, Val_overlay, Test_overlay: Overlay of manual and automatic masks with original image(color code: green=TP, red=FN, yellow=FP)

	- Segmentation_models: 
			- data: 
				- MuscleCNN: data to be fetched during training, derived from BB, GM, TA
			- main.py : script to run to reproduce results
			- Models.py, myclasses.py, myLosses.py, network_models.py : scripts used by main.py
			- requirements.txt : libraries used for runninng main.py

	- LICENSE.txt : original license in https://github.com/qubvel/segmentation_models.pytorch

	- Subjects_mean_gray_level_zscore.xls/csv : calculated mean gray level from automatic or manual segmentation

	- MATLAB : 
		- EnsembleModel.m : matlab script to merge different networks outputs
		- post_process_muscleNet.m : matlab script to process ensemble model output
		- SegmentationMetrics.m : matlab script to extract metrics to evaluate performances

2. Relationship between files, if important: /

3. Additional related data collected that was not included in the current data package: /

4. Are there multiple versions of the dataset? no


METHODOLOGICAL INFORMATION

1. Description of methods used for collection/generation of data: 
Images were acquired by experienced neurodiagnostic technicians (5-10+ years of experience), using an Esaote® MyLab Twice (Esaote SpA, Genoa, Italy) device, with a 3-13 MHz linear broadband transducer and a fixed preset (gain 50%, general mid frequency setting, fixed depth of 40 or 60 mm depending on the muscle protocol, focus at 40 mm depth, image enhancers off). 

2. Methods for processing the data: 
Train new models or load and test uploaded models using main.py. Post-process outputs using EnsembleModel.m or post_process_muscleNet.m and extract performance using SegmentationMetrics.m 

3. Instrument- or software-specific information needed to interpret the data: 
Cuda capable GPU, MATLAB

4. Standards and calibration information, if appropriate: /

5. Environmental/experimental conditions: requirements.txt

6. Describe any quality-assurance procedures performed on the data: /

7. People involved with sample collection, processing, analysis and/or submission: 

	- Kristen M. Meiburger, Francesco Marzola, Nens van Alfen, Jonne Doorduin
