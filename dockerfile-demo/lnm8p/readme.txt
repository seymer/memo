1. 创建本地目录
mkdir -p src/public
mkdir -p logs/nginx
mkdir -p conf/nginx

2. 配置文件
mv default.conf conf/nginx/
echo "<?php phpinfo();" > src/public/index.php

3. 基础命令
docker-compose up -d
docker-compose down
docker-compose ps

4. 清理
docker-compose down
mv conf/nginx/default.conf ./
rm -rf conf logs src

5. 备注
PHP连接mysql IP使用
docker inspect xxx
"Gateway": "172.23.0.1",
"IPAddress": "172.23.0.2",
如果你暴露了外部端口，从外部端口连接，使用gateway ip
若使用内部端口，则使用ip address
你最好在每次重启或重建后重新查看mysql容器ip，它是变化的。
