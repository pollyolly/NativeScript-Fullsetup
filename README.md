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
<pre>
export JAVA_HOME=$(update-alternatives --query javac | sed -n -e 's/Best: *\(.*\)\/bin\/javac/\1/p')
</pre>
Create folder and download the sdk tools:
<pre>

mkdir android/sdk
cd /root/android/sdk/
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

Running in Android
<pre>
tns run android --bundle
</pre>

Important: you might experience <b> unexpected identifier app.js </b> if forgot to add --bundle option.

# Troubleshooting

Configure JVM heap size
<pre>
Environment Variables:

Variable name: _JAVA_OPTIONS 
Varialble value: -Xmx500m

Or add <b> org.gradle.jvmargs=-Xmx500m </b>
in C://Users/<your-name>/.gradle/gradle.properties
  
</pre>

Configure SQLite database
<pre>
new CopyWebpackPlugin([
    { from: { glob: "fonts/**" } },
    { from: { glob: "**/*.+(jpg|png)" } },
    { from: { glob: "assets/**/*" } },
    {from: "**/*.db"} //Adding this line for the files ending with .db to be recognize
                      //when using db.copyDatabase('sample.db')
</pre>
