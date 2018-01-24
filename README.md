# ACI AppCenter App

In this repo, you'll find some resources to get you quickly started on developing an ACI App.

- A sample stateless app (Cisco_DemoApp)
- A sample stateful app (Cisco_DemoStatefulApp)
- Tools provided by Cisco to develop an ACI App.
- Quick tutorial to use the tools.

## Tools

### Prerequisites

#### UNIX (Linux, macOS,...)

#### Docker
Alternatively, you can use the docker image provided to run the tools.

To use it, a few steps are required to get started:
1. Install [docker](https://docs.docker.com/engine/installation/)
2. `cd` into the `tools` directory of this repo.
3. Create the docker image. Run the command:
```
docker build . -t aciappcenter-tools:latest
```
4. Upon the successful completion of the `docker build` command, you can check that the docker image has been generated (`docker images`).
5. Run the container using the command:
```
docker run -it -d -v <LOCAL_FOLDER>:<FOLDER_IN_CONTAINER> --name aciapptools aciappcenter-tools:latest
```
This command uses the `-v` parameter to mount a local directory into the container. That way, any file created in `<FOLDER_IN_CONTAINER>` will be present on your machine (in `<LOCAL_FOLDER>`) and vice versa. 



### ACI App Creator


#### Using docker container
1. Run the following command:
```
docker exec -it aciapptools python tools/aci_app_creator.py -o <FOLDER_IN_CONTAINER>
```


### ACI App Packager
1. Put your app in `<LOCAL_FOLDER>`
2. Run the following command:
```
docker exec -it aciapptools python tools/aci_app_packager.py -f <FOLDER_IN_CONTAINER>
```
3. You'll find the packaged add in `<LOCAL_FOLDER>`
