## Terminal Script to Install Home Assistant (with Hassio Supervisor)


### Automated Script

The command below will execute the [`install_hassio.sh`](https://github.com/icanfixitweb/Hassio-Virtual-Machine/blob/master/hassio_install_script/install_hassio.sh) script to install Home Assistant and its dependencies automatically.

**[IMPORTANT]** If you are using Linux Mint the Automated Script will not work, you must follow the [Manual Installation](https://github.com/icanfixitweb/Hassio-Virtual-Machine/tree/master/hassio_install_script#manual-installation) method below.

```
sudo su
wget -O - https://raw.githubusercontent.com/icanfixitweb/Hassio-Virtual-Machine/master/hassio_install_script/install_hassio.sh | bash
```
***

### Manual Installation

##### Install dependencies
* `sudo apt-get install bash jq curl avahi-daemon dbus software-properties-common apparmor-utils`
 
##### Install Docker (Ubuntu) ([Linux Mint users follow these instructions](https://github.com/icanfixitweb/Hassio-Virtual-Machine/tree/master/hassio_install_script#install-docker-linux-mint))
* `sudo apt-get install apt-transport-https ca-certificates curl software-properties-common -y`
* `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
* `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`
* `sudo apt-get update`
* `sudo apt-get install docker-ce -y`

> ##### Install Docker (Linux Mint)
> * `sudo apt-get install apt-transport-https ca-certificates curl software-properties-common -y`
> * `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
> 
> open the "additional-repositories.list"
> * `sudo nano /etc/apt/sources.list.d/additional-repositories.list`
> 
> add the following line in the file
> * `deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable`
> 
> close the file with `CTRL+X` and press `Y` on your keyboard to save and continue with the rest of the installation
> * `sudo apt update`
> * `sudo apt-get update`
> * `sudo apt-get install docker-ce -y`

##### Install Home Assistant
* `curl -sL https://raw.githubusercontent.com/icanfixitweb/Hassio-Virtual-Machine/master/hassio_install_script/original_script/installer.sh | bash -s -- -d /home/me/docker/hassio`

> This last command will install Home Assistant in `/home/me/docker/hassio`. Replace `me` with your username or replace the whole path with your preferred path. 

***

Once the installation is completed go to `http://hassio.local:8123/` or `http://yourIPaddress:8123/` (replace `yourIPaddress` with your actual IP address) from your web browser to access your new Home Assistant installation.
