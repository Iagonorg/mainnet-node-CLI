# Iagon Storage Node CLI
Iagon Storage Node CLI is a cross-platform CLI application which allows users to share their storage on the Iagon network to earn extra money.

# Introduction
Welcome to the installation guide for Iagon Node CLI , a Command line application that empowers users to securely store files with ease. This document provides step-by-step instructions to help you install and set up Iagon Node CLI on your Windows, Linux, freeBSD or macOS system.

# Downloading the Installation Package
Visit https://github.com/Iagonorg/mainnet-node-cli/releases/latest to download the installation package for your operating system.

# Installation Steps
# Windows
- Download application from this link
  - https://github.com/Iagonorg/mainnet-node-cli/releases/download/v1.0.1/iag-cli-windows.exe
- Follow the on-screen instructions to complete the installation process.
- Once the installation is complete, Iagon Node CLI is ready to use.

# Command Set for Interacting with the Node CLI
- Start Node Evaluation:
   - Command: ./iag-cli-windows start
   - Description: This command is used to evaluate the node or start the node if it has already been evaluated.
- Stop Node:
  - Command: ./iag-cli-windows stop
  - Description: Use this command to stop your node if it is already running.
- Regenerate Authorization Key:
  - Command: ./iag-cli-windows key:regenerate
  - Description: Regenerate the authorization key for your node.
- Get Node Information:
  - Command: ./iag-cli-windows  get:info
  - Description: Retrieve information about your node.
- Check Node Status:
  - Command: ./iag-cli-windows get:status
  - Description: Check the status of your node.
- Get Node Verification Status:
  - Command: ./iag-cli-windows get:verification
  - Description: Obtain the verification status of your node.
- Display Command Help:
  - Command: ./iag-cli-windows help
  - Description: Display help for commands.

# Linux
- Download application from this link
  - wget https://github.com/Iagonorg/mainnet-node-cli/releases/download/v1.0.1/iag-cli-linux
- Open a terminal window.
- Navigate to the directory where the installation package is located.
- Enter the following command to make it executable
    - chmod +rwx ./iag-cli-linux
- Follow the on-screen instructions to complete the installation process.
- Once the installation is complete, Iagon Node CLI is ready to use.

# Command Set for Interacting with the Node CLI.
- Start Node Evaluation:
    - Command: ./iag-cli-linux start
    - Description: This command is used to evaluate the node or start the node if it has already been evaluated.
- Stop Node:
  - Command: ./iag-cli-linux stop
  - Description: Use this command to stop your node if it is already running.
- Regenerate Authorization Key:
  - Command: ./iag-cli-linux key:regenerate
  - Description: Regenerate the authorization key for your node.
- Get Node Information:
  - Command: ./iag-cli-linux get:info
  - Description: Retrieve information about your node.
- Check Node Status:
  - Command: ./iag-cli-linux get:status
  - Description: Check the status of your node.
- Get Node Verification Status:
  - Command: ./iag-cli-linux get:verification
  - Description: Obtain the verification status of your node.
- Display Command Help:
  - Command: ./iag-cli-linux help
-   Description: Display help for commands.

# Run as SYSTEMD-Service under Linux
### (Autostart at Boot and continuously check if it is running, if not auto-restart)

- Create a script in the same directly where you downloaded the iag-cli-linux to:  
```nano /full/path/to/your/iag-cli/iag-cli-node-checker.sh```

- Insert the following code into that file and save it:  
```
#!/bin/bash
while true; do
    if ! pgrep -f "/full/path/to/your/iag-cli/iag-cli-linux /snapshot/iagon-node-cli/build/commands/startServer.js" > /dev/null; then
        /full/path/to/your/iag-cli/iag-cli-linux start
    fi
    sleep 30
done
```

- Make the script executable:  
```chmod +x /full/path/to/your/iag-cli/iag-cli-node-checker.sh```  

- Create the SYSTEMD-Service script-file:  
```nano /etc/systemd/system/iag-cli.service```

- Insert the following code into that file and save it:  
```
[Unit]
Description=IAG CLI Service
After=network.target

[Service]
Type=simple
User=<username>
Group=<usergroup>
ExecStart=/full/path/to/your/iag-cli/iag-cli-node-checker.sh
ExecStop=/full/path/to/your/iag-cli/iag-cli-linux stop
WorkingDirectory=/full/path/to/your/iag-cli/

Restart=always
RestartSec=60

[Install]
WantedBy=multi-user.target
```

⚠️Make sure you replace `<username>` and `<usergroup>` with the Username and Usergroup of the User who should run the iag-cli-linux⚠️

- Reload/Refresh the SYSTEMD Daemon:  
```sudo systemctl daemon-reload```  

- Enable the IAG-CLI Service:  
```sudo systemctl enable iag-cli.service```  

- Start the IAG-CLI Service:  
```sudo systemctl start iag-cli.service```  

- By now your IAGON-Node should run, will automatically start after boot and will restart automatically if it crashes.  

# macOS
- Download application from this link 
    - wget https://github.com/Iagonorg/mainnet-node-cli/releases/download/v1.0.1/iag-cli-macos
- Open a terminal window.
- Navigate to the directory where the installation package is located.
- Enter the following command to make it executable
    - chmod +rwx ./iag-cli-macos
- Follow the on-screen instructions to complete the installation process.
- Once the installation is complete, Iagon Node CLI is ready to use.

# Command Set for Interacting with the Node CLI.
- Start Node Evaluation:
    - Command: ./iag-cli-macos start
    - Description: This command is used to evaluate the node or start the node if it has already been evaluated.
- Stop Node:
  - Command: ./iag-cli-macos stop
  - Description: Use this command to stop your node if it is already running.
- Regenerate Authorization Key:
  - Command: ./iag-cli-macos key:regenerate
  - Description: Regenerate the authorization key for your node.
- Get Node Information:
  - Command: ./iag-cli-macos  get:info
  - Description: Retrieve information about your node.
- Check Node Status:
  - Command: ./iag-cli-macos get:status
  - Description: Check the status of your node.
- Get Node Verification Status:
  - Command: ./iag-cli-macos get:verification
  - Description: Obtain the verification status of your node.
- Display Command Help:
    - Command: ./iag-cli-macos help
    - Description: Display help for commands.



# For FreeBSD
- Download application from this link 
    - wget https://github.com/Iagonorg/mainnet-node-cli/releases/download/v1.0.1/iag-cli-freebsd
- Open a terminal window.
- Navigate to the directory where the installation package is located.
- Enter the following command to make it executable
    - chmod +rwx ./iag-cli-freebsd
- Follow the on-screen instructions to complete the installation process.
- Once the installation is complete, Iagon Node CLI is ready to use.
- Command Set for Interacting with the Node CLI.
- Start Node Evaluation:
    - Command: ./iag-cli-freebsd  start
    - Description: This command is used to evaluate the node or start the node if it has already been evaluated.
- Stop Node:
    - Command: ./iag-cli-freebsd stop
    - Description: Use this command to stop your node if it is already running.
- Regenerate Authorization Key:
    - Command: ./iag-cli-freebsd key:regenerate
    - Description: Regenerate the authorization key for your node.
- Get Node Information:
    - Command: ./iag-cli-freebsd  get:info
    - Description: Retrieve information about your node.
- Check Node Status:
    - Command: ./iag-cli-freebsd get:status
    - Description: Check the status of your node.
- Get Node Verification Status:
    - Command: ./iag-cli-freebsd get:verification
    - Description: Obtain the verification status of your node.
- Display Command Help:
    - Command: ./iag-cli-freebsd help
    - Description: Display help for commands.
	
# Post-Installation Steps
Upon completion of the node CLI application installation, users are required to register their device's node by following these steps:

- Launch  Application:
  - Open the  Iagon Node CLI application on your device.
- Configure API Port:
  - Specify the port for the Node  to operate. The default port is randomly generated. Optionally, users may choose an available alternative port.
- Select File Storage Path:
  - Choose a file path for  Iagon Node CLI to store files. Ensure that the selected path has adequate free storage space and hit Evaluate.
- Testing Phase:	
    - The application will conduct a thorough test to validate the functionality of file uploads and downloads in the chosen storage path. This process may take a few minutes.
- Authorization Key Retrieval:
 - Upon successful testing, users will be provided with an authorization key. Copy this key and securely store it for future use.

# Steps to migrate to higher version
- Install the latest version of Iagon Node from above installation steps.
- Stop the older version of your Iagon Node CLI.
- After installation, start the latest version of the node.

