## How to Run Lane Durst & Connor Morris' Project Code

These instructions were written for someone with a computer running Windows 10 (or 11); certain steps may differ if you attempt to follow this guide on a Linux or macOS machine.

### Installing Dependencies
1. An install of Python version 3.8 is required for this code to be run.
2. An install of Jupyter Notebook linked to the Python 3.8 installation is required.
3. With Python 3.8 installed, run the following commands, in order, within a terminal window that has access to the Python 3.8 installation:
    - py -3.8 -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
    - py -3.8 -m pip install wheel==0.38.4 setuptools==66.0.0
    - py -3.8 -m pip install stable-baselines3==1.8.0 --no-cache-dir
    - py -3.8 -m pip install opencv-python
    - py -3.8 -m pip install --upgrade wheel setuptools
    - py -3.8 -m pip install gym-super-mario-bros
    - py -3.8 -m pip install tensorboard

[NOTE: Explanations for each of these commands are contained in the main.ipynb file under the section titled 'A Note About Dependencies'.]

### Running The Code
1. Open the Jupyter Notebook file 'main.ipynb' within the /src/ folder of this repository.

2. Run the code blocks under the 'Imports' section in order.

(If you would like to view a version of the environment with random inputs instead of an AI model, run the 'Default Code w/ Random Inputs' section.)

3. Run the code blocks under the 'Preprocessing the Environment' section in order.

(If you would like to vizualize what the frame stacking looks like, you can run the code blocks in the 'Frame Stack Vizualization Code' secion; however, make sure to run the state = env.reset code block if you wish to continue on.)

4. Run the code blocks under the 'Saving the Model' section in order.
    - At the moment, the code is set to store the model files and log files in a new folder in your C:\ drive called '4444_AI_files'. If you wish to store the files somewhere else, simply change the directory location listed in the second code block.

5. Run the code blocks under the 'Training the Model' section in order.
    - At the moment, the code is set to run for 10 million timesteps; this will take a long time to run unless you have an extremely powerful computer. If you want to reduce the number of timesteps without manually interrupting the learn method, simply change the value of the variable 'total_timesteps' in the second code block to a more reasonable number.

[NOTE: Upon running the first code block in the 'Training the Model' section, the output should state 'Using Cuda device below'; if it doesn't, then the model is training without any GPU acceleration. This will massively increase the time it takes to train the model, so it's recommended that you ensure you followed the Dependency Install Guide properly and have PyTorch with CUDA support installed.]
    
6. Finally, run the code blocks under the 'Testing the Created Models' section in order.
    - Currently, the code is set to initalize the final 10 million timestep model. If you want to load an alternative model, simply change the first code block with 'best_model_10000000' to the name of a different model file.

[NOTE: If you changed the storage directory in Step 3, make sure you update the 'model = PPO.load(...)' line in the first code block to include the new directory.]

### Viewing the Tensorboard Log File
Viewing the TensorBoard log file is fairly simple, it consists of 3 steps:
1. Open a new terminal window and navigate to the directory where the log file is stored.
2. Run the command 'tensorboard --logdir=.'
3. Copy the provided link and paste it into a browser.

[NOTE: The TensorBoard command will exit if the 'CTRL+C' hotkey is used. This is the same hotkey for copying text on Windows, so make sure to either highlight & right-click to copy the link or manually type the link in yourself.]