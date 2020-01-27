
# OMFListener fix procedure

## Steps

### Step 1 - install hub toolkit

If toolkit 1.5.3.37 (latest) is installed, skip to Step 3. Otherwise go to https://academic.osisoft.com/toolkit, download and install. 

### Step 2 - start OMFListener 

Launch the LabVIEW version for which the hub toolkit was installed. From the Tools menu, click 'Start OMFListener'. Go to Step 6.  


### Step 3 - empty OMFListener message queue

Open a CMD shell. The directory where OMFListener.exe is installed depends on the LabVIEW version. For LabVIEW 2018 32-bit for example, the directory is C:\Program Files (x86)\National Instruments\LabVIEW 2018\project. Within the CMD shell, cd to this directory and execute:

    .\OMFListener.exe empty_queue

### Step 4 - remove previous configuration

In the same CMD shell, execute:

    .\OMFListener.exe configure_clean

Note: a browser window with no content will open, you can close it.


### Step 5 - start OMFListener 

In the same CMD shell, execute: 

    .\OMFListener.exe run 

Note: the CMD window will disapear once OMFListener is fully started and a browser window will open.

### Step 6 - configure OMFListener 

In the field asking for a token, enter the relevant token then click 'Submit'. If successful, click word/link 'HERE' in the blue ribbon message. 

At this point, OMFListener statistics web page should show up with updates every 5 seconds. 


