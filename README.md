## Brain Tumor Segmentation
A brain tumor is a mass or growth of abnormal cells in your brain.Many different types of brain tumors exist. Some brain tumors are noncancerous (benign), and some brain tumors are cancerous (malignant). Brain tumors can begin in your brain (primary brain tumors), or cancer can begin in other parts of your body and spread to your brain as secondary (metastatic) brain tumors.

How quickly a brain tumor grows can vary greatly. The growth rate as well as the location of a brain tumor determines how it will affect the function of your nervous system.

Brain tumor treatment options depend on the type of brain tumor you have, as well as its size and location.


### Dataset Link
Brain MRI segmentation: https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation

### Requirements:
To get started with the project make sure you have python installed.
Install your dependencies: <br>
```pip install -r requirements.txt``` <br>
Now you get the full list of your dependencies with <br>
 ```pip freeze -r requirements.txt``` or
 ```pip freeze > requirements.txt```

### Folder Setup:
Here is a detailed folder setup to help you get started

brain-tumor-segmentation (Main Project Folder) 📁
- dataset 📁
- - kaggle_3m
- - lgg-mri-segmentation
- venv 📁
- flask_app 📁
- README.md
- notebook.ipynb


creating a virtual env:
1. `python -m venv venv` (project folder path\venv)
2. To activate: `.\venv\Scripts\activate.ps1` 
3. Install the req packages: eg `pip install tensorflow` (without venv do: pip install tensorflow --user)

### GPU support for tensorflow
- configuration: https://www.youtube.com/watch?v=hHWkvEcDBO0
- On windows in virtual environment terminal run
 `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted` 
- ``` pip list``` to see all packages
- `pip cache purge` to clear pip cache
- Please make sure of your tensorflow version and if it supports Cuda
 `tf.test.is_built_with_cuda()`
- using tensorflow 2.10.0 for python version 3.10.6
`pip install tensorflow==2.10.0 `

- Finally run code to check gpu availability:
``` 
import tensorflow as tf

print("TensorFlow version:", tf.__version__)
# Get the list of available GPUs
gpus = tf.config.list_physical_devices('GPU')
if gpus:
  for gpu in gpus:
    print("GPU detected:", gpu)
else:
  print("No GPU detected")

# Check if TensorFlow is using the GPU
print("Is TensorFlow using GPU?", tf.test.is_built_with_cuda())
print("Is GPU available for TensorFlow?", tf.test.is_gpu_available()) 
```



### Flask App
Flask app can be found in the flask_app folder
To run the app:
`python app.py`