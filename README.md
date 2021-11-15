# Docker Installation

I used Ubuntu to install Docker.

Type “sudo apt update” to update the apt repository. Then type “sudo apt install docker.io” to install Docker.

Install Docker Compose by typing…
“sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose”

Test the Docker Compose installation by typing “docker-compose –version”.

Make sure Docker is running by typing “sudo service docker status”. If it is not running, type “sudo service docker start”.

# OpenVAS Installation

Type “sudo docker run -d -p 443:443 –name openvas mikesplain/openvas” to install OpenVAS on Docker. This grabs the application from the Docker registry. Make sure your CPU is not maxed out so you can proceed to the next step.

Go to your browser and type in https://localhost/ in the address bar. You will be prompted that the connection is not private. Disregard all certificates and continue to the site. Log in with the following credentials…

	“Username: admin
	Password: admin”

After you are logged in, create a target by clicking on the “Configuration” tab at the top of the page and the clicking on “Targets”.

Create a new target by clicking on the star icon next to the question-mark icon in the top-left corner below the tabs. Fill in the “Name” field as whatever you want and next to the “Manual” radio button, type the first three parts of your IP address (i.e. 10.0.0) and finish off the address with a .1-255. It should look like i.e. “10.0.0.1-255”. Click the “Create” button.

Click on the “Scans” tab and click on “Tasks”. Create a new task by clicking on the star icon next to the question-mark icon in the top-left corner below the tabs. Fill in the “Name” field as whatever you want and select the “Scan Target” as the name of the target that you previously named in the last paragraph. Keep the “Scanner” selection as “OpenVAS Default” and click “Create”.

Click the green play button (start button) next to the task that you just created under the “Actions” column. Refresh the page to make sure OpenVAS is scanning properly.

Once the scan is complete, click the status bar under the “Status” column. The page will give you a list of vulnerabilities you have on your system.
