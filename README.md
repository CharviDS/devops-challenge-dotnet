

1)Solution

This is a .Net application and pipeline is created using Github actions. 
Docker credentials are created using 

Technologies used

Git

Github actions

Docker

mcr.microsoft.com/dotnet/sdk:5.0 is used as the base image.

Acceess to docker hub is stored as environment variables in Github secrets in the settings.
Username : secrets.DOCKERHUB_USERNAME
Password : secrets.DOCKER_PASSWORD

To trigger the pipeline you have to make your changes out of a checked out branch from the main as the main branch is protected and send a PR to merge to main branch. When the Pull request is created to the main branch github actions will run checks to check if the stages of the pipline is passed, once the checks are passed you can merge it to main.
You can observe the pipline workflow when you go to actions in the github.

Github workflow includes,

dotnet test which has been allowed to fail

docker login

build the docker image using latest as default

push the docker image that was built in the previous step to the docker hub

the final docker image pf the build applciaction as a container can be found in the below link in docker hub with the tage latest

https://hub.docker.com/r/cjandsilvap/charvi/tags

post actions










