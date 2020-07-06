# Flask_Note

## 目录

#### 1_Flask上传本地图片并在页面上显示

https://blog.csdn.net/dcrmg/article/details/81987808

#### 2_Docker部署flask项目

https://blog.csdn.net/qq_35224503/article/details/98783809

https://www.jianshu.com/p/84caf2a7a3ea

删除Docker镜像 https://www.cnblogs.com/quanxiaoha/p/10542278.html

Dockerfile文件

```dockerfile
FROM python:3.6
# 拷贝Linux上当前目录下的flask_demo文件夹
COPY ./flask_demo /root/xxxx/flask_demo
RUN pip install -r /root/xxxx/flask_demo/requirements.txt -i https://pypi.doubanio.com/simple/
ENTRYPOINT ["python","/root/xxxx/flask_demo/app.py"]
```

