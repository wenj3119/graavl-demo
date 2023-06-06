# graavl-demo
graavl简单使用
## GraalVM Native Support

### Download GraalVM
```
bash <(curl -sL https://get.graalvm.org/jdk)
```
* [graalvm github](https://github.com/graalvm/graalvm-ce-builds/releases/tag/vm-22.3.2)
* 在上面地址下载自己操作系统对应的版本即可

### 配置JAVA_HOME
```
# 命令，打开/etc/profile文件
sudo vim /etc/profile

# 内容，在/etc/profile文件中添加
export JAVA_HOME=[上面下载的Graalvm解压的地址] eg：/opt/jdk/graalvm-17
export JRE_HOME=$JAVA_HOME/jre
export CLASSPATH=.:$JAVA_HOME/lib:$JRE_HOME/lib:$CLASSPATH
export PATH=$PATH:$JAVA_HOME/bin

# 命令，使上面内容生效
source /etc/profile
```
### 安装native-image

```
# 到上面下载的graavlvm的bin目录下,执行如下命令
./gu install native-image
# 安装相关依赖，我这里是linux系统执行如下命令，其他操作系统参考下面链接
sudo apt-get install build-essential libz-dev zlib1g-dev
```
https://www.graalvm.org/latest/reference-manual/native-image/

```
$ ./gradlew nativeCompile
```
Then, you can run the app as follows:

```
$ build/native/nativeCompile/graavl-demo
```

```
cd build/native/nativeCompile
./graavl-demo
```


# 对比
## jar包启动
![image](https://github.com/wenj3119/graavl-demo/assets/49096108/49443685-a0bb-4a47-8e33-41cff35a77a8)


## native-image方式启动
![image](https://github.com/wenj3119/graavl-demo/assets/49096108/e6a4d659-4110-428d-a058-c7d8f25f5963)
