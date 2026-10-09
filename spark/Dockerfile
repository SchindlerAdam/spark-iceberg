FROM apache/spark:4.1.3-scala2.13-java21-ubuntu

USER root

ARG ICEBERG_VERSION=1.12.0
ARG HADOOP_VERSION=3.4.2
ARG POSTGRES_VERSION=42.7.8
ARG AWS_SDK_VERSION=2.29.52

ADD https://repo1.maven.org/maven2/org/apache/iceberg/iceberg-spark-runtime-4.1_2.13/${ICEBERG_VERSION}/iceberg-spark-runtime-4.1_2.13-${ICEBERG_VERSION}.jar \
    /opt/spark/jars/

ADD https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/${HADOOP_VERSION}/hadoop-aws-${HADOOP_VERSION}.jar \
    /opt/spark/jars/

ADD https://repo1.maven.org/maven2/software/amazon/awssdk/bundle/${AWS_SDK_VERSION}/bundle-${AWS_SDK_VERSION}.jar \
    /opt/spark/jars/

ADD https://jdbc.postgresql.org/download/postgresql-${POSTGRES_VERSION}.jar \
    /opt/spark/jars/

RUN chown spark:spark \
    /opt/spark/jars/iceberg-spark-runtime-4.1_2.13-1.12.0.jar \
    /opt/spark/jars/hadoop-aws-3.4.2.jar \
    /opt/spark/jars/bundle-2.29.52.jar \
    /opt/spark/jars/postgresql-42.7.8.jar

USER spark