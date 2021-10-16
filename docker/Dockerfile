FROM pytorch/pytorch:1.9.0-cuda11.1-cudnn8-runtime
WORKDIR /tgdlf
COPY enn /tgdlf/enn
COPY grid_configuration.py /tgdlf
COPY grid_data_v2.py /tgdlf
COPY grid_LSTM.py /tgdlf
COPY train_decay_loss.py /tgdlf
COPY util.py /tgdlf
COPY requirements.txt /tgdlf
RUN pip install -r requirements.txt && python /tgdlf/enn/setup.py install
CMD /bin/bash
