# mnist examples, read and write data to an HDFS path
CLASSPATH=$($HADOOP_HDFS_HOME/bin/hadoop classpath --glob) python convert_to_records.py --input_directory MNIST_data --output_directory hdfs://plusplus-mac:9000/mnist/data

CLASSPATH=$($HADOOP_HDFS_HOME/bin/hadoop classpath --glob) python mnist_train.py --input_dir hdfs://plusplus-mac:9000/mnist/data --log_dir hdfs://plusplus-mac:9000/mnist/checkpoint/mnist
