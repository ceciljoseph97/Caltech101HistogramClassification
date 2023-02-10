# **Image Classification of Caltech101 Dataset( Histogram Data )**
Caltech-101 contains a total of 9,146 images, split between 101 distinct object categories (faces, watches, ants, pianos, etc.) and a background category. 

### **Dataset Distribution**

We can observe that the Faces category has the highest number of images as 870. And the lowest number of images as low as 31. Such an imbalanced dataset is one of the major reasons for the bad performance of deep neural networks and other general classifiers.

### **Run Strategies:**
**`Options`**
1. `Run Classifiers with K-fold Strategy(Training|Testing).`
2. `Run Classifiers with Stratified K-fold Strategy(Training|Testing).` 
3. `Run SVM with [3, 5, 10, 15, 20, 25, 30] images per class for training.`

for the options 1 and 2, below classifiers used and performance is observed:
1. `Multi-layer Perceptron (MLP) Classifier.`
2. `SVM Classifier.`
3. `Random Forest Classifier.`
4. `KNN Classifier.`
5. `Logistic Regression Classifier.`
6. `LightGBM Classifier.`

**Dataset consideration**
1. Original Dataset
2. Dataset after Removing the `BACKGROUND_Google` Class.(noise class).

**Some general Observation**
1. Training|Testing Strategy have high impact in classifier performance.
2. `random_state` has considerable impact in classifier performance.
3. `[3, 5, 10, 15, 20, 25, 30..]` images per class for training showing increase in accuracy but after the training split `30` classifier seems to get overfitted and accuracy flatlines. This is due to the imbalanced dataset and in the frequency plot we can see minimum number of images in a class is 31 and max is 870, which will impact the classifier performance considerably.
4. SVM classifier is showing good promise in terms of computational cost and accuracy => Reason for choosing SVM over other for train split scenario.

### **Requirements:**
`Images.csv`: Contains the images which are represented by an image ID and the corresponding
class.<br>
`EdgeHistogram.csv`: Contains the feature data, Edge Histogram feature data for the images (Dimension of 80).

### **installation and Deployment**
For a local installation, make sure you have pip installed and run:<br>
    
    pip install notebook
**Note**: Use conda environment to ease up the setup and future environment setups.

    conda create --name <envname> --file requirements.txt
    conda activate testing
Install the necessary dependencies:

    python -m pip install -r requirements.txt

Running in a local installation
Launch with:

    jupyter notebook 

if using google colab: Just run the cells.
