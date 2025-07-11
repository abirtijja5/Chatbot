## Install de python 3.9
---
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
  libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
  libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
---
### Install pyenv
curl https://pyenv.run | bash

export PATH="$HOME/.pyenv/bin:$PATH"

### Install Python 3.9
pyenv install 3.9.18

### installation de l'env RASA
pyenv virtualenv 3.9.18 rasa_env


---
### Activation de l'env RASA
rasa init 

### Rentré dans l'env
pyenv activate rasa_env
 
---
### workflow
faire modif sur data/nlu.yml
rasa train
rasa shell