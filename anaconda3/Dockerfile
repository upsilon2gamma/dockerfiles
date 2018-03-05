from continuumio/anaconda3

ENV UPDATED_AT=1508515909

VOLUME ["/opt/notebooks"]

RUN /opt/conda/bin/conda update conda -y
RUN /opt/conda/bin/conda update anaconda -y
RUN /opt/conda/bin/conda install jupyter -y
RUN /opt/conda/bin/conda install -c anaconda opencv -y

RUN useradd -ms /bin/bash anaconda
USER anaconda
WORKDIR /home/anaconda
RUN mkdir .jupyter
# http://jupyter-notebook.readthedocs.io/en/stable/public_server.html
# generate password hash in python and copy it to `jupyter_notebook_config.json`
#  In [1]: from notebook.auth import passwd
#  In [2]: passwd()
#  Enter password:
#  Verify password:
#  Out[2]: 'sha1:67c9e60bb8b6:9ffede0825894254b2e042ea597d771089e11aed'
COPY jupyter_notebook_config.json .jupyter

ENTRYPOINT /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser
