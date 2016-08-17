# PySpark Installation Instruction for Ubuntu 14.04,16.04

The scripts mentioned bellow will work for most of the versions of ubuntu, however we have tested it for only 14.04 and 16.04. F Pyspark installation requires you to setup

1. Installing java properly

2. Hadoop on single node

3. Scala

4. Spark

5. Python


---

## Java Setup

### Step 1 : Installing Java

```
sudo apt-add-repository ppa:webupd8team/java
sudo apt-get install oracle-java7-installer
```

### Step 2: Set the environment Variable

Put the bellow code at the end of .bashrc file. And inside the .profile file. It is located at  '~' or 'home' location. Also for ubuntu 16.04 users, you should carefully append this line int \/etc\/environment file. Please take the backup of this \/etc\/environment file before making any changes.

```
JAVA_HOME=/usr/lib/jvm/java-7-oracle
```

Add the path of java's bin folder in PATH variable. First try to add the following code at the end of .bashrc

```
PATH=$JAVA_HOME/bin:$PATH
source ~/.bashrc
```

If it doesn't work, try updating PATH and JAVA\_HOME in profilerc. For python, it seems that 16.04 has issues updating environment variable, therefore it is better that you edit \/etc\/environment file and add updated path in the location. Again, don't forget to take backup of this file, i.e \/etc\/environment

Do not use PATH=ABC:$PATH kind of format in \/etc\/environment, as .it can be fatal for your system. It will consider $ literally. Update PATH as follow in \/etc\/environment.

```
PATH=/usr/lib/jvm/java-7-oracle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
```

Now restart the system.

In case there are any reboot issues, open the machine without lightdm or display managers. Via cntl+alt+Fn+F2. Now revert the changes you did in \/etc\/environment via backup of the same file. And then type

```
sudo reboot
```

Please ping me at bugs.opensource@gmail.com , in case you have trouble setting up the environment variable.

> Note : Do not install oracle-java-9 for any reasons, because it seems to be incompatible with latest scala version available

---

## Hadoop Setup \(Limited Use\)

### Step 1 : Download and unzip hadoop-x.x.x.tar.gz

```bash
mkdir ~/temp
cd ~/temp
wget https://dist.apache.org/repos/dist/release/hadoop/common/hadoop-2.7.2/hadoop-2.7.2.tar.gz
tar -xvzf hadoop-2.7.2.tar.gz
sudo mv hadoop-2.7.2 /usr/local/hadoop
```

### Step 2 : Give permissions to hadoop. Replace &lt;&lt;username&gt;&gt; in bellow script with your computer name and execute

```
sudo chown +R <<username>>:<<username>> /usr/local/hadoop
```

### Step 3 : Add an environment variable.

Follow steps similar to adding JAVA\_HOME, just that instead of JAVA\_HOME, you will have to add HADOOP\_HOME

```
HADOOP_HOME=/usr/local/hadoop
```

and path needs to be updated in .bashrc,.profile as bellow :

```
PATH=$HADOOP_HOME/bin:$PATH
```

> Never update the PATH env variable in \/etc\/environment directly the way you modify other variables. Rather add the expanded path in the exisiting PATH env variable declaration as bellow
> 
> ```
> PATH=/usr/local/hadoop/bin:/usr/lib/jvm/java-7-oracle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
> ```

and finally reboot the system or source the ~\/.bashrc and ~\/.profile file, the get the changes reflected.

type 'hadoop', to see if the is returning any errors or not.

---

## Scala Setup \(Limited Use\)

### Step 1 : Download and unzip scala-x.x.x.tgz

```bash
cd ~/temp
wget http://downloads.lightbend.com/scala/2.11.8/scala-2.11.8.tgz
tar -xvzf scala-2.11.8.tgz scala-2.11.8
sudo mv scala-2.11.8 /usr/local/scala
```

### Step 2 : Give permissions to scala. Replace &lt;&lt;username&gt;&gt; in bellow script with your computer name and execute

```
sudo chown +R <<username>>:<<username>> /usr/local/scala
```

### Step 3 : Add an environment variable.

Follow steps similar to adding JAVA\_HOME, just that instead of JAVA\_HOME, you will have to add SCALA\_HOME

```
SCALA_HOME=/usr/local/scala
```

and path needs to be updated in .bashrc,.profile as bellow :

```
PATH=$SCALA_HOME/bin:$PATH
```

> Never update the PATH env variable in \/etc\/environment directly the way you modify other variables. Rather add the expanded path in the exisiting PATH env variable declaration as bellow
> 
> ```
> PATH=/usr/local/hadoop/bin:/usr/lib/jvm/java-7-oracle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
> ```

and finally reboot the system or source the ~\/.bashrc and ~\/.profile file, the get the changes reflected.

type 'hadoop', to see if the is returning any errors or not.

---

## Spark Setup \(Limited Use\)

### Step 1 : Download and unzip spark-x.x.x.tar.gz

```bash
mkdir ~/temp
cd ~/temp
wget https://dist.apache.org/repos/dist/release/hadoop/common/hadoop-2.7.2/hadoop-2.7.2.tar.gz
sudo mv hadoop-2.7.2.tar.gz /usr/local/hadoop
```

### Step 2 : Give permissions to hadoop. Replace &lt;&lt;username&gt;&gt; in bellow script with your computer name and execute

```
sudo chown +R <<username>>:<<username>> /usr/local/hadoop
```

### Step 3 : Add an environment variable.

Follow steps similar to adding JAVA\_HOME, just that instead of JAVA\_HOME, you will have to add HADOOP\_HOME

```
HADOOP_HOME=/usr/local/hadoop
```

and path needs to be updated in .bashrc,.profile as bellow :

```
PATH=$HADOOP_HOME/bin:$PATH
```

> Never update the PATH env variable in \/etc\/environment directly the way you modify other variables. Rather add the expanded path in the exisiting PATH env variable declaration as bellow
> 
> ```
> PATH=/usr/local/hadoop/bin:/usr/lib/jvm/java-7-oracle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
> ```

and finally reboot the system or source the ~\/.bashrc and ~\/.profile file, the get the changes reflected.

type 'hadoop', to see if the is returning any errors or not.

---

