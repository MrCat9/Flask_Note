# Flask_Note

## 目录

#### 1_Flask上传本地图片并在页面上显示

https://blog.csdn.net/dcrmg/article/details/81987808

#### 2_Docker部署flask项目

https://zhuanlan.zhihu.com/p/78432719

https://blog.csdn.net/qq_35224503/article/details/98783809

https://www.jianshu.com/p/84caf2a7a3ea

删除Docker镜像 https://www.cnblogs.com/quanxiaoha/p/10542278.html

Dockerfile文件

```dockerfile
FROM python:3.6
WORKDIR /project/flask_demo

COPY requirements.txt ./
RUN pip install -r requirements.txt
RUN pip install dlib==19.19.0  # 直接放在requirements里安装会报错
RUN pip install torch==1.4.0+cpu torchvision==0.5.0+cpu -f https://download.pytorch.org/whl/torch_stable.html

COPY . .

CMD ["gunicorn", "app:app", "-c", "./gunicorn.conf.py"]
```

```dockerfile
FROM python:3.6
# 拷贝Linux上当前目录下的flask_demo文件夹
COPY ./flask_demo /root/xxxx/flask_demo
RUN pip install -r /root/xxxx/flask_demo/requirements.txt -i https://pypi.doubanio.com/simple/
ENTRYPOINT ["python","/root/xxxx/flask_demo/app.py"]
```

#### 3_flask允许跨域

Flask实现跨域请求的处理方法 https://blog.csdn.net/wangshu_liang/article/details/86490137

Flask允许跨域 https://www.cnblogs.com/chnmig/p/9920693.html

#### 4_flask服务gunicorn部署报错`Connection reset by peer`

flask服务gunicorn部署压测的Connection reset by peer问题解决方式 https://blog.csdn.net/lizhe_dashuju/article/details/103169746