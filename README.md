# reproducibility-tutorial
Assembling the genome Plasmodium falciparum. 
## Computer Setup 
#Download miniconda installer    
 wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
-install silently
 bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda

# Make sure all conda packages will be in path by symbolic links to /bin
 ln -s /opt/conda/pkgs/*/bin/* /bin
 ln -s /opt/conda/pkgs/*/lib/* /usr/lib

# Install Jupyter lab version 1.2.3
 /opt/conda/bin/conda install -c conda-forge -y jupyterlab=1.2.3
 /opt/conda/bin/conda install -c conda-forge -y nodejs=10.13.0


 /opt/conda/bin/pip install bash_kernel
 /opt/conda/bin/pip install ipykernel
 /opt/conda/bin/python3 -m bash_kernel.install

#Test JupyterLab
 /opt/conda/bin/jupyter lab --no-browser --allow-root --ip=0.0.0.0 --NotebookApp.token='' --NotebookApp.password='' --notebook-dir='/scratch/reproducibility-tutorial/'

#Install Snakemate
 /opt/conda/bin/conda search -c bioconda snakemake
 /opt/conda/bin/conda install -c bioconda -c conda-forge -y snakemake=5.8.1

#make sure all conda packages will be in path by symbolic links to /bin
 ln -s /opt/conda/bin/* /bin
 ln -s /opt/conda/lib/* /usr/lib

#Install Docker
 #update ubuntu apt-get package manager
  sudo apt-get update
 #install some needed packages 
  sudo apt-get install -y \apt-transport-https \ca-certificates \curl \gnupg-agent \software-properties-common

 #add the docker key 
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -   

 #add the repository 
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

 #update apt-get with new repository information   
  sudo apt-get update

 #install docker    
  sudo apt-get install -y docker-ce docker-ce-cli containerd.io

 #Test docker
  docker run hello-world
 
