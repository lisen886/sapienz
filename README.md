## Sapienz Prototype (Out-of-date)
Sapienz: Multi-objective Automated Testing for Android Applications  

This is a prototype of the Sapienz approach for multi-objective automated testing for Android applications.
Please note that this repository is no longer maintained.

Publication:
```
@InProceedings{mao:sapienz:16,
    author = "Ke Mao and Mark Harman and Yue Jia",
    title = "Sapienz: Multi-objective Automated Testing for {Android} Applications",
    booktitle = "Proc. of ISSTA'16",
    year = "2016", 
    pages = {94--105}
} 
```

## Installation

Simply download the artefact [here](https://github.com/Rhapsod/sapienz/archive/d0f06c30800332bbafa7cf0ed32379fe1abcad5d.zip) and apply the following environment configuration: 

### Environment Configration
* Python: 2.7

* Android SDK:
    API 19

* Linux:
    sudo apt-get install libfreetype6-dev libxml2-dev libxslt1-dev python-dev

* Mac OS:
    brew install coreutils for gtimeout

Install Python dependencies:

    sudo pip install -r requirements.txt


## Usage
    python main.py <apk_path | source_folder_path>

where apk\_path is path to the subject apk under test  
or you can specify source\_folder\_path for the subject app with source code

### Subject Requirement:
* instrumented apk should be compiled and named with suffix "-debug.apk"
* closed-source/non-instrumented apk name should end with ".apk" 

### Settings
* ANDROID\_HOME and WORKING\_DIR in settings.py should be set before starting Sapeinz.

### Output
* for open-sourced apps, outputs are stored under the given source folder
* for closed-sourced apps, output are stored under <apk_file_path>_output

Output content:

    /coverages - Coverage reports are stored here
    
    /crashes - Crash reports and corresponding test cases that lead to the crashes 
    (and also recorded videos files when using real devices)
    
    /intermediate - Generated test event sequences for each generation; logbook of the genetic evolution; 
    and line charts showing the variation trend for each objectives.


##  Notes
* This implementation has been tested with Android 4.4, running on Ubuntu 14.04 and Mac OS 10.10
* If measure statement coverage for open-sourced apps, the subjects need to be processed to support EMMA instrumentation:
(Please refer to Dynodroid https://code.google.com/archive/p/dyno-droid/)
* This version is only for emulators running on a physical PC. 


## Contact
<dreamict@gmail.com>
