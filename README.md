# Legged_gym-Installation

   Last update 2023.12.29 by Daegeol Ko, UNIST

   <h3><strong>Before you start, you have to check install Anaconda and Graphic Driver</strong></h3>

   code by https://github.com/leggedrobotics/legged_gym

   code by https://github.com/Improbable-AI/walk-these-ways

# 1. Install basic environment

  ### 1.  make conda environmnet to execute legged gym with python 3.8

  ```
  conda create -n <env_name> python=3.8
  ```
  in here, for example, <env_name> is ‘legged_gym’. You can type only some name

### 2. install pytorch and cuda version in conda environment

  ```
  pip3 install torch==1.10.0+cu113 torchvision==0.11.1+cu113 torchaudio==0.10.0+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
  ```
  if you have any problem with cuda and pytorch, you have to set these for your graphic card

# 2. Install Isaac gym

### 1. Install Isaac gym

#### a. Download and install Isaac Gym Preview 4 from https://developer.nvidia.com/isaac-gym

#### b. click join now button. Then you have to sign in. after log in, click agree button and download it.

Click Member area and agree it.

#### c. lastly, extract it at Home

### 2. execute Isaac gym

#### a. open terminal,and directory is Home

```
cd isaacgym/python && pip install -e .
cd examples && python 1080_balls_of_solitude.py
```

In this step, you have to meet <h4>ModuleNotFoundError: No module named 'isaacgym'</h4> without this error, you must have problem with graphic driver error. 

So, when you meet other error, you have to type 
```
nvidia-smi
```
and check output is right.

#### b. Solving ModuleNotFoundError: No module named 'isaacgym'

you have to 
```
pip install gym 
```
twice. In Home dir and isaac gym dir.

this error be occured, because Isaacgym creator makes it run at python version 3.11. so we have to change it for our conda python version. So, we install it home and  solving crash.

# 3. Install rsl_rl (PPO implementation)

### It has problem when they update rsl_rl version 1.2.0 → 2.0.0.
### So, now we just use rsl_rl 1.2.0 in this Repository

```
git clone https://github.com/Lab-of-AI-and-Robotics/Legged_gym-Installation
cd rsl_rl && git checkout v1.0.2 && pip install -e .
```

if you meet error that there is no git, then 

```
pip install git
```


### 1. Install legged_gym

```
git clone https://github.com/leggedrobotics/legged_gym
cd legged_gym && pip install -e .
```

### 2. identify execute

in home directory,

```
cd legged_gym
python legged_gym/scripts/train.py –task=anymal_c_flat
```

then you have to meet many error. Below is manual that can solve errors.

### 3. AttributeError: module 'numpy' has no attribute 'float'. 

```
setup numpy version with your python version.
pip install numpy==1.23.0
```

### 4. ModuleNotFoundError: No module named 'tensorboard'

```
pip install tensorboard
```

### 5. AttributeError: module 'distutils' has no attribute 'version'

```
pip install setuptools=59.5.0
```

# 4. walk-these-ways

this is advanced from legged_gym

at home,

```
git clone https://github.com/Improbable-AI/walk-these-ways
cd walk-these-ways
pip install -e .
```



 


