FROM datamechanics/spark:3.2.0-hadoop-3.3.1-java-11-scala-2.12-python-3.8-dm16

USER root

# Updating pip 
RUN pip install --upgrade pip

# Updating Anaconda
RUN conda update conda

# Updating Anaconda packages
RUN conda update --all

RUN conda install -y -c conda-forge nodejs jupyterlab jupyterhub spylon-kernel

RUN pip install jupyterlab-sparkmonitor findspark

RUN python -m spylon_kernel install

RUN ipython profile create && \
    echo "c.InteractiveShellApp.extensions.append('sparkmonitor.kernelextension')" >>  $(ipython profile locate default)/ipython_kernel_config.py

RUN chown -R 1000:1000 /home/sparkuser