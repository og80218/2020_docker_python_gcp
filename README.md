20200709_P2_使用docker-compose打包jupyter

1.開啟虛擬機器(centos7)，建議使用user進入(建議別使用root)，進入後打開終端機

2.至docker官網依照步驟安裝docker&docker-compose

3.docker&docker-compose安裝完成後，

  #開啟終端機輸入
  
    git clone https://github.com/og80218/2020_dockercompose_jupyter.git
	
	#下載完成後
	
	cd 2020_dockercompose_jupyter
	
	docker-compose up -d
	
	#啟動完成後，可開啟windows網頁，網址輸入虛擬機器IP:8889，有顯示表示完成。
	
	
#註記:欲修改images，可至資料夾dockerfile目錄下，

#修改dockerfile-jupyter內的FROM XXXX(XXXX可至dockerhub查詢)