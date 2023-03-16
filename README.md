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
# 보안그룹 설정
```
인스턴스 A는 B를 통해서만 접속해야할때 B의 서브넷 ip를 넣는다
```
