OpenCV
======

Basic set of tutorials that demonstrate OpenCV with C++ in Visual Studio

Steps To Initialize OpenCV for Visual Studio : (With help from http://www.youtube.com/watch?v=cgo0UitHfp8)

STEP 1 
  Go to https://sourceforge.net/projects/opencvlibrary/files/opencv-win/ and download the latest .exe file
  
STEP 2
  Extract the downloaded file to a nice destination like C:\opencv245 for version 2.4.5
  From the folder opencv245\opencv copy all files and place in C:\opencv245 for easier access later on.
  Delete folder C:\opencv245\opencv
  
STEP 3
  START --> Computer --> System Properties --> Advanced System Settings --> Environment Variables
  
STEP 4
  Under System Variables, create a New System Variable with following details :
    Variable Name - OPENCV_BUILD
    Variable Value - C:\opencv245\build
  
  Under System Variables, edit the Path variable by adding the following value :
    %OPENCV_BUILD%\x86\vc10\bin;
    
STEP 5
  In Visual Studio, create a new project and name it "MyNewOpenCV" or whatever else you like.
  Under Visual C/C++, choose the "Win32 Console Application" option.
  Click OK --> Next --> Additional Options --> Empty Project
                    --> Application Type --> Console Application
  Click Finish
  
STEP 6
  Under Property Manager, right-click on Debug|Win32 tab.
  Click "Add New Project Property Sheet"
  Name it "OPENCV_DEBUG" and click "Add".
  
STEP 7
  Right-click on OPENCV_DEBUG and select "Properties"
  
  C/C++ --> Additional Include Directories --> Clck and select "Edit" from drop-down menu
  Paste the following string :
    $(OPENCV_BUILD)\include
    
  Linker --> General --> Additional Library Directories --> Clck and select "Edit" from drop-down menu
  Paste the following string :
    $(OPENCV_BUILD)\x86\vc10\lib
    
  Linker --> Input --> Additional Dependencies --> Clck and select "Edit" from drop-down menu
  Paste the following string (all of them together) :
    opencv_core245d.lib
    opencv_imgproc245d.lib
    opencv_highgui245d.lib
    opencv_ml245d.lib
    opencv_video245d.lib
    opencv_features2d245d.lib
    opencv_calib3d245d.lib

STEP 8
  DONE! SETUP COMPLETE.
  Return to Solution Explorer tab.
  Source Files (right-click) --> Add --> New Item --> C++ File (Name : main.cpp)


