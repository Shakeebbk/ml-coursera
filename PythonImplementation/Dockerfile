FROM continuumio/miniconda

WORKDIR /opt/notebooks

COPY requirements.txt ./
RUN apt install -y python-setuptools python-pip
RUN pip install --no-cache-dir -r requirements.txt

ENV TINI_VERSION v0.6.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /usr/bin/tini
RUN chmod +x /usr/bin/tini
ENTRYPOINT ["/usr/bin/tini", "--"]

RUN /opt/conda/bin/conda install jupyter -y --quiet

EXPOSE 8888
CMD ["/opt/conda/bin/jupyter", "notebook", "--allow-root", "--notebook-dir", "/opt/notebooks", "--ip", "0.0.0.0", "--port", "8888", "--no-browse"]
