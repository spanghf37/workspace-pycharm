FROM rapidsai/rapidsai-dev:22.06-cuda11.5-devel-ubuntu20.04-py3.9

COPY ../../requirements.txt /

RUN source activate rapids && \
    python -m pip install -r requirements.txt
