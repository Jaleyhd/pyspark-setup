# PySpark Installation Instruction for Ubuntu 14.04,16.04

The scripts mentioned bellow will work for most of the versions of ubuntu, however we have tested it for only 14.04 and 16.04. F Pyspark installation requires you to setup 

1. Hadoop on single node

2. Scala
3. Spark
4. Python


## Installing Hadoop



Step 1 : Download and unzip hadoop

```bash
mkdir ~/temp
cd ~/temp
wget https://dist.apache.org/repos/dist/release/hadoop/common/hadoop-2.7.2/hadoop-2.7.2.tar.gz
sudo mv hadoop-2.7.2.tar.gz /usr/local/hadoop
```



Step 2 : Give permissions to hadoop. Replace &lt;&lt;username&gt;&gt; in bellow script with your computer name and execute

```
sudo chown +R <<username>>:<<username>> /usr/local/hadoop
```

Step 3 : Move 



