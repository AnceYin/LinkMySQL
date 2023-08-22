### 更新下载源
sudo apt update
### 安装MySQL
sudo apt install mysql-server
### 安装MySQL C++客户端开发库
sudo apt-get install libmysqlcppconn-dev
### 启动mysql服务
sudo service mysql start
### 查看debian-sys-maint的密码
sudo cat /etc/mysql/debian.cnf
### 根据密码登录debian-sys-maint账号
mysql -u debian-sys-maint -p 
### 输入密码
W23gJTnFOIUFbn02
### 进去`mysql`数据库
use mysql
### 修改密码
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
### 保存上述操作
flush privileges;
### 设置远程登录
update user set user.Host='%' where user.User='root';
### 保存上述操作
flush privileges;
### 退出数据库
exit
### 设置开机自启动
sudo update-rc.d -f mysql defaults
### 进入WSLCtrl+`打开终端给最高权限改配置文件, 将第一个127.0.0.1改成0.0.0.0
sudo chmod 777 /etc/mysql/mysql.conf.d/mysqld.cnf
