
# 后端一键安装脚本（大猫猫版）

本文以 CentOS 7 和 CentOS 8 为例。
# 脚本功能

    可选配置节点为WebAPI模式或MySQL模式
    可选配置单端口多用户
    可选启用BBRv1（CentOS 7 使用Mainline版本kernel，CentOS 8使用系统自带kernel）
    可选注册为系统服务

# 安装

CentOS 7（非主要支持版本，请有条件的优先使用CentOS 8）

yum install wget -y && wget https://raw.githubusercontent.com/SSPen/Airport-toolkit/master/ssr_node_c7.sh && chmod +x ssr_node_c7.sh && ./ssr_node_c7.sh

CentOS 8

dnf install wget -y && wget https://raw.githubusercontent.com/SSPen/Airport-toolkit/master/ssr_node_c8.sh && chmod +x ssr_node_c8.sh && ./ssr_node_c8.sh

# 卸载

systemctl disable ssr_node && \rm /usr/lib/systemd/system/ssr_node.service && \rm -rf /soft/shadowsocks

# 服务启动

systemctl start ssr_node

# 服务停止

systemctl stop ssr_node

# 注意事项

    由于后端不再支持Python3，在CentOS 7环境中安装时会额外安装Python3.6
    所有跟节点安装本身无关的功能会通过单独的脚本提供
    
