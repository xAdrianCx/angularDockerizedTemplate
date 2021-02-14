# Angular dockerized develop template  

this template allows you to create a dockerized angular project ready for development without having to worry about docker config files, just plug and play  

## Instructions  

1 - clone project in your desired local folder:  
    git clone https://github.com/xAdrianCx/angularDockerizedTemplate.git  

2 - navigate into initialize folder and deploy project  
    cd initialize  
    docker build -t angular .  
    cd ..  
    docker run -itd -v ${PWD}:/app --name <nameContainer> angular  
    docker exec -it <nameContainer> ng new <nameProject> --directory=.  
    sudo chown -R $USER:$(id -gn $USER) ./*  

3 - once created the project, we dont need anymore the angular image, remove it  
    docker rm -f <nameContainer>  
    docker system prune -a  

4 - we can now develop with de new project starting docker-compose  
    docker-compose up  

5 - we can launch commands inside container with: (compose should be up)  
    docker-compose exec web ng g c xcy  

## Sources
* Open Source Devops [YouTube](https://www.youtube.com/channel/UCIJg_4sIbnmPDRqPVUNkayg)  
[video tutorial](https://www.youtube.com/watch?v=i7tTwv4WVn0&t=75s)