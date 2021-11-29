# WA-53-21-Kremic

Programming Challenge for Job Application - ECG data classification

To build the Docker Image for Jupyter Lab ([source](https://github.com/jupyter/docker-stacks/tree/master/tensorflow-notebook)), set your Terminal's working directory to `/path/to/extracted/WA-53-21-Kremic`, and run the following command:

    docker build -t jupyter
    
Next, run:

    docker images
    
This should list your local Docker Images. It should look something like:

    REPOSITORY                    TAG         IMAGE ID       CREATED              SIZE
    jupyter                       latest      b48ba2a9f1f0   About a minute ago   7.02GB
    ...

Now, you can run a container with your jupyter image, with the following command:

    docker run -it -d -p 8888:8888 \
    --name docker-jl \
    -v /path/to/extracted/WA-53-21-Kremic/notebook:/home/jovyan/work \
    -e JUPYTER_ENABLE_LAB=yes \
    jupyter
    
The tag `-d` means that the container is running in detached mode, so in order to get the token, you should run:

    docker container logs docker-jl
    
Use the last link from the logs to start your Jupyter Lab instance.

## Using the ECG ipython notebook ([source](https://github.com/spdrnl/ecg))

Before you run the code, the instance needs an aditional Python library. Open the Container Terminal from the bottom of the Launcher tab, and enter the following command:

    pip install tensorflow_addons

Now we can finally run the code. In the Jupyter Lab instance, on the lefthand side, navigate into the `/work` directory, and start the **ECG.ipynb** notebook. From the context menu at the top, you can try `Kernel -> Restart Kernel and Run All`, or play around with the code yourself.
