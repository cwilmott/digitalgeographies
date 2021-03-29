# Before class

1. Make sure you have the Anaconda GUI installed for your machine: https://www.anaconda.com/products/individual

2. Install the UC Berkeley Virtual Private Network Global Protect - instructions here: https://security.berkeley.edu/services/bsecure/bsecure-remote-access-vpn

Test it by logging on!

# In class

Okay - I HAVE NO IDEA IF THIS WILL WORK. We're going to set up an internal chat server using the VPN as if we were on the campus. This will be using Socket IP and python. The reason we are doing this is to try to get some idea about protocols and exchange and how this might work peer to peer rather than through web browsers. This way also allows you (even if it fails) to look at the code that links different computers with each other and see how different protocols - FTP; SSH; SHTP etc... might work! 

1. Download the `chat_server.py` and `chat_client.py` files from the Github folder. *Save them in a folder on your desktop*. Feel free to take a look at them, but DO NOT CHANGE ANYTHING!

2. Turn on your VPN.

3. Now, we are going to do something new - and often difficult: use the command line. To do this you need to open the command interface. **For Mac**, right click on the folder that holds your code and select "Open New Terminal at Folder". **For PC** Open the window for your folder. At the top, at the address bar, click and you should be able to type in `cmd` and press enter. Or you might be able to right-click and see either "Open Command Window" or "Open Powershell Window here" or similar.  

4. Once your window is open, wait! I will need to open my VPN, find out my IP address, change the server side code to match and give you the IP address.

5. Once the above is done, type in the following to your terminal/command line script:
```
python chat_client.py
```
6. You will be asked to enter the IP address which I have given you. Enter it (you won't see it) and press `ENTER`

7. Fill out the PORT number `33000`

8. You will be prompted to enter your name.

9. Then, in theory, we may be able to chat on a virtual internal network peer to peer chat.
