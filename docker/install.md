# 安装Docker
```
1. 更新系统
sudo apt update
sudo apt upgrade
2. 安装依赖包
sudo apt install apt-transport-https ca-certificates curl software-properties-common
3. 添加Docker官方仓库的GPG密钥
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
4. 添加Docker官方仓库
echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
5. 安装Docker
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
6. 启动Docker服务
sudo systemctl start docker
7. 设置Docker开机自启动
sudo systemctl enable docker
8. 验证Docker安装
sudo docker --version
9. 使用Docker
sudo docker run hello-world
不使用sudo的情况下运行Docker命令的权限
sudo usermod -aG docker your_username
```