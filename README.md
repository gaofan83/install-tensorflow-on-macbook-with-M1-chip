#### Install tensorflow on macbook with M1-chip to play with deep learning
#####
I learned how to install tensorflow, matplotlib, pandas, jupyter notebook from [this youtube video](https://www.youtube.com/watch?v=vDPa0MYcPLg).

##### Below are the codes to use. When prompted to enter tensorflow virtual environment, I used `/Users/fangao/tf_macos`
```
brew install libjpeg
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/apple/tensorflow_macos/master/scripts/download_and_install.sh)"
cd tf_macos
source ./bin/activate
pip install --upgrade pip
pip install cython
git clone https://github.com/pandas-dev/pandas.git
cd pandas
python3 setup.py install
pip install matplotlib
pip install notebook
```

##### Fix some codes for Jupyter notebook
```
cd /Users/fangao/tf_macos/lib/python3.8/site-packages/ipykernel
vi eventloops.py
### Replace the line
return sys.platform == 'darwin' and V(platform.mac_ver()[0]) >= V('10.9')
### With the new line
return sys.platform == 'darwin' and V(platform.mac_ver()[0]) >= V('10.9') and platform.mac_ver()[2] != 'arm64'
### Save the edited file
```
##### Start Jupyter notebook
```
cd
jupyter notebook
```
