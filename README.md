# ConvertMovToGif

#### A MacOS Automator File for Converting video files from .mov to .gif

##### By Ryan Duff

## Description
This is a simple Automator Quick Action that you can use to convert any .mov file into a .gif. It requires gifify for the conversion and uses a short bash shell script to load your user bash profile, execute the conversion and place the resultant .gif file on your desktop.


## Installation Requirements
* Computer running OSX
* Gifify [(link to Gifify on GitHub)](https://github.com/vvo/gifify "Gifify")

## Setup
* Once gifify has been installed, clone/download this repository to your machine.
* Open the downloaded project folder using Finder, right-click on the convertMovToGif.workflow file and click Open. OSX will prompt you and ask if you wish to install the Quick Action. Click the Install button to make the action available.
* If OSX does not prompt you to install the Quick Action, you can install it manually. To do so, simply move the convertMovToGif.workflow file contained in the project folder to: Macintosh HD > Users > [YourUserName] > Library > Services via the command line in Terminal.
* _Note: The user Library folder is typically hidden in OSX. For this reason I recommend moving the file via the command line. If you prefer to use Finder to move the file, navigate to Macintosh HD > Users > [YourUserName]. Click "Go" in the menu bar, then click "Go to Folder" from the dropdown menu. Enter ~/Library at the prompt. Finder will make the Library folder and all its contents visible. Navigate to Library > Services and place convertMovToGif.workflow within the Services folder._

## Using the Quick Action
* Once the convertMovToGif.workflow file has been installed it will be available for use on any .mov within a Finder window. 
* Open a finder window and highlight the .mov file you wish to convert. 
* In the file preview pane, click the "More" button. This will list all available Quick Actions for .mov files.
* Click "convertMovToGif"
* You can also access the Quick Action by right-clicking on any .mov file and selecting convertMovToGif from the Quick Actions list.
* Once convertMovToGif has been selected, an animated gear icon will appear in the menu bar to indicate that the action has begun and a file named temp.gif will appear on the desktop.
* The time needed to completed the conversion is dependent on the file size. Even small 10-20 second videos will take a minute or two to convert. Expect proportionatley longer wait times with larger files.
* When conversion has been completed you will be prompted to enter a name for the new file. A .gif extension will be added automatically so do not include it in your file name.
* The temp.gif file on your desktop will be renamed accordingly.
* Not that your original .mov file will be destroyed at the end of the process so please duplicate it before launching the Quick Action if you require a copy of the original file.

## Additional Notes
You are encouraged to tinker with this file and customize it for your own use. You can do so with the OSX Automator application. Open the Automator app from your Applications folder and select Open from the menu bar, then navigate to Macintosh HD > Users > [YourUserName] > Library > Services and select convertMovToGif.workflow. 

Example: If you'd like to prevent the Quick Action from destroying your original .mov file, simply eliminate the final two actions (Get Value of Variable and Move Finder Items to Trash).

All changes to the conversion parameters will need to be made within the Run Shell Script action of the workflow. When you download the workflow the initial script is as follows:

* $ source ~/.bash_profile
* $ cd desktop/
* $ gifify  "$@" -o "temp".gif --resize 720:-1

You can add options to modify the conversion on the third line. If, for instance you would prefer to have your .gif output to 480 vertical pixels you could do so by altering line 3 like this:

* $ gifify  "$@" -o "temp".gif --resize 480:-1

Gifify offers many options for making the file conversion and you will get a lot more out of the workflow by learning about them. [Click Here](https://github.com/vvo/gifify) to see the documentation. 

Please reach out if this Quick Action is not working for you and I'll be happy to help. Also, feel free to contact me with any modifications etc. It's a work in progress and I'd love to have hear any outside opinions and advice.
