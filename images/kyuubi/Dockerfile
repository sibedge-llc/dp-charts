FROM apache/kyuubi:master-snapshot

RUN wget -O /opt/kyuubi/jars/postgresql-42.3.4.jar https://repo1.maven.org/maven2/org/postgresql/postgresql/42.3.4/postgresql-42.3.4.jar
RUN wget -O /opt/kyuubi/jars/hadoop-aws-3.3.2.jar https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.2/hadoop-aws-3.3.2.jar
RUN wget -O /opt/kyuubi/jars/aws-java-sdk-bundle-1.12.210.jar https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.210/aws-java-sdk-bundle-1.12.210.jar

RUN wget -O /opt/kyuubi/externals/spark-3.2.1-bin-hadoop3.2/jars/postgresql-42.3.4.jar https://repo1.maven.org/maven2/org/postgresql/postgresql/42.3.4/postgresql-42.3.4.jar
RUN wget -O /opt/kyuubi/externals/spark-3.2.1-bin-hadoop3.2/jars/hadoop-aws-3.3.1.jar https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.1/hadoop-aws-3.3.1.jar
RUN wget -O /opt/kyuubi/externals/spark-3.2.1-bin-hadoop3.2/jars/aws-java-sdk-bundle-1.12.210.jar https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.210/aws-java-sdk-bundle-1.12.210.jar