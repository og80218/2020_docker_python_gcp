20200713_P1_使用docker-compose打包jupyter和python

1.開啟虛擬機器(centos7)，建議使用user進入(建議別使用root)，進入後打開終端機

2.至docker官網依照步驟安裝docker&docker-compose

3.docker&docker-compose安裝完成後，

  #開啟終端機輸入
  
    git clone https://github.com/og80218/2020_docker_python_gcp.git
	
	#下載完成後，啟動docker
	
	systemctl start docker
	
	cd 2020_docker_python_gcp
	
	docker-compose up -d
	
	#啟動完成後，可開啟windows網頁，網址輸入虛擬機器IP:2289，有顯示表示完成。
	
	#*重要*若有更改docker-compose.yml檔案，啟動方式如下
	
	docker-compose up -d --build
	
	#切換至有.py的目錄下，欲執行.py檔，開啟主程式
	
	cd 2020_docker_python_gcp
	
	#進入python bash，安裝ta-lib，A終端機
	
	docker exec -it python bash
	
	yum install -y gcc
	
	wget https://sourceforge.net/projects/ta-lib/files/ta-lib/0.4.0/ta-lib-0.4.0-src.tar.gz
	
	tar -xvf ta-lib-0.4.0-src.tar.gz
	
	cd ta-lib
	
	./configure --prefix=/usr
	
	make
	
	make install
	
	pip3 install ta-lib
	
	#完成後，可開啟B終端機，下載ngrok(linux版)，並換時區開啟
	
	./ngrok http 5000 -region au
	
	#回A終端機，開啟sever，至/app

	python app.py
	
#註記:欲修改images，可至資料夾dockerfile目錄下，

#修改dockerfile-jupyter內的FROM XXXX(XXXX可至dockerhub查詢)