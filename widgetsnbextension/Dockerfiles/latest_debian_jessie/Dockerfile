#Dockerfile for building widgetsnbextension
FROM ppc64le/python:2.7
MAINTAINER ajay gautam <agautam@us.ibm.com>
ENV PATH /root/miniconda2/bin:$PATH
RUN apt-get -y update \

# Install miniconda
	&&  wget https://repo.continuum.io/miniconda/Miniconda2-4.3.14-Linux-ppc64le.sh -O miniconda.sh &&\
    bash miniconda.sh -b config --set always_yes yes --set changeps1 no --set show_channel_urls true \
	&& conda update conda -y && conda install conda-build -y  && rm -rf Miniconda2-4.3.14-Linux-ppc64le.sh \

#clone recipe and build from it
	&& git clone https://github.com/AnacondaRecipes/widgetsnbextension-recipe.git && cd widgetsnbextension-recipe \
	&& conda build recipe
CMD ["python", "/bin/bash"]
