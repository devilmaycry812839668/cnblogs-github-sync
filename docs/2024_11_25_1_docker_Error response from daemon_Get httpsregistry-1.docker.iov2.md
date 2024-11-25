---

title: docker报错——docker_Error response from daemon_Get "https://registry-1.docker.io/v2/"
 
description: 

#多个标签请使用英文逗号分隔或使用数组语法

tags: 杂谈

#多个分类请使用英文逗号分隔或使用数组语法，暂不支持多级分类

---





相关：
https://www.cnblogs.com/liujunjun/p/18546650

<br/>

<br/>

从docker的hub库中拉取镜像时报错，具体如下：



docker: Error response from daemon: Get "https://registry-1.docker.io/v2/": net/http: request canceled while waiting for connection (Client.Timeout exceeded while awaiting headers).
See 'docker run --help'.

<br/>

在<https://www.cnblogs.com/liujunjun/p/18546650>中找到解决方法，经过测试成功解决问题，具体步骤如下：





<br/>

修改配置文件 /etc/docker/daemon.json，修改后内容如下：

```
{
    "runtimes": {
        "nvidia": {
            "args": [],
            "path": "nvidia-container-runtime"
        }
    },


    "registry-mirrors": ["https://docker.registry.cyou",
    "https://docker-cf.registry.cyou",
    "https://dockercf.jsdelivr.fyi",
    "https://docker.jsdelivr.fyi",
    "https://dockertest.jsdelivr.fyi",
    "https://mirror.aliyuncs.com",
    "https://dockerproxy.com",
    "https://mirror.baidubce.com",
    "https://docker.m.daocloud.io",
    "https://docker.nju.edu.cn",
    "https://docker.mirrors.sjtug.sjtu.edu.cn",
    "https://docker.mirrors.ustc.edu.cn",
    "https://mirror.iscas.ac.cn",
    "https://docker.rainbond.cc"]


}
```

<br/>



修改后配置文件，重启docker服务，命令如下：



```
systemctl daemon-reload

systemctl restart docker
```











<br/>

<br/>

**个人github博客地址：**
[https://devilmaycry812839668.github.io/](https://devilmaycry812839668.github.io/ "https://devilmaycry812839668.github.io/")