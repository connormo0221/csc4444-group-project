## This project was completed by Lane Durst & Connor Morris ###

### Dependency Install Guide ###

1. An install of python 3.8 is required for this code to be run
2. An install of jupyter notebook is required for the code to be run
3. Run the following commands in a terminal window that has access to the python 3.8 installation
    - py -3.8 -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
    - py -3.8 -m pip install wheel==0.38.4 setuptools==66.0.0
    - py -3.8 -m pip install stable-baselines3==1.8.0 --no-cache-dir
    - py -3.8 -m pip install opencv-python
    - py -3.8 -m pip install --upgrade wheel setuptools
    - py -3.8 -m pip install gym-super-mario-bros
    - py -3.8 -m pip install tensorboard
[NOTE: explanations for what each of these command do are detailed within the main.ipynb file in the section titled 'List of libaries, websites, and other resources referenced for this project:']

### Running The Code ###
1. run the section named 'Imports'

(if you would like to view the random input version of the environment, run the Default Code w/ Random Inputs section)

2. run the code blocks within the 'Preprocessing the Environemnt' section [there are two of these code blocks]

(if you would like to vizualize what the frame stacking looks like you can now run the code blocks in the 'Frame Stack Vizualization Code' secion, though make sure to run the state = env.reset code block if you wish to continue on)

3. run the code blocks in the 'Code For Saving The Model' section
    - at the moment the code is set to store the model files and log files in a new folder in your C: drive called 4444_AI_files. If you wish to store them somewhere else, simply change this directory to something more appropriate

4. run the code blocks in the 'Training the Model Section'
    - at the moment the code is set to run for 10 million timesteps, this may take a long time to run. If you want to reduce the number of timesteps without manually interrupting the learn method, simply reduce the number in the 'total_timesteps = 10000000' line to a more reasonable number
[NOTE: this should say Using Cuda device below the initial code block, if it does not it will use your CPU instead of your GPU and will likely be much slower]
    
5. Run the 'Testing the Created Models' section of the code
    - currently the code is set to initalize the final, 10 million timestep model, if you want to load an alternative model, simply change 'best_model_10000000' to a different model file in the first code block
[NOTE: if you changed the storage directory in step 3, make sure you update the 'model = PPO.load(...)' line to include the new directory]


### Viewing the Tensorboard Log File ##
viewing the tensorboard log file is fairly simple, it consists of 3 steps
1. open the terminal and navigate to the directory where the log file is stored
2. run the command 'tensorboard --logdir=.'
3. Copy the provided link and paste it into a browser
[NOTE: the tensorboard command will exit if the 'CTRL+C' hotkey is used. This is the same hotkey for copying text on windows, so make sure to either highlight, right click, and copy or simply manually type in the link]