# Welcome to Agile Lab!

This is our technical test. Once you are done, you can either upload the answers to your own repository and share us the link, or you can zip your answers up and send it directly to us via email!

Enjoy!

## 1. Devops knowledge base
- Do you know systemd, SysVinit or Upstart?

I use systend in contained (container runtimes):
To use the systemd cgroup driver in /etc/containerd/config.toml with runc, set



- Do you know FHS? How to manage package compile?

FSH stands for "Filesystem Hierarchy Standard"
Store compiled files in in /root_project/build/


- Should you clean trash in your server when change role?

Yes trash should be clean when change role to save memory in hard disk.


- Do you have server naming schema? What about hostname of you server?

Yes, I set the server name in /etc/hostname and.or /etc/host, for example:

-   gitlab.idsvn.asia
-   192.168.0.200   gitlab.idsvn.asia   gitlab

- How long uptime of your server? Do you update new version OS?

Uptime server is 24/7, the server is always on.

Yes I always update latest production OS version, for instance: RHEL-8.3.


- Do you use key or password for ssh, do you have policy for password?

For on-premiss sever I use password for ssh.

For AWS EC2 server, I use key secret for example (idsvn.pem):
$ chmod 400 idsvn.pem
$ ssh -i "idsvn.pem" ubuntu@ec2-3-140-217-76.us-east-2.compute.amazonaws.com

Password policy: upper & lower case character + special key (@#$) + alphanumeric key.


- Do you use firewall on your server?

Yes I use firewall on my server (just open the service ports):
$ sudo firewall-cmd --zone=public --add-port=6443/tcp --permanent
$ firewall-cmd --reload


- Do you know Heartbleed, Shellshock and POODLE?

Shellshock, is a family of security bugs in the Unix Bash shell, Shellshock could enable an attacker to cause Bash to execute arbitrary commands and gain unauthorized access to many Internet-facing services, such as web servers, that use Bash to process requests.


- Do you use redis or mongod? How to authentication them? What user of process mongod or redis?

I use MongoDB Atlas. 

I connect to the MongoDB cluster by using RHEL 7, mongo shell:

and authenticate my username "kuber":
$ mongo "mongodb+srv://cluster0.wxl9x.mongodb.net/myFirstDatabase" --username kuber


- How do you deploy code to server? Do you use git pull for deployment?

run "docker-compose up --build" to generate container image. e.g.:   nginx-plus

$ docker tag nginx-plus idsvnasia/nginx-plus:1.0

$ docker push idsvnasia/nginx-plus:1.0

$ docker pull idsvnasia/nginx-plus:1.0

or in the nginx-plus-deployment.yaml, claim:

image:  dsvnasia/nginx-plus:1.0

$ kubectl  apply -f  nginx-plus-deployment.yaml

$ kubectl  get deploy

$ kubectl  get pods



Credited to [xluffy](https://github.com/xluffy)
