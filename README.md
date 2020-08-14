# docker-mult-container-sample


## Architecture: 									
									|----> Nginx/3000  (React Server)    Worker 
									|      with Prod React FIles           |
									|                                      |
  Browser ---> Nginx/80(ROUTING) -------> Express Server--------------> Redis
															   |
															   |
															   |
															   |------->Postgres
															   
															   


## Production multi-container deployment  

1. Push code to github  
2. Travis automatically pulls repo  
3. Travis builds test image, tests code  
4. Travis builds prod image  
5. Travis pushes built prod images to Docker Hub  
6. Travis pushes project to AWS EB  
7. EB pulls images from Docker Hub, deploys	  	


## Travis confiiguration  
1. Link the repository	to travis-ci.org. Navigate Name->Settings  
    Click on Sync Account & search the repository & enable it for build project	
2. Create Environment variable in this repository on travis-ci.org (Repositiry->More options-> Settings).  
   The variables are DOCKER_USERID & DOCKER_PASSWORD. These are user id and passwor of the Docker Hub - https://hub.docker.com/

	