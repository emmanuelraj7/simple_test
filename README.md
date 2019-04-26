# Upgrade simple model Python 

## What news? 
1. Add Python parser to work with Valohai.yaml
2. Unzip, untar example
3. Add log output path, saved path

## Unzip, untar

Because the datasets are **".tar.gz"** format so we need to unzip it before training.

We can unzip to any folder and tell Python where exactly our training data is. 

The Docker image is based on Ubuntu so we use bash script to unzip the file.

For example I unzip the train, val, test dataset to **tmp** folder by the command: 

```css
# Create 3 folder train, test, validation:

mkdir /tmp/train 
mkdir /tmp/test
mkdir /tmp/validation 

# Untar command: 

tar -xzf /valohai/inputs/train/train-set-images.tar.gz -C /tmp/train/
tar -zxf /valohai/inputs/test/test-set-images.tar.gz -C /tmp/test/
tar -zxf /valohai/inputs/validation/validation-set-images.tar.gz -C /tmp/validation/

```
## Note: 

* The _/valohai/inputs/_ folder is read-only, you can not unzip there.
* Our download dataset will not locate exactly in _/valohai/inputs/_ but it will be downloaded in seperated folder which the folder name is the **Name** you define in **valohai.yaml** file. See **inputs:** section in **valohai.yaml** file. 
* The _**parameters**_ in **valohai.yaml** is exactly the **Python argparse**. Take a look at _**keras-dvc-cnn-simple.py**_ file to know to how **parse** your arguments from outside to your python script.

Finally we have dataset and Python script ready to train. You can try to modify other Python file with argparse and valohai.yaml. Have fun! 



    
