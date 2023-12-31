## Django搭建博客
使用Django快速搭建博客

### 要求
* Python: 3.9 or （其他我没试试）
* Django: 4

### 特点

* markdown 渲染，代码高亮
* 三方社会化评论系统支持(畅言)
* 展示最新发布，博客分页
* 博文归档，标签

### 复现本博客
```shell
pip install -r requirements.txt
修改setting.py配置数据库（可选）
配置畅言：http://changyan.kuaizhan.com/（自行注册修改changyan.html的appid和conf）
python manage.py makemigrations blog
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver（或者python manage.py runserver 0.0.0.0:8000）
```
浏览器中打开<http://127.0.0.1:8000/>即可访问

部署mysql容器作为数据库

修改settings.py配置

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'myblog',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': '172.17.0.2', # 修改ip
        'PORT': '3306' #修改port
    }
}
```

使用docker



## ref

* [django2精致网站](https://github.com/jhao104/django-blog)

