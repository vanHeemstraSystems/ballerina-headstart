# 300 - Installing on Linux

[Download the DEB file or RPM file](https://ballerina.io/downloads) and double-click on it to launch the installer. The installer guides you through the installation process and installs the Ballerina distribution to ```/usr/lib64/ballerina```.

***Info***: Alternatively, you can use either of the below commands to install Ballerina using the downloaded DEB or RPM file. Replace the ```<ballerina-home>/<ballerina-binary>.deb``` or ```<ballerina-home>/<ballerina-binary>.rpm``` with the actual file path.

For the DEB file:

```dpkg -i <ballerina-home>/<ballerina-binary>.deb ```

For the RPM file:

```rpm -i <ballerina-home>/<ballerina-binary>.rpm ```

If you would like to run the commands for ballerina from another directory then the directory in which the executable resides, add the executable to the environment variable PATH.

See the current paths as follows:

```$ echo $PATH```

Now add the ballerina executable to the path, as follows:

```$ export PATH=$PATH:/usr/lib64/ballerina```

Again check the path:

```$ echo $PATH```

To learn how to set the path permanently, see https://opensource.com/article/17/6/set-path-linux
