# microwatt_ubuntu_20
Implementation of Microwatt in Ubuntu 20

sudo apt install python3-pip
pip3 install virtualenv requests
export PATH=$PATH:/home/$USER/.local/bin

mkdir ~/.virtualenvs && cd ~/.virtualenvs
python3 -m venv libresoc
sudo apt install python3.8-venv
source ~/.virtualenvs/libresoc/bin/activate

pwd
/home/santhosh/libresoc

git clone https://gitlab.com/nmigen/nmigen.git
git clone https://gitlab.com/nmigen/nmigen-boards.git

git clone https://gitlab.com/nmigen/nmigen-soc
cd nmigen
pip install wheel
python setup.py develop

cd nmigen-boards
python setup.py develop

cd nmigen-soc
python setup.py develop

git clone https://gitlab.com/openpowerfoundation/openpower


