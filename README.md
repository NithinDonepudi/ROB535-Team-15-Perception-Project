# ROB535-Team-15-Perception-Project
 This Project contains the files of Team-15 from ROB 535- Self Driving cars-Perception and Control of Fall 2021. This Team Consists of:

 1)Nithin Donepudi
 
 2)Barry Thierno
 
 3)Daksh Narang
 
 4)Kaifan Yue
 
 5)Faris Tulbah
 
 As a part of this project, we are required to detect/classify vehicles from a GTA V dataset. The dataset contains 10204 snapshots, where 7573 of them are used for training and the other 2631 are used for testing. Each snapshot contains an RGB image, a point cloud, the camera matrix, and a list of 3D bounding boxes (only for trainval). There is only one vehicle in each snapshot.
 
Each *bbox.bin file contains an array with 11 columns. Each row contains information of a bounding box: rotation vector, position (centroid x, y, z), size of the bounding box (length, width, height), class id, and a flag. The mapping from class id to the type of vehicle is provided in classes.csv

# How To Run Our Code
The code is distributed among four primary .ipynb files namely:

1)preprocesstrain.ipynb

2)preprocesstest.ipynb

3)catboostmodel.ipynb

4)graphinference.ipynb

## Dependencies

While I have included the import statements for all and intall statements for some particular dependencies. At the end of the day thee following are what you will need:

1)TensorFlow

2)Numpy

3)Keras

4)Matplotlib

5)CatBoost

6)PIL

7)Glob

8)csv

9)Pandas


## Step-By-Step

**NOTE**: I have already ran most of these steps and put the resulting files on the GitHub, However Just in case you want to know how these files were produced, I am including those steps as well. Alternatively, To see our Output **Skip to Step 3**.

**Step 1)** Using the the graphinference.ipynb file running the code cell by cell you should be able to obtain all the ".tsv" files required for preprocessing the training and the testing sets. One of the file dependencies this program has is the frozen model, this can be easily downloaded online, additionally I have put it in this GitHub Repo. One thing that might be a cause of irritation is the Tf version compatibility, but I have added code to fix these errors.

**Step 2)** Once we have all the files required to preprocees our models, we excute the preprocesstrain.ipynb and preprocesstest.ipynb files cell-by-cell. As long as all the file dependencies obtained from the previous step are present, this should not be a problem. At the end of this step, we should obtain a train and test ".tsv" file.

**Step 3)** This is the gradient Boosting step, here we are feeding the preprocessed model that has been sent through three different kinds of CNN's to be boosted. We are Using the CatBoost Algorithm in this particular Scenario. After running the code Cell by cell we will end up with a ".csv" containing the guid and the label of the image in the requested format.

