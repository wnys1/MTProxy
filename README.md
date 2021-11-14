安装MTProxy前建议先安装宝塔，
yum install -y wget && wget -O install.sh http://v7.hostcli.com/install/install_6.0.sh && sh install.sh

然后搭载好网站，

安装SSL证书，

## 新建目录
mkdir /home/mtproxy && cd /home/mtproxy

## 开始安装
curl -s -o mtproxy.sh https://cdn.jsdelivr.net/gh/wnys1/MTProxy/mtproxy.sh && chmod +x mtproxy.sh && bash mtproxy.sh

## 使用方式
下面所有操作前进入到目录
cd /home/mtproxy

## 修复常见问题
bash mtproxy.sh fix

## 运行服务
bash mtproxy.sh start

## 调试运行
bash mtproxy.sh debug

## 停止服务
bash mtproxy.sh stop

## 重启服务
bash mtproxy.sh restart

## 卸载安装
因为是绿色版卸载极其简单，直接删除所在目录即可。

rm -rf /home/mtproxy

## 开机启动
编辑/etc/rc.local开机自启服务文件，将如下代码添加到开机自启脚本中；

# 编辑自启文件
vi /etc/rc.local

# 添加如下代码
bash /home/mtproxy/mtproxy.sh start > /dev/null 2>&1 &

