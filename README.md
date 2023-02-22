# EC2 Password
``` 
sed -i "s/PasswordAuthentication no/PasswordAuthentication yes/g" /etc/ssh/sshd_config
sudo echo -e "[password]\n[password]" | sudo passwd ec2-user
systemctl restart sshd
```
# EC2 Port Changing
``` 
echo 'Port [port]' >> /etc/ssh/sshd_config
systemctl restart sshd
```
