# Lecture Notebooks  
* Lecture notebooks are organized by classes, in each respective folder.  
* The `requirements.txt` file can be used to install all the necessary packages for all the notebooks in this course.

------------------
#### Note: As detailed below, multiple steps are necessary to run pyspark locally. We recommend trying out *Vocareum* before setting up locally, since the environment is already up and running there.


## Option 1: Docker
1. Install Docker from https://docs.docker.com/get-docker/. MAKE SURE TO DOWNLOAD THE APPROPRIATE ONE FOR YOUR OPERATING SYSTEM.
2. Open Docker Desktop application. 
3. Also open Terminal and run the following command to install the image on your personal device: 
    ```bash
    docker pull jupyter/pyspark-notebook:x86_64-ubuntu-22.04
    ```
4. After the image is downloaded and installed, define your `HOSTDIR` on Terminal. This is the absolute path in your personal computer's filesystem to the Lecture Notebooks. So, this will be the location where you download/clone this GitHub repository. For example, if you clone this repository on Desktop, your path will be `~/Desktop/lecture-notebooks/`.
    ```bash
    HOSTDIR=~/Desktop/lecture-notebooks/
    ```
5. Finally, run the Docker image using the following command:
    ```bash
    docker run -p 8888:8888 -v $HOSTDIR:/home/jovyan docker.io/jupyter/pyspark-notebook:x86_64-ubuntu-22.04
    ```
6. This will generate a URL of the form: `http://127.0.0.1:8888/lab?token=<unique-token>`, where your Jupyter Server will be running. Just copy and paste this URL in your browser and it will launch the Jupyter Hub.

## Option 2: Anaconda
### To run pyspark locally, install Java, Spark and Python first if you don't have them already
You need both Java and python for pyspark to work locally. Follow the steps here (https://www.datacamp.com/tutorial/installation-of-pyspark) based on your operating system, to download & install Java and set up corrsponding Environment Variables.

After you have done the above, proceed to create a python environment for the course from the requirements.txt file given here.  

## Environment creation and installation
You're free to do this any other way if you're comfortable, but we recommend the below:
1) Install Anaconda from https://www.anaconda.com/download. You can refer to https://docs.anaconda.com/free/anaconda/install/index.html for installation instructions. MAKE SURE TO DOWNLOAD THE APPROPRIATE ONE FOR YOUR OPERATING SYSTEM.
2) Once anaconda is downloaded and the conda command is working in your terminal (refer to installation instructions), confirm that `conda activate base` command works (this should activate your base environment).
3) Run the following (replace \<your-environment-name> with a name for your environment, I used DSC232r):  
    ```bash
    conda create -n <your-environment-name> python=3.7.5
    conda activate <your-environment-name>
    ```
4) Make sure you have git installed, and an account with GitHub. Download this repository via git (https://github.com/ucsd-dsc232r-s24/lecture-notebooks.git). You can run the following command on terminal, in the location where you want to clone the repository.
    ```bash
    git clone https://github.com/ucsd-dsc232r-s24/lecture-notebooks.git
    ```
5) Navigate to the folder location where you have downloaded this repository. Then, run 
    ```bash
    pip install -r requirements.txt
    ```
This should create your environment with all necessary packages.