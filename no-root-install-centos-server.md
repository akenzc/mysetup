

### 建立文件夹

    cd ~
    mkdir local
    mkdir local/bin
    echo "export PATH=~/local/bin:~/local/python/bin:$PATH" >> ~/.bashrc

### 安装python

	wget -c https://www.python.org/ftp/python/2.7.7/Python-2.7.7.tgz
	tar -zxf Python-2.7.7.tgz
	cd Python-2.7.7
	./configure --prefix=~/local/python
	make -j 8
	make install

### 安装distribute

	wget https://pypi.python.org/packages/source/s/distribute/distribute-0.7.3.tar.gz
	tar zxf distribute-0.7.3
	cd distribute-0.7.3
	python setup.py install
		
### 安装setuptools

	wget https://pypi.python.org/packages/source/s/setuptools/setuptools-4.0.1.tar.gz
	tar zxf setuptools-4.0.1
	cd setuptools-4.0.1
	python setup.py install
	
### 安装pip

	wget https://pypi.python.org/packages/source/p/pip/pip-1.5.6.tar.gz
	tar zxf pip-1.5.6.tar.gz
	cd pip-1.5.6
	python setup.py install
	
### 安装python第三方库

	pip install django
	pip install django-suit
	pip install simplejson
	pip install mysql-python
	pip install uwsgi
	
### 安装nginx
如果报错 `./configure: error: the HTTP rewrite module requires the PCRE library.` 则需要下载并解压prce，并指定pcre的源码目录
	
	wget http://nginx.org/download/nginx-1.7.1.tar.gz
	tar zxf nginx-1.7.1.tar.gz
	cd nginx-1.7.1
	./configure --prefix=~/local/nginx
	./configure --prefix=~/local/nginx --with-pcre=~/aken/pcre-8.35/
	make -j 8
	make install
	
