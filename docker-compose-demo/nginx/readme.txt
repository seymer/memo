1. 创建本地目录（可以不用）
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


