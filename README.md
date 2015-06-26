# pinax-project-account

[![Join the chat at https://gitter.im/pinax/pinax-project-account](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/pinax/pinax-project-account?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

In addition to what is provided by the "zero" project, this project provides
thorough integration with django-user-accounts, adding comprehensive account
management functionality. It is a foundation suitable for most sites that have
user accounts.


Usage:

```
django-admin.py startproject --template=https://github.com/pinax/pinax-project-account/zipball/master <project_name>
```

Customization:


```
修改域名
edite fixtures/sites.json

设置联系邮箱 <project name>/settings.py
+THEME_CONTACT_EMAIL = "ruishenglin@126.com"

页尾信息<project name>/templates/_footer.html
-{% trans "&copy; 2015 &lt;your company here&gt;" %}
+{% trans "&copy; 2015 广州市香港科大霍英东研究院 物联网研发部" %}

导航栏<project name>/templates/site_base.html
+{% block site_brand %}
+	<a class="navbar-brand" href="{% url "home" %}">home</a>
+	<a class="navbar-brand" href="{% url "home" %}">news</a>
+	<a class="navbar-brand" href="{% url "home" %}">files</a>
+	<a class="navbar-brand" href="{% url "home" %}">settings</a>
+	<a class="navbar-brand" href="{% url "home" %}">help</a>
+{% endblock %}
```


Getting Started:

```
pip install virtualenv
virtualenv mysiteenv
source mysiteenv/bin/activate
pip install Django==1.8.1
django-admin.py startproject --template=https://github.com/pinax/pinax-project-account/zipball/master mysite
cd mysite
chmod +x manage.py
pip install -r requirements.txt
./manage.py migrate
./manage.py loaddata sites
./manage.py runserver
```
