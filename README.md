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
# flask 예제 파일
```
#!/usr/bin/python3
from flask import Flask, abort, request, jsonify
import logging

app = Flask(__name__)

log = logging.getLogger('werkzeug')
log.disabled = True
app.logger.disabled = True

@app.route('/health', methods=['GET'])
def get_health():
  try:
    ret = {'status': 'ok'}

    return jsonify(ret), 200
  except Exception as e:
    logging.error(e)
    abort(500)

if __name__ == "__main__":
  app.run(host='0.0.0.0', port=80)
  ```
