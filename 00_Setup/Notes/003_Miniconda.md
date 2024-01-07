# [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)

- [Miniconda](#miniconda)
  - [Linux](#linux)
    - [Download \& Install](#download--install)
      - [Option 1](#option-1)
        - [Command list](#command-list)
      - [Option 2](#option-2)
        - [Command list](#command-list-1)
      - [Option 3](#option-3)
    - [Create/Activate/Deactivate/Remove](#createactivatedeactivateremove)
      - [Command list](#command-list-2)
    - [Disable/Deactivate Base Env by default](#disabledeactivate-base-env-by-default)
      - [Option 1](#option-1-1)
        - [Command list](#command-list-3)
      - [Option 2](#option-2-1)
        - [Command list](#command-list-4)
    - [Delete Miniconda](#delete-miniconda)
  - [Windows](#windows)
  - [MacOS](#macos)

## Linux

### Download & Install

#### Option 1

* [Download & Install](https://docs.conda.io/projects/miniconda/en/latest/)

![Miniconda_Command_Line](../Images/001_Software_List/Miniconda_Command_Line.png)

##### Command list

```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh

~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh  (optional)

source ~/.bashrc
```

* Steps

![003_Option_1.1](../Images/003_Miniconda/003_Option_1.1.png)
![003_Option_1.2](../Images/003_Miniconda/003_Option_1.2.png)

#### Option 2

* [Download & Install](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html)

![003_Option_2_Command_Line](../Images/003_Miniconda/003_Option_2_Command_Line.png)

##### Command list

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
source ~/.bashrc
```

* Steps

![003_Option_2.1](../Images/003_Miniconda/003_Option_2.1.png)
![003_Option_2.2](../Images/003_Miniconda/003_Option_2.2.png)
Press space key to scroll screen or q key to the end

![003_Option_2.3](../Images/003_Miniconda/003_Option_2.3.png)
![003_Option_2.4](../Images/003_Miniconda/003_Option_2.4.png)
![003_Option_2.5](../Images/003_Miniconda/003_Option_2.5.png)
![003_Option_2.6](../Images/003_Miniconda/003_Option_2.6.png)

#### Option 3

* Download (mirror or browser)

```
wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

* Download from browser

[Miniconda home](https://repo.anaconda.com/miniconda/)
[Miniconda tsinghua mirror](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/)

### Create/Activate/Deactivate/Remove

#### Command list

```
conda info --envs
conda create -n my_virtual_conda_env python=3.11
conda activate my_virtual_conda_env
conda deactivate
conda remove --name my_virtual_conda_env --all
```

* Steps

![003_Virtual_Env_Create_1](../Images/003_Miniconda/003_Virtual_Env_Create_1.png)
![003_Virtual_Env_Create_2](../Images/003_Miniconda/003_Virtual_Env_Create_2.png)
![003_Virtual_Env_Activate](../Images/003_Miniconda/003_Virtual_Env_Activate.png)
![003_Virtual_Env_Deactivate_Remove_1](../Images/003_Miniconda/003_Virtual_Env_Deactivate_Remove_1.png)
![003_Virtual_Env_Deactivate_Remove_2](../Images/003_Miniconda/003_Virtual_Env_Deactivate_Remove_3.png)
![003_Virtual_Env_Deactivate_Remove_3](../Images/003_Miniconda/003_Virtual_Env_Deactivate_Remove_3.png)

### Disable/Deactivate Base Env by default

#### Option 1

##### Command list

`conda config --set auto_activate_base false`

or

```
vi ~/.condarc
auto_activate_base: false
```

#### Option 2

##### Command list

```
1. vi ~/.bashrc

2. comment out all lines below

# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/home/kz/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/home/kz/miniconda3/etc/profile.d/conda.sh" ]; then
        . "/home/kz/miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/home/kz/miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<

3. source ~/.bashrc
```

* Deactivate base env once

![003_Base_Env_Deactivate](../Images/003_Miniconda/003_Base_Env_Deactivate.png)

### Delete Miniconda

* [Deactivate base env by default](#disabledeactivate-base-env-by-default)
* Delete installation folder
  e.g.
  `rm -rf ~/miniconda3/`

## Windows

## MacOS