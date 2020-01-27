
# OMFListener fix procedure

## Steps

### Step 0 - verify or get info about OMFListener

To verify if OMFListener, or just get information about it, open a web browser page with this URL: http://localhost:6008. 

The page has all the following information:

* Root in AF
* Device name
* Version 

Sample screenshot below:

![](https://academichub.blob.core.windows.net/images/omflistener-stats-christian-012720.png)


Note: to shutdown OMFListener cleanly, go to http://localhost:6008/shutdown. Username and password are `admin` and `secret` respectively.  

You can check the state of all OMFListeners at https://academicpi.osisoft.com/PIVision/#/Displays/137/Hub_Listeners_All (Hub PI Vision account needed for access). If a given OMFListener is green with active heartbeat already, or becomes green just after starting it, you can skip the steps below which are for repair. The date under colored status is the last time a health update has been received. 


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

### Step 7 - check status of OMFListener health

Go to https://academicpi.osisoft.com/PIVision/#/Displays/137/Hub_Listeners_All and find OMFListener device ID shown on the statistics page in Step 6. 

--------------------------------- end --------------------------------------------

