# how_to_install_opencv430_for_java_on_linux_because_it_is_hard_for_some_reason
Documents my one day of figuring out how to compile and run opencv on ubuntu

# Instructions
## try the guide
https://www.360learntocode.com/2020/05/install-opencv-in-linuxubuntu-for-java.html

## if cmake java tests aren't successful - paths might be different
export ANT_HOME=/usr/share/ant
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/

## link jar library to vscode project
https://www.youtube.com/watch?v=3Qm54znQX2E

## test code:

import org.opencv.core.Core;
import org.opencv.core.CvType;
import org.opencv.core.Mat;

public class App {
   public static void main( String[] args ) {
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
        Mat mat = Mat.eye(3, 3, CvType.CV_8UC1);
        System.out.println("mat = " + mat.dump()); 
    }
}

# if Exception in thread "main" java.lang.UnsatisfiedLinkError: no opencv_java453.so in java.library.path: [/usr/java/packages/lib, ...
sudo cp opencv-453.jar /lib
sudo cp libopencv_java453.so /lib
