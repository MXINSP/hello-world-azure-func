# Demo: Azure Function in a Linux Container

## To create an image:
* `docker build -f hello-world/Dockerfile -t mxinsp/hello-world:latest . `
  * The dot `.` (Build Context) at the end of the above command is important.  
  * A _build's context_ is the set of files located in the specified PATH or URL.
  * `docker build -t <IMAGE_NAME> .`
  * `docker build -t <REGISTRY>/<IMAGE_NAME>:<TAG> .`

## To run a container using the newly created image:
* `docker run -it --rm -p 8181:80 mxinsp/hello-world:latest`
* `docker run -d --rm --name func-hello-world -p 8181:80 -v $(pwd):/var/www/logs mxinsp/hello-world:latest`
  * If you're using PowerShell, then change `$(pwd)` -> `${pwd}`

## To save the image to your container registry:
* `docker push mxinsp/hello-world:latest`
---
## Links
* [Create a function on Linux using a custom container](https://learn.microsoft.com/en-us/azure/azure-functions/functions-create-function-linux-custom-image?pivots=programming-language-csharp&tabs=isolated-process%2Cbash%2Cazure-cli%2Cv1)
