<https://docs.docker.jp/compose/django.html>を参考にした。ただし、以下の点を変更した：

- Dockerfileで、`ADD`よりも`COPY`のほうがいいらしいので`COPY`に変えた
- requirements.txtで指定しているDjangoのバージョンが古いので4.0系にした

# Djangoプロジェクトの生成方法

`sudo docker-compose run web django-admin startproject hoge .`

もともと`django-admin.py`になっていたが、Django 4.0には存在しないようなので`django-admin`に変えた。

sudoは環境によってはなくてもよい。

# Djangoアプリの実行方法

`sudo docker-compose up -d`

# その他

コンテナが停止している場合は`sudo docker-compose run web /bin/bash`、動作中の場合は`sudo docker-compose exec web /bin/bash`でwebコンテナのシェルを開ける。`exit`で終了。
