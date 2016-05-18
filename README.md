# hello-world
###########################################################################
Gitlab Server Install
###########################################################################
https://about.gitlab.com/downloads/#ubuntu1404

sudo apt-get install curl openssh-server ca-certificates postfix
##選擇Internet Site
##輸入mail ok

2. Add the GitLab package server and install the package
##英文   
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
##中文   
curl -sS http://packages.gitlab.cc/install/gitlab-ce/script.deb.sh | sudo bash

sudo apt-get install gitlab-ce
sudo gitlab-ctl reconfigure

sudo vim /etc/gitlab/gitlab.rb
