<https://docs.docker.jp/compose/django.html>を参考にした。ただし、以下の点を変えた：

- Dockerfileで、`ADD`よりも`COPY`のほうがいいらしいので`COPY`に変えた
- requirements.txtで指定しているDjangoのバージョンが古いので4.0系に変えた

# Djangoプロジェクトの生成方法

`sudo docker-compose run web django-admin startproject hoge`

もともと`django-admin.py`になっていた部分を、Django 4.0には存在しないようなので、`django-admin`に変えた。

sudoは環境によってはなくてもよい。

# Djangoアプリの実行方法

`sudo docker-compose up -d`

# その他

`sudo docker-compose run web /bin/bash`でwebコンテナのシェルを開ける。`exit`で終了。
