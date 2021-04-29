# 600 - Connecting with Ballerina Central

After having installed Ballerina (see https://github.com/vanHeemstraSystems/ballerina-headstart), make sure to add an ***Ballerina Central access token*** to your Ballerina settings as follows:

1) Open https://central.ballerina.io/dashboard and login with your account (registration is required).
2) Look at the window with the title ***Your Ballerina Token***.
3) Copy the text from above window, e.g.: ```[central] accesstoken="---SOME TOKEN HERE---"```
4) Paste the above text in ```<USER_HOME>/.ballerina/Settings.toml``` file.

Check if you can now ***pull Ballerina modules*** from Ballerina Central as follows (e.g. ballerina/ftp):

```
$ bal pull ballerina/ftp
ballerina/ftp:1.1.0-alpha9 [central.ballerina.io -> home repo]  100% [==========] 1671/1671 KB (0:00:
ballerina/ftp:1.1.0-alpha9 pulled from central successfully
```
