# Eclipse, OpenCV, C++ and Ubuntu        

Configuring OpenCV with Visual Studio seemed painful to me  and Visual Studio sucks RAM which  makes your PC slow. Some people try  codeblocks which is faster as it is a lightweight IDE. But trying  something different is not that bad! I will share ins and outs of  configuring OpenCV with Eclipse CDT bundle (C/C++ Development Tool) in  Ubuntu.

### Step 1: Install JDK

1.1 # [Download Oracle JDK ](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)and  extract wherever you want to to keep. Let’s assume the path is  something like “/home/user/jdk1.7.0_80” where ‘user’ is your pc user  name.

1.2 # Set path variable by editing bashrc file:

`$ gedit .bashrc`

Copy the following lines any where in the file (I usually put at the bottom) and do the  changes as for your path.

`export JAVA_HOME="/home/user/jdk1.7.0_80" `

`export PATH=${JAVA_HOME}/bin:$PATH`

This change will be effective after running the following command.

`$ source .bashrc`

1.3 #  Finally check java version whether it shows the newly added java version or not:

`$ java -version `

I have JDK8 and this command shows me something like –

`java version "1.8.0_77" Java(TM) SE Runtime Environment (build 1.8.0_77-b03) Java HotSpot(TM) 64-Bit Server VM (build 25.77-b03, mixed mode) `

If it shows your desired java version,  then you have successfully installed jdk. Other wise check again whether  you missed anything or you can try other way to install Oracle JDK.  Here is some other ways to do so:  https://www.digitalocean.com/community/tutorials/how-to-install-java-on-ubuntu-with-apt-get

### Step 2: Install Eclipse CDT  

There is a package called `eclipse-cdt` in the Ubuntu repositories, this is what we want. If you haven’t got `g++` already, you need to install that as well, so all you need is:

`sudo apt-get install eclipse eclipse-cdt g++`

### Step 3: Prerequisite to install OpenCV in Ubuntu  

[Missing any of the following packages will affect running OpenCV properly ,  so be sure the packages are installed.]

3.1 # Open up a terminal and update the apt–get  package manager followed by upgrading any pre-installed packages:

`$ sudo apt-get update $ sudo apt-get upgrade `

3.2 # Now we need to install our developer tools:

`$ sudo apt-get install build-essential cmake git pkg-config`

The pkg–config   is likely to be already installed, but be sure to include it just in  case. [If we  pull down the OpenCV from git repository then we need git,  otherwise not] . The  cmake  package is used to configure our build.

3.3 # OpenCV needs to be able to load  various image file formats from disk, including JPEG, PNG, TIFF, etc. In  order to load these image formats from disk, we’ll need our image I/O  packages:

`$ sudo apt-get install libjpeg8-dev libtiff4-dev libjasper-dev  libpng12-dev`

3.4 # At this point, we have the ability  to load a given image off of disk. But how do we display the actual  image to our screen? The answer is the GTK development library, which  the highgui  module of OpenCV depends on to guild Graphical User Interfaces (GUIs):

`$ sudo apt-get install libgtk2.0-dev`

 3.4  # We can load images using OpenCV, but what about processing video  streams and accessing individual frames? We’ve got that covered here:

`$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev`

 3.5 # Install libraries that are used to optimize various routines inside of OpenCV:

`$ sudo apt-get install libatlas-base-dev gfortran`

###  Step 4: OpenCV 3.0.0 and OpenCV Contrib 3.0.0  

[Opencv Contrib  repository is intended for development of so-called “extra” modules,  contributed functionality. New modules quite often do not have stable  API, and they are not well-tested. Thus, they shouldn’t be released as a  part of official OpenCV distribution, since the library maintains  binary compatibility, and tries to provide decent performance and  stability.]

4.1 # Download OpenCV from here: <http://opencv.org/downloads.html>

4.2 # Download OpenCV Contrib from here: <https://github.com/Itseez/opencv_contrib/releases>

[Important:  Please match the versions of OpenCV and Contrib! Choosing version by  stability and availability of resources is recommended. I will show  using version 3.0.0]

4.3 # Extract both downloaded files in anywhere you prefer.

4.4 # Create a  directory, which we, for example, denote as <cmake_binary_dir>,  where you want to put the generated Makefiles, project files as well the  object files and output binaries.

`$ cd <cmake_binary_dir>  `

`$ cmake -DOPENCV_EXTRA_MODULES_PATH=<opencv_contrib_directory>/modules  <opencv_source_directory>`

[Example: In my case, I put those two extracted folders, in <cmake_binary_dir> and my cmake command was like: `$ cmake -DOPENCV_EXTRA_MODULES_PATH=opencv_contrib-3.0.0/modules opencv-3.0.0`]

Now use the following commands to finish the installation.

`$ make -j5`

`$ sudo make install`

 

### Step 5: Create a simple OpenCV C++ Project in Eclipse

[PS: Pictures used in this section are taken from opencv forum]

5.1 # Start Eclipse.

5.2 # Go to **File -> New -> C/C++ Project**![Eclipse Tutorial Screenshot 0](http://docs.opencv.org/2.4/_images/a0.png)

5.3 # Choose a name for your project (i.e. DisplayImage). An **Empty Project** should be okay for this example.  Leave everything else by default. Press **Finish**.

![Eclipse Tutorial Screenshot 1](http://docs.opencv.org/2.4/_images/a1.png)

5.4 # Your project (in this case DisplayImage) should appear in the **Project Navigator** (usually at the left side of your window).

![Eclipse Tutorial Screenshot 3](http://docs.opencv.org/2.4/_images/a3.png)

5.5 # Now, let’s add a source file using OpenCV:

![Eclipse Tutorial Screenshot 4](http://docs.opencv.org/2.4/_images/a4.png)

 

5.6 #

- Right click on **DisplayImage** (in the Navigator). **New -> Folder** .
- Name your folder **src** and then hit **Finish**
- Right click on your newly created **src** folder. Choose **New source file**:
- Call it **DisplayImage.cpp**. Hit **Finish**

 

![Eclipse Tutorial Screenshot 7](http://docs.opencv.org/2.4/_images/a7.png)

 

 So, now you have a project  with a empty .cpp file. Let’s fill it with some sample code (in other  words, copy and paste the snippet below):

```
#include <stdio.h>
#include <iostream>
#include "opencv2/core.hpp"
#include "opencv2/highgui.hpp"
using namespace std;
using namespace cv;
/** @function main */
int main()
{
  Mat image;
  char path1[] = "/home/user/EclipseProjects/img/book.png";
  image = imread(path1, 1);

  if(!image.data )
  {
     printf("No image data \n");
     return -1;
  }

  namedWindow( "Display Image", CV_WINDOW_AUTOSIZE );
  imshow("Display Image", image );

  waitKey(0);

  return 0;
}
```

 

5.7 #  We are only missing one final  step: To tell OpenCV where the OpenCV headers and libraries are. For  this, do the following:

- Go to **Project–>Properties**

- In **C/C++ Build**, click on **Settings**. At the right, choose the **Tool Settings** Tab. Here we will enter the headers and libraries info:

  1. In **GCC C++ Compiler**, go to **Includes**. In **Include paths(-l)** you should include the path of the folder where opencv was installed. In our example, this is `/usr/local/include/opencv`.

     ![Eclipse Tutorial Screenshot 9](http://docs.opencv.org/2.4/_images/a9.png)

     Note: If you do not know where your opencv files are, open the **Terminal** and type:

     ```
     $ pkg-config --cflags opencv
     ```

     For instance, that command gave me this output:

     ```
     -I/usr/local/include/opencv -I/usr/local/include
     ```

      

  2. Now go to **GCC C++ Linker**,there you have to fill two spaces:

     First in **Library search path (-L)** you have to write the path to where the opencv libraries reside, in my case the path is:

     ```
     /usr/local/lib
     ```

     Then in **Libraries(-l)** add the OpenCV libraries that  you may need. Usually just the 3 first on the list below are enough (for  simple applications) . In my case, I am putting all of them since I  plan to use the whole bunch:

     All the following libraries are from opencv 3.0.0 and contrib 3.0.0

     ```
     opencv_stitching 
     opencv_superres 
     opencv_videostab 
     opencv_adas 
     opencv_bgsegm 
     opencv_bioinspired 
     opencv_ccalib 
     opencv_datasets 
     opencv_face 
     opencv_latentsvm 
     opencv_objdetect 
     opencv_line_descriptor 
     opencv_optflow 
     opencv_reg 
     opencv_rgbd 
     opencv_saliency 
     opencv_surface_matching 
     opencv_text 
     opencv_tracking 
     opencv_xfeatures2d 
     opencv_calib3d 
     opencv_features2d 
     opencv_shape 
     opencv_video 
     opencv_ml 
     opencv_flann 
     opencv_ximgproc 
     opencv_xobjdetect 
     opencv_xphoto 
     opencv_highgui 
     opencv_videoio 
     opencv_imgcodecs 
     opencv_photo 
     opencv_imgproc 
     opencv_core 
     opencv_hal
     ```

      

     ![Eclipse Tutorial Screenshot 10](http://docs.opencv.org/2.4/_images/a10.png)

     If you don’t know where your libraries are (or you are just psychotic and want to make sure the path is fine), type in **Terminal**:

     ```
     pkg-config --libs opencv
     ```

     My output (in case you want to check) was: .. code-block:: bash

     > -L/usr/local/lib -lopencv_core -lopencv_imgproc -lopencv_highgui  -lopencv_ml -lopencv_video -lopencv_features2d -lopencv_calib3d  -lopencv_objdetect -lopencv_contrib -lopencv_legacy -lopencv_flann

     Now you are done. Click **OK**

  3. Your project should be ready to be built. For this, go to **Project->Build all**

     In the Console you should get something like

     ![Eclipse Tutorial Screenshot 12](http://docs.opencv.org/2.4/_images/a12.png)

  4. Ok! It is done! Run and see the effect. Don’t forget to replace the directory with a valid image in the code.

 

### Step 6: Some Errors Handling  

```
6.1 “libopencv_core.so.2.4: cannot open shared object file: No such file 
or directory” in ubuntu XX.XX
```

You haven’t put the shared library in a location where the loader can  find it. Look inside the /usr/local/opencv , /usr/local/opencv2,  /usr/local/lib folders and see if either of them contains any shared  libraries (files beginning in lib and usually ending in .so). when you  find them, create a file called /etc/ld.so.conf.d/opencv.conf

`$ sudo gedit /etc/ld.so.conf.d/opencv.conf`

and write to it the paths to the folders where the libraries are stored, one per line. Then run

`$ sudo ldconfig -v`

for example, if the shared libraries were stored under /usr/local/lib then I would write this to my opencv.conf file:

`/usr/local/lib/`

Hopefully, the problem will be solved; at least in my case. If still problem exists, do the following:

Include the path of your opencv’s `.so` files in LD_LIBRARY_PATH ()

```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
```

To learn more about shared libraries see at <https://www.eyrie.org/~eagle/notes/rpath.html>

 

```
6.2 # src/subdir.mk:18: recipe for target 'src/hello.o failed
```

Try the following links to solve this problem.

a) <http://www.eclipse.org/forums/index.php/m/790534/>

b) <http://stackoverflow.com/questions/24897323/recipe-for-target-failed-error-in-eclipse-using-cygwin>

This problem usually occurs when the wrong parser/compiler/linker is used. Try changing these:

Parser: Properties->C/C++ Build->Settings->Binary Parser

In my case:

```
Elf parser
Cygwin PE Parser
PE Windows Parser
```

Current Tool Chain / Current Builder:  Properties->C/C++ Build->Tool Chain EditorIn my case:

```
Tool chain  

GCC Assembler
GCC Archiver
GCC C++ Compiler
GCC C Compiler
MinGW C Linker
MinGW C++ Linker

Current Builder: 

Gnu Make Builder
```