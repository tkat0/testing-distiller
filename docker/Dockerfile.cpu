FROM python:3.6.7

RUN pip install --upgrade pip

# https://github.com/NervanaSystems/distiller/tree/ee1d160f75bd171d8f9b8afd17a65bcb0327a623
ENV PYTHONPATH /opt/distiller:${PYTHONPATH}
RUN git clone --single-branch https://github.com/NervanaSystems/distiller.git /opt/distiller && \
    cd /opt/distiller && \
    git checkout ee1d160 && \
    pip install -r requirements.txt

ENV PYTHONPATH /work/:${PYTHONPATH}
ENV JUPYTER_PATH ${PYTHONPATH}:${JUPYTER_PATH}