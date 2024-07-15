FROM apache/airflow:2.7.2-python3.8

ADD requirements.txt .
USER root

# Install dependencies
RUN apt-get update \
  && apt-get install -y --no-install-recommends \
         gcc \
         heimdal-dev \
         procps \
         ant \
  && apt-get autoremove -yqq --purge \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*


USER airflow
RUN pip install -r requirements.txt

CMD ["webserver"]
