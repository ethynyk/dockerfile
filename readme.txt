rename it to dockerfile
docker build -t docker_name:tag .

function run_docker() {
     docker run  -e LOCAL_USER_ID=`id -u $USER_ID` --privileged -itd -v $2:/project/$1 --name $1  docker_name:tag /bin/bash
}

add the function to ~/.bashrc

run_docker user_name /workwspace/path

docker exec -it user_name /bin/bash

exit container
docker stop user_name 
docker rm user_name 

remove the docker image:
1. docker image list 
2. docker rmi docker_name:tag


export docker image:
docker save -o docker_xxx.tar docker_name:tag

load the docker:
docker load -i docker_xxx.tar

