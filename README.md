# pollution_with_images
Implementation for the experiments in "Learning Pollution Maps from Mobile Phone Images" paper, AI for Good track, IJCAI 2022.
Link to paper: https://www.ijcai.org/proceedings/2022/0697.pdf
The conda environment file is provided as **environment.yml**.

## Repository Structure
|
|
|___ code
|
|___ data (images for training and evaluation)
|
|___ govdata (government sensor data)

## Code Breakdown
code
|
|___ src (script files for training and data generation)
|
|___ notebooks (jupyter notebooks for augmentation and splitting of data, estimating error and evaluation)
|
|___ \*.csv (csv files containing image name and corresponding pm2.5 values)


### Scripts (code/src/)
The script **train_haze.py** can be run on all images (using all_data.csv) to train UNet with haze density for the LeUNet model.
The script **train_pm.py** is run to train the remaining models on the training data (train_data.csv).
In script **dehaze.py** we dehaze a single image, which can be used to find the haze density map for the corresponding image.

### Notebooks (code/notebooks/)
**data_split.ipynb** splits the data from China and New Delhi in 0.8:0.2 and 0.3:0.7 between train and test splits.
**augment_data.ipynb** augments the training data with random crops covering 50% area of images.
**error_estimate.ipynb** looks at government sensor data and does ground truth error estimation.
**evaluation.ipynb** evaluates performance of trained models on test data.
