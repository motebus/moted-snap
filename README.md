# Topic(mote://)

## bash
Control the device sudch like ssh
- token: For security
- command: Write script here
## xstorage
Operate xstorage
- method: 
    1. setConfig: Save info to config
    2. getConfig: Get info from config
    3. changeEiName: Rename einame of app
    4. getBucket: Get file from bucket
    5. setBucket: Save file to bucket
    6. listBucket: List all files in bucket
    7. removeBucket: Remove file in bucket
- catalog: Catalog name
- idname: File name
- data: Content
## nearby
Search near device
## drop
Drop file to other device
- method: 
    1. ls: List the all files in the device you choose 
    2. cp: Send the file to another device
    3. rcp: Get the file from another device
    4. cat: Get the content of the file
    5. rm: Remove the file
- DDN: The DDN of target
- path: The directory
- files: The name of the file
- fsize: The size of the file (`rcp`)
## shot
Screen capture
## measure
Check system information
- method
    1. info: Get the information of cpu, os, gpu, disk......
    2. status: Get the status of your device, such like temp., loading, ram......
## qsnap
Computing deploy
- type:
    1. fbots: Run the flow
    2. aibots: Run the AI model
- operate:
    1. list: List the all services
    2. run: Run a new service (`fbots`)
    3. restart: Restart the service 
    4. checkAlive: Check all service alive if not would restart ti
    5. stop: Stop the running service
    6. start: Start the stopped service (`fbots`)
    7. delete: Delete the service
    8. open: Open a new service (`aibots`)
    9. close: Close the service (`aibots`)
- svcName: Service name
- startTime (`run`): 
    1. now: Immediately run the service
    2. 2020/12/18-14:23:0(date): Run the service at that time
- stopTime (`run`):
    1. forever: Never stop the service
    2. 2020/12/18-14:24:0(date): Stop the service at that time
- MCHAT_EINAME: Same as parameter of flowbot (`fbots`, `run`)
- MCHAT_APPNAME: Same as parameter of flowbot (`fbots`, `run`)
- MCHAT_UDID: Same as parameter of flowbot (`fbots`, `run`)
- MCHAT_DC: Same as parameter of flowbot (`fbots`, `run`)
- MCHAT_IOC: Same as parameter of flowbot (`fbots`, `run`)
- MCHAT_WATCHLEVEL: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_UI: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_QCODE: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_FLOWFILE: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_QNAME: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_MODE: Same as parameter of flowbot (`fbots`, `run`)
- FBOT_PORT: Same as parameter of flowbot (`fbots`, `run`)
- svcSource: The URL of the entry code (`aibots`, `open`)
- modelName: The model name you use (`aibots`, `open`)
- modelSource: The URL of the model (`aibots`, `open`)
- parameter: The parameter for entry code (`aibots`, `open`)
## apt
Package management
- operate
    1. list: List all package in your device
    2. remove: Remove the package in your device
    3. install: Install the package in your device
- type
    1. snap
    2. apt
    3. npm
- packageName: The package name
- keyword: If you don't know the correct package name, you can use this to help you search (`list`)
## time
Timezone setting
- method
    1. now: Get the time of your device
    2. listTimezone: Get the timezone which you could set 
    3. setTimezone: Set your timezone to your device
- zone: 
    1. Enter the state you want to search (`listTimezone`) 
    2. Enter the complete area you want to set (`setTimezone`) 
- keyword: If you don't know the correct area name, you can use this to help you search (`listTimezone`)
## setUser
User information setting
- EiTag: The tag of your device
- EiLoc: The location of your device
## getUser
User information getting
## listPeripherals
List peripherals
- device:
    1. usb: List the usb device on your device
    2. camera: List the camera on your device
    3. ip: List other device which in the same local network with your device
    4. screen: List the screen on your device
- update: True/False for update (`ip`)
## env
Process environment parameter
- method
    1. read: Get the content of environment
    2. create: Create the new environment
    3. append: Append new parameter to the environment
    4. update: Re-write the content to the environment
    5. delete: Delete the environment
- path: The path of environment
- content: The content of environment (**Use array format**)
## schedule
Make schedule
- operate
    1. list: List the all schedule
    2. create: Create a new schedule
    3. delete: Delete the schedule
    4. start: Start the autostart schedule (`boot`)
    5. stop: Stop the autostart schedule (`boot`)
- type
    1. once: Only do once
    2. routine: Do routinely
    3. boot: Autostart when boot
- hour (`once`, `routine`)
- minute (`once`, `routine`)
- month (`once`, `routine`)
- day (`once`, `routine`)
- week (`routine`)
- command: Write script here
- job: The job name (`boot`)
- workspace: Choose the workspace you want to open on (`boot`)
- terminal: Check whether show the terminal (**0/1**) (`boot`)
## window
Operate window
- operate
    1. list: List the all service with window
    2. assign: Assign the service to let keybot control
    3. move: Move the service to other workspace
    4. change: Switch the workspace
- service: The service id (**Use array format in assign**)
- key: Which device you assign service to (`assign`)
- workspace: Which workspace you want to move (`change`)
## keybot
Define keybot shortcut
- device: The device you want to set
- shortcuts: Define the key
```
{
    "device": "numPad",
    "shortcuts": {
        "0": "Mic",
        "1": "Workspace1",
        "2": "Workspace2",
        "3": "Workspace3",
        "4": "Workspace4",
        "5": "Super",
        "6": "Workspace0",
        "7": "Sceenshot",
        "8": "Window",
        "9": "Screencast",
        "/": "Switch",
        "*": "Mute",
        "+": "Volume+",
        "-": "Volume-"
    }
}
```
## audio
Operate audio
- operate
    1. adjust: Adjust the volume
    2. list: List all speakers and microphones
    3. change: change the source of speaker or microphone
- volume (`adjust`):
    1. number => like 100, 50, 30
    2. difference => like +5, -5, +30
- device: Which speaker or microphone you want to adjust (`change`, `adjust`)
- port: The device port (`change`)
- audio (`change`):
    1. source: Which means input audio
    2. sink: Which means output audio  
## shortcut
Manage GNOME shortcut
- operate
    1. list: List all function
    2. get: Get the function shortcut
    3. set: Set the shortcut to the function
    4. reset: Reset shortcut to Default
- func: The GNOME function name
- key: Keyboard key as shortcut

# Package requirement
- wmctrl
- scrot
- nodejs

# Error Code
| No | ErrCode | ErrMsg |
| -- | ---- | ------- |
| 1	| 0	| OK |
| 2	| -30001 | Error topic |
| 3	| -30002 | Permission denied |
| 4	| -30003 | Illegal parameter |
| 5	| -30004 | Operate not found |
| 6	| -30005 | Error |
| 7	| -30006 | Invalid parameter |
| 8	| -30007 | Type not found    |
