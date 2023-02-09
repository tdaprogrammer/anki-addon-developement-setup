# anki-addon-developement-setup
*Pycharm setup for anki addon developement*
I'm using Python 3.9.13, other versions can work as well, however I haven't try it.   
Create a new project in Pycharm, go to the terminal and type 
```
import subprocess
subprocess.check_call(["pip3", "install", "--upgrade", "pip"])
subprocess.check_call(["pip3", "install", "mypy", "aqt[qt6]"])
```
This should download the necessary libraries to run anki in your Pycharm virtual environment.
Create a new python file in Pycharm, I'll call it runaki.py.   
Go to [the anki repository](https://github.com/ankitects/anki/blob/main/qt/runanki.py) and copy and paste the code in your python file you just have created.  
This python file will run anki to test your extension.
You don't want to mix up your anki profile and your anki development profile, to avoid this, you can configure anki to run in a different profile folder, to do that go to Pycharm,   
run configurations and in the parameters put the following:   
``` -b your_profile_path```.   This line comes from the [anki source](https://github.com/ankitects/anki/blob/f616bea580f6174c6b95f00e9374d48ce5ab520b/qt/aqt/__init__.py#L385)   
That will create a separate folder from you local anki installation.   
Now run the project in Pycharm then, go to tools->addons->view files. Keep in mind that path because all your extensions will be in there.
I'll create a folder called "myaddon" and link it with my Pycharm folder path though a symbolink link.
Because I'm running Windows, open a cmd with administrator privileges and run the command:   
```
mklink /D "C:\Anki\addons21\test" "C:\Users\*your_profile_name*\PycharmProjects\anki-addon\myaddon\src"
```
Happy anki addon development!

