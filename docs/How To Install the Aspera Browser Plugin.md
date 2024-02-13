## How To Install the Aspera Browser Plugin

One of the major logistical problems that we have to address at the Human Connectome Project, even for our own internal analysis, is how to move huge quantities of data from site to site. Our solution uses a file transfer protocol powered by Aspera that is capable of highly-accelerated data transfers across high-speed networks. It works (to oversimplify) by taking advantage of unused bandwidth in network fiber and rapidly pushing large chunks of data through.

We have an Aspera server on our end that manages downloads. To connect to it, you must install the Aspera browser plugin on your local machine. This plugin works in all major browsers in Mac OS, Windows and Linux (CentOS6 or later).

### Before you get started:

* Installation may require a browser restart, so we recommend installing the plugin right away rather than waiting until you have a dataset queued for download.
* Please note that this will not be effective if you have a slow connection on your end. So don't try this while using the free wireless at your local coffeeshop.

### Step by Step Installation:

1. Click the link at the top of your ConnectomeDB to download Aspera Connect. (Or [download Aspera Connect](http://downloads.asperasoft.com/en/downloads/8?list) from their website.
2. An installer file will download to your computer. (If you are using Chrome, this appears in the bottom left corner of the browser window). Also, a rather unfriendly-sounding notification dialog will appear. Click **OK** in this dialog.   
  
 ![](http://devadmin.humanconnectome.org/img/tutorial/Aspera-instructions/aspera-dialog-2.png)
3. Open the Aspera Connect installer -- for Chrome, you can click the file label in the bottom left corner of the browser window.  
  
 ![](http://devadmin.humanconnectome.org/img/tutorial/Aspera-instructions/aspera-install-warning.png)
4. Click through any dialogs that appear, including the end-user license agreement, as necessary to install the software. Choose the Typical installation.

> [!note]
> When prompted for a language selection, please use "US English." Other language options do not appear to be fully supported by Aspera. This is an issue we have raised with their developers and this item may be updated at a future time.
 ![](http://devadmin.humanconnectome.org/img/tutorial/Aspera-instructions/aspera-install-type.png) 

After completing these steps, the Aspera installer will automatically install across all browsers on your computer. A browser restart may be necessary to use it.

### Also See:

* By default, Aspera will download HCP data to your desktop. We strongly recommend setting your own preferences here.
* **[Troubleshooting Aspera Downloads](./Aspera%20Plugin%20Help%20and%20FAQ.md)** - What to do if Aspera downloads do not work on your network.
  


