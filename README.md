## Scripts
# Client scripts
They are stored into /cient-scripts, you must own the RSSHServer.pem certificate in order to get it working
Then call checkGateway.sh

## Add the service Deamon
# Copy file 
Copy rssh.service file to /etc/systemd/system/
# Start the service
systemctl start rssh
# Automatically get it to start on boot
systemctl enable rssh
# Control the status of the service
systemctl -l status rssh

## Add an alias for gateway.sh script
sudo nano ~/.bashrc
add 'alias gateway='/home/ec2-user/rssh-server/./gateway.sh'
. ~/.bashrc

## Get the internet source for a gateway
gateway -c moduleID or gatewayID


## Connect through SSH to the gateway
gateway -i moduleID or gatewayID


## Reboot the gateway
gateway -r moduleID or gatewayID
