# Building a Jenkins Pipeline on an EC2 Instance

## Create a security group

![image](https://user-images.githubusercontent.com/49791498/141510211-e00dc083-b854-40a4-9236-39f2ad9fb9b1.png)

## Launch an EC2 instance

![image](https://user-images.githubusercontent.com/49791498/141513230-c522b58b-fc7d-42ac-b264-42b4cbbe01bb.png)

### Connect to it

![image](https://user-images.githubusercontent.com/49791498/141517154-c00ae5bf-a898-4fa0-84c8-868da2ad14d7.png)

## Install Jenkins

```bash
sudo yum update –y
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo yum install jenkins -y
sudo service jenkins start
sudo systemctl start jenkins.service
sudo systemctl enable jenkins.service
```

## Configure Jenkins

- Navigate to ```http://ec2-instance-ip:<port>```
![image](https://user-images.githubusercontent.com/49791498/141525130-f285e4a0-233f-4d37-a4b7-b8a24432a58f.png)

- Get your Admin password by running
  
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

## Install Amazon EC2 plugin

![image](https://user-images.githubusercontent.com/49791498/141528057-04871e2c-fef5-4e56-9d5e-0b1a71aa488c.png)

## References

- [Documentation](https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/#:~:text=Jenkins%20is%20an%20open%2Dsource,in%20a%20matter%20of%20minutes.&text=Install%20and%20configure%20Jenkins,-Clean%20up)
