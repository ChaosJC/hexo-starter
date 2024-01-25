---
title: Docker部署ZeroTierMoon服务
tags: [内网穿透]
categories: [ZeroTier]
cover: https://file.zfjyc.cn/file/static/zerotier_banner_repeat_1706085226336__310906.webp
poster:
  topic: 
  headline: Docker部署ZeroTierMoon服务
  caption: 
  color: white
banner: https://file.zfjyc.cn/file/static/zerotier_banner_repeat_1706085226336__310906.webp
date: 2024-01-24 15:55:10
description:
references:
  - '[✨docker-zerotier-moon](https://github.com/rwv/docker-zerotier-moon)'
---

{% hashtag ZeroTier color:yellow%}

{% quot 部署 %}

- **拉取ZeroTier Moon镜像**
  
  {% copy docker pull seedgou/zerotier-moon prefix:$ %}
  
  {% image https://file.zfjyc.cn/file/static/20240124160036_repeat_1706083237283__775153.png bg:var(--card) padding:16px %}

- **部署ZeroTier Moon服务并查看MoonID**

    {% copy docker run --name zerotier-moon -d --restart always -p 10002:9993/udp -v /home/docker/zerotier-moon:/var/lib/zerotier-one seedgou/zerotier-moon -4 1.1.1.1 -p 10002  prefix:$ %}
    
    {% copy docker logs zerotier-moon   prefix:$ %}
  
    {% image https://file.zfjyc.cn/file/static/20240124172348_repeat_1706088229494__101486.png bg:var(--card) padding:16px %}
    
    {% mark 参数注释 color:red %}
    
    - {% u -p 10002:9993/udp %} 映射监听端口 外部端口:容器内监听端口，默认监听9993UDP端口不需要修改，如果需要改其他端口直接修改命令中的{% mark 两个10002 color:warning %} 端口即可
    - {% u -v %} 将主机的{% mark /home/docker/zerotier-moon color:warning %}挂载到容器的{% mark /var/lib/zerotier-one  color:warning %} 使配置持久化，防止重新创建时MoonID改变
    - {% u -4 %} 外网IP地址，目前不支持域名的方式

{% quot 加入Moon节点 %}



复制上面部署成功后的MoonID

- Windows

  {% copy zerotier-cli orbit 改成获取到的MoonID 改成获取到的MoonID prefix:$ %}

{% link https://github.com/rwv/docker-zerotier-moon %}
