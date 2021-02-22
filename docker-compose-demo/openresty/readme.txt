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

4. 错误
如遇FastCGI sent in stderr: "Primary script unknown"，是因为本地src目录与nginx root 配置不一致。
