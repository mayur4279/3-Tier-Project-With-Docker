# 3-tier-project-using-docker

### Step1 :- Build  the images:-   

#### docker  build  -t  "tomcat"  -f  Dockerfile.tomcat  .  
#### docker  build  -t  "mysql"  -f  Dockerfile.mysql  .  
#### docker  build  -t  "nginx"  -f  Dockerfile.nginx  .  

### Step2 :- Run  the images:-   

#### docker run -d  -p  8080:8080  tomcat  
#### docker run -d  -p  3306:3306  mysql  
#### docker run -d  -p  80:80  nginx  

### step3 :- Edit The IP Address of  context.xml  file (tomcat container)  

#### docker exec  -it  <contaner_id>  /bin/bash 
#### cd /usr/local/tomcat/conf  
#### sed  -i  's/<old-ip>/new-ip-of-mysql/g'  context.xml   


### step4 :- Edit The IP Address of  nginx.conf  (nginx container)   
#### docker exec  -it  <contaner_id>  /bin/bash 
#### cd /etc/nginx/
#### sed  -i  's/old-ip/public-ip-of-instance/g'  nginx.conf 


----------------------------------------------------------------------
### Now edit the security group and access your application from  Web  
