# Pill_Detection
This repository contains the detail procedure to train a model for Pill Detection. Upgradations are still in progress.

Step 1: ANNOTATION
- Collect the dataset and annotate it. 
- For annotation I have used "LabelImg" tool. 
    - Just clone the labelImg repo "https://github.com/heartexlabs/labelImg".
    - In "data/predefined_classes.txt" include the desired class name and save with the updates list of classes. 
    - run labelimg.py
    - .xml file will be separately for each image.

Step 2: CONVERSION FROM .xml TO .csv
- run xml_to_csv.py to save the annotated data in .csv format using the command: python xml_to_csv.py
- this will save a csv file with the name "pills_label.csv"

Step 3: SPLITTING THE LABELS 
- This will split the pill_labels.csv into train and test

Step 4: TRAINING
- mscoco_label_map.pbtxt is used as label map.
- A training pipeline is provided in training_pipeline.config.
- After training weights are saved in model/frozen_inference_graph.pb

Step 5: TESTING
- For testing, include all the testing images inside test folder. 
- On cmd, after directing to the path where "test.py" is situated and run test.py as: python test.py
