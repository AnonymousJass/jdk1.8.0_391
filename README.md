#Now we need to click on the download button and let the download finish. Usually the downloads files stored on our Downloads directory. Now lets open our terminal and navigate to /usr/lib/jvm (If our system doesn't have any of Java versions then we need to create this jvm directory under /usr/lib manually by using sudo mkdir -p /usr/lib/jvm command) by using following command:

cd /usr/lib/jvm

sudo unzip -r jdk1.8.0_391.zip

#After all files extracted we need to navigate to our newly de-compressed directory (jdk1.8.0_321) by using following command:

cd jdk1.8.0_391

#Here we need to set the java path to do so we need to change the environmental variables. We need to edit the file by text editor like Nano, so we run the following command to edit the file:

sudo nano /etc/environment

/usr/lib/jvm/jdk1.8.0_391/bin:/usr/lib/jvm/jdk1.8.0_391/db/bin:/usr/lib/jvm/jdk1.8.0_391/jre/bin

#In the above screenshot we had highlighted the modified part of default file. Now we save and close this file by using CTRL+X then Y then Enter ⤶ key.

# Now we will install OpenJDK 8 as an alternative, so that we can change our Java versions easily as per our requirement. We need to use following command:

sudo update-alternatives --install  "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_391/bin/java" 0

#After that we will set Java compiler by using following command:

sudo update-alternatives --install  "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_391/bin/javac" 0

#Now we can set Java OpenJDK 8 by using following command:

sudo update-alternatives --set java /usr/lib/jvm/jdk1.8.0_391/bin/java

#Also for the Java compiler we use following command:

sudo update-alternatives --set java /usr/lib/jvm/jdk1.8.0_391/bin/javac

#Now we are ready to rock. Let choose our Java version by using following command from anywhere of our terminal:

sudo update-alternatives --config java

#In the above screenshot we can clearly see that our Java version 8 is on the number 2, and the Java version 11 is on number 0. So we just need to run the above command to switch between Java versions. Here we are going to use Java OpenJDK8, so here we need to type 2 and hint ENTER ⤶ button

#Now we are using Java 8, as we can see the output of java -version command

java -version

