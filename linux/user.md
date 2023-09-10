# 用户操作
## 1. 添加新用户
```
sudo adduser newuser
```
## 2. 将新用户添加到sudo组
```
sudo usermod -aG sudo newuser
```
## 3. 测试sudo权限
```
su - newuser
sudo apt update
```