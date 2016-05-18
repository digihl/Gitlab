# Gitlab Server Install
原始參考：https://about.gitlab.com/downloads/#ubuntu1404

1.安裝必要元件
sudo apt-get install curl openssh-server ca-certificates postfix
##選擇Internet Site
##輸入mail ok

2. Add the GitLab package server and install the package
##英文   
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
##中文   
curl -sS http://packages.gitlab.cc/install/gitlab-ce/script.deb.sh | sudo bash

3.安裝
sudo apt-get install gitlab-ce
sudo gitlab-ctl reconfigure
##如不調整任何項目，以上網頁已經可以開啟執行囉!

4.設定主機位置及SMTP設定
sudo vim /etc/gitlab/gitlab.rb

********************************************************
# 設定Gitlab路徑
external_url 'http://127.0.0.1'

# 設定由 Gmail SMTP 發送信件

gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.gmail.com"
gitlab_rails['smtp_port'] = 587
gitlab_rails['smtp_user_name'] = "my.email@gmail.com"
gitlab_rails['smtp_password'] = "my-gmail-password"
gitlab_rails['smtp_domain'] = "smtp.gmail.com"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_tls'] = false
gitlab_rails['smtp_openssl_verify_mode'] = 'peer'
********************************************************

5.設定完，重新再執行一次
sudo gitlab-ctl reconfigure
