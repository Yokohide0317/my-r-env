FROM condaforge/miniforge3:23.3.1-1

RUN mamba create -n r431_env r-base=4.3.1 python=3.11 r-IRkernel jupyterlab -y

RUN echo "conda activate r431_env" >> ~/.bashrc
ENV PATH /opt/conda/envs/r431_env/bin:$PATH

RUN R -e "IRkernel::installspec(name = 'ir431', displayname = 'r431_docker')"
RUN R -e "install.packages(c('dplyr', 'ggplot2', 'pandoc', 'BiocManager', 'devtools'), repos='http://cran.rstudio.com/')"

RUN conda clean -i -t -y