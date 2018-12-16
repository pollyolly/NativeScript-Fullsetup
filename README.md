# NativeScript-Fullsetup

Install required libraries:
<pre>
sudo apt-get install lib32z1 lib32ncurses5 libbz2-1.0:i386 libstdc++6:i386
</pre>
Note: the command above may fail, you can proceed to the next procedure.

G++ Compiler:
<pre>
sudo apt-get install g++
</pre>
Install JDK 8:

<pre>
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
</pre>

Set JAVAHOME system environment:

export JAVA_HOME=$(update-alternatives --query javac | sed -n -e 's/Best: *\(.*\)\/bin\/javac/\1/p')

Download the SDK tools only:
<pre>
creat a folder and download the sdk tool.
cd /root/android/sdk/ | 
$:/root/android/sdk/ curl -O "copy the link of linux sdk tools zip file here from android downloads..."
</pre>

Note: it will generate the <b>tools</b> folder

Copy these lines inside ubuntu /root/.bashrc:
<pre>
export ANDROID_HOME=$HOME/android/sdk
export PATH=${PATH}:$ANDROID_HOME/tools
export PATH=${PATH}:$ANDROID_HOME/tools/bin
export PATH=${PATH}:$ANDROID_HOME/platform-tools
export PATH=${PATH}:$ANDROID_HOME/platform-tools/adb
</pre>

Inside your /android/sdk/tools/bin run this command:
<pre>
sdkmanager "tools" "emulator" "platform-tools" "platforms;android-28" "build-tools;28.0.3" "extras;android;m2repository" "extras;google;m2repository"
</pre>
Check your configuration:
<pre>
tns doctor
</pre>
