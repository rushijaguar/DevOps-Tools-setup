EC2: ubuntu

apt update -y

apt install fontconfig openjdk-21-jre -y

wget -O /etc/apt/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

apt update -y

apt install jenkins -y
 
systemctl start jenkins

vim /etc/sudoers

jenkins ALL=(ALL) NOPASSWD: ALL
