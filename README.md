# knowledge-graph-rdf-sparql

### Installing Blazegraph and Wikibase
We will chose lyrasis/blazegraph. Open a console window (Command Prompt in Windows or Terminal in Mac). Enter the following command:

`docker pull lyrasis/blazegraph:2.1.5`

The run command shown in the instructions is more complicated than what is listed on the Docker cheatsheet:
`docker run --name blazegraph -d -p 8889:8080 lyrasis/blazegraph:2.1.5`

The --name option makes it possible to refer to the container in a more abbreviated way. The -d option runs the container in detached mode, a detail we will not worry about. The -p 8889:8080 port command maps the port number where the service is listening inside the container (8080 in this example) to the port number outside the container where clients connect.


To stop the Blazegraph server, issue the following command 
`docker container stop blazegraph`


To restart the container, enter:
`docker restart blazegraph`

Note that stopping the container does not get rid of it. It is still present in an inactive form at the state when it was stopped. To actually remove the container, list the containers using:
`docker container ls --all`

and find the ID of the lyrasis/blazegraph:2.1.5 container. Then issue the command
`docker container rm {containerId}`

where {containerId} is the ID you found in the list. For example, if the ID were XXXXXXXXXXX, the command would be
`docker container rm XXXXXXXXXXX`

Note that this removes the container, but doesn’t delete the generic Docker image that you downloaded and used to set up the container. To delete the image as well, list the images using
`docker image ls`

### Starting Blazegraph
Access to the Blazegraph graph database and query functions is done through a web browser via the port that you set when you initiated the Blazegraph server using docker run (port 8889). To access the database, open your favorite web browser and enter the following in the browser URL bar:
`localhost:8889/bigdata/`
