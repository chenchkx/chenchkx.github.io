### anconda 下载
```
wget https://repo.continuum.io/archive/Anaconda3-2021.11-Linux-x86_64.sh
```
### anconda 安装
```
bash "Anaconda3-2021.11-Linux-x86_64.sh" -u
vim ~/.bashrc
  export PATH="/... 你的路径../anaconda3/bin/:$PATH"
  source activate
source ~/.bashrc

which python
python -V
```



### 虚拟环境创建

```
-----------py39+torch1.10.0+cu102--------------
conda create -n torch python=3.9
conda activate torch
pip install "/nfs4-p1/ckx/toolkits/torch-1.10.0+cu102-cp39-cp39-linux_x86_64.whl"
pip install "/nfs4-p1/ckx/toolkits/torchvision-0.11.1+cu102-cp39-cp39-linux_x86_64.whl"
pip install torch-scatter torch-sparse torch-cluster torch-spline-conv torch-geometric -f https://data.pyg.org/whl/torch-1.10.0+cu102.html
pip install "/nfs4-p1/ckx/toolkits/dgl_cu102-0.7.1-cp39-cp39-manylinux1_x86_64.whl"
pip install ogb
pip install seaborn
pip install openpyxl
conda install -c anaconda cudatoolkit=10.2

```
```
-----------py39+torch1.10.0+cu113--------------
conda create -n torch python=3.9
conda activate torch
conda install pytorch==1.10.0 torchvision cudatoolkit=11.3 -c pytorch
pip install dgl -f https://data.dgl.ai/wheels/cu113/repo.html
pip install ogb
pip install seaborn
pip install openpyxl
pip install torch-scatter torch-sparse torch-cluster torch-spline-conv torch-geometric -f https://data.pyg.org/whl/torch-1.10.0+cu113.html

pip install "/nfs4-p1/ckx/toolkits/dgl_cu113-0.7.1-cp39-cp39-manylinux1_x86_64.whl"

```




### ZSH终端安装

```
chsh -s /bin/zsh
重启session终端，然后选择(2)

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
sed -i '1i\export TERM=\"xterm-256color\"' ~/.zshrc
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="agnoster"/g' ~/.zshrc
sed -i 's/plugins=(git)/plugins=(git zsh-autosuggestions zsh-syntax-highlighting)/g' ~/.zshrc
source ~/.zshrc


注意：  git clone https: 如果报错 GnuTLS recv error (-54): Error in the pull function. 
git clone https:  改成-》  git clone git:
     

source ~/anaconda3/bin/activate
conda init zsh bash
conda config --set auto_activate_base True
```



### 清华镜像

```

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --append channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/fastai/
conda config --append channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --append channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --set show_channel_urls yes
ssl_verify: false


vim .condarc
按i 键
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
按Esc键
:wq
conda clean -i




```





