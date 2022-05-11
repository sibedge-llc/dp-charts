FROM datamechanics/spark:3.2.0-hadoop-3.3.1-java-11-scala-2.12-python-3.8-dm16

RUN wget -O /opt/spark/jars/postgresql-42.3.4.jar https://repo1.maven.org/maven2/org/postgresql/postgresql/42.3.4/postgresql-42.3.4.jar

COPY ./requirements.txt ./requirements.txt 
RUN /opt/conda/bin/pip install --quiet --no-cache-dir -r ./requirements.txt
