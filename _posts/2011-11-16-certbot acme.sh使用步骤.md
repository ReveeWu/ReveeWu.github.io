# certbot acme.sh使用步骤
1. 安装acme(需翻墙) ```curl https://get.acme.sh | sh ```
2. 使alias生效 ```source ~/.bashrc```
3. 声明阿里云key&secret ```export Ali_Key="your key" Ali_Secret="your secret"```
4. 开始申请证书 ```acme.sh   --issue   --dns dns_ali  -d *.yourdomain.com```
5. 安装到指定目录供nginx使用 ```acme.sh --install-cert -d *.yourdomain.com --key-file       /etc/nginx/ssl/yourdomain.com/key.pem  --fullchain-file /etc/nginx/ssl/yourdomain.com/cert.pem --reloadcmd     "sudo nginx -s reload"```
6. 结束~

###### 注：acme会自动记录相关配置，如key&secret，nginx安装目录等，crontab任务执行时，如果需要更新证书，会自动安装到nginx目录


