FROM python:3.7-slim
RUN  apt-get update \
  && apt-get install -y wget \
  && rm -rf /var/lib/apt/lists/*
RUN pip install kfserving
RUN pip install tritonclient[all] --extra-index-url=https://pypi.ngc.nvidia.com  
COPY bert_transformer_v2 bert_transformer_v2/bert_transformer_v2
COPY setup.py bert_transformer_v2/setup.py
WORKDIR bert_transformer_v2
RUN pip install -e .
ENTRYPOINT ["python", "-m", "bert_transformer_v2"] 
