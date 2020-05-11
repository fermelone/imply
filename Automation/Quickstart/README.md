# Multipass + Cloud-init Imply.io Quickstart
## One-line command fully working Apache Druid environment

### Instructions:
- Download Multipass for your OS here: https://multipass.run/
- Download `quickstart.yaml` from this repository and place it in a known directory
- Open a terminal and naviagate to where you downloaded `quickstart.yaml`
- Run this command:  
```bash
multipass launch --name imply-quickstart --cloud-init quickstart.yaml --cpus=2 --mem=4G
```
- Wait until the instance is created, and then run `multipass list` to get the instance's IP address:
```bash
Name                    State             IPv4             Image
imply-quickstart        Running           0.0.0.0          Ubuntu 18.04 LTS
```
- Open a browser and navigate to the <INSTANCE_IP>:9095 to use imply's Pivot!  
You should be welcomed with the following screen:

  <img src="https://docs.imply.io/images/quickstart-01.png" alt="Pivot Welcome Screen" width="500">
  
  From this point, you should continue the instructions here:  
  https://docs.imply.io/on-prem/quickstart#load-data-file
  
### What's under the hood:
You can go ahead and shell into the instance by using `multipass shell imply-quickstart`  

Inside, you will see that there's no process taking your terminal session, because we're using something called `screen`, which is a session manager _(more on screen [here](https://linuxize.com/post/how-to-use-linux-screen))_

To take control of the session that's running all of imply's processes and resources, simply type:  
```bash
sudo screen -r imply
```
Which is the name we gave to that session.

_To detach from the session without closing it, hit CTRL-A > CTRL-D_
