# nginx-http-flv-module-packages
一些[nginx-http-flv-module](https://github.com/winshining/nginx-http-flv-module)的rpm安装包。

[nginx-http-flv-module](https://github.com/winshining/nginx-http-flv-module)在这个工程中被编译为动态模块，现在只有Red Hat Enterprise Linux 6（CentOS 6）和7（CentOS 7）的安装包可用。

# 依赖

* 在Red Hat Enterprise Linux 6（CentOS 6）或者7（CentOS 7）上通过yum安装的[Nginx](http://nginx.org)。

# 安装

    rpm -ivh nginx-http-flv-module-version-release.arch.rpm

例如，在Red Hat Enterprise Linux 6（CentOS 6）上，你可以通过下面的命令安装[nginx-http-flv-module](https://github.com/winshining/nginx-http-flv-module)：

    rpm -ivh nginx-http-flv-module-1.2.4-1.el6.x86_64.rpm

## 注意

你必须以root身份安装rpm包。

# 安装后

## 将conf文件添加到nginx.conf

[nginx-http-flv-module](https://github.com/winshining/nginx-http-flv-module)用到的conf文件位于/etc/nginx/http-flv，你可以在/etc/nginx/nginx.conf中通过`include`将它们添加到配置中。

    http {
        ...;
        include /etc/nginx/http-flv/http-flv.conf;
    }

    include /etc/nginx/http-flv/rtmp.conf;

### 注意

在`include`之前，你可以根据环境修改conf文件。

## 启动或者重新加载[Nginx](http://nginx.org)

    service nginx start

或者

    service nginx reload
