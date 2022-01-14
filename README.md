# How to compile a micro-manager device adaptor

This is a step by step guide on how to compile a micro-manager device adaptor using a recent Visual Studio and Boost library on Windows 10.

This has been tested with the configuration
- Windows 10
- Visual Sudio 2019 community edition 2020 v16.63
- Boost v1.77 installed in C:\Software\boost
- micro-manager cloned from https://github.com/jboulanger/mmCoreAndDevices/

Feel free to use a different version of Boost or another approach to clone the mmCoreAndDevices repository. 

1. Download and install visual studio https://visualstudio.microsoft.com/downloads/
2. Download and install github desktop https://desktop.github.com/ for retreiving files from github (need to create an account on github)
3. Dowload boost for windows https://sourceforge.net/projects/boost/files/boost-binaries/1.78.0/boost_1_78_0-msvc-14.2-64.exe/download and install it in C:\Software\boost
4. Clone the mmCoreAndDevices repository for example from https://github.com/jboulanger/mmCoreAndDevices
5. Open Visual Studio and select the project you want to work with in the mmCoreAndDevices solution
6. To update the toolset and SDK to match the installed one :
   1. In the Solution explorer righ click on the project and select "properties"
   2. In the left panel in the treet open "configuration properties" and select "general", update the two following line to the available options. For example:
      - Windows SDK version : 10.0 
      - Plateform Toolset  : Visual Studio 2019 (v142) 
8. to update the location of the boost library used to compile the project:
    1. Open file MMCommons.props in the folder mmCoreAndDevices/buildscripts/VisualStudio
    2. Change the path for location includes and libraries:
      ```xml
          <MM_BOOST_INCLUDEDIR>C:\Software\boost\boost_1_77_0</MM_BOOST_INCLUDEDIR>
          <MM_BOOST_LIBDIR>C:\Software\boost\boost_1_77_0\lib64-msvc-14.2</MM_BOOST_LIBDIR>
      ```
9. Test the building the project (Ctrl-B) or Build>Build 'name of the project' or righ click in the Solution explorer and buid
  
