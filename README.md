# webApp
Link to github-https://github.com/Ori-Abramovitch/Web-App.git. \
Link for the presentation of Web App- https://www.youtube.com/watch?v=T5d5ldQX2YM\

A Web app server that implements a REST-API for the clients,and a single web-page.\
The server supports parallelism requests. which given a flight data - find irregular behavior at the flight and report it to the client.\
There is two possible ways to connect to the server -\
1. By the client web page appliction - the client just need to upload the files and the app will connect to the server by itself.\
2. By himself - the client could connect dircet to the server and ask for the answers.

## Collaborators
This program was developed by four student, Ori Choen, Ori Abramnovich, Aviv Dimri and Yosef Berebi, CS students from Bar-Ilan university, Israel.

## Code Design:
We use with the node.js technology for the server app, and the client web-page with html&css. all this by the MVC architecture. 

## REST-API:
The sever is bind to the port - 8080 and the ip is your localhost if you download this project to your own computer.
There are a few http functions that the API supports and  will extend for each one of them which type is it and what it is url.
1. GET - '/' - by the '/' the client will get the web-page that he can connect to the server from there - \
The client shold upload two files - train and test file, and also to choose  which algoritem he want to test the flight.\
There are two possible algoritems -\
A. Line Regression.\
B. MinCircle.\
After uploading the files - the server return him which features have irregular activity and when the devion started and when its ended.

2.GET- /api/amodel - given a id of the client the server will return is status by a json, the given id should by at the query with the name 'model_type'.

3.GET- /api/amodels - the server will return all the clients that where connect to him by a json.

4.POST -/api/detect -the client should upload two files - if just one of them will upload the server will return an error,\
the names of the files should be at the body request by the name - train and test. And the server will return the irregular activity by json to the client.

5.DELETE - /api/model - given an id of the client - the server will erase him from his list of models.

## Structure project:
There are a few folders:

1.In the view folder you have the the view control for the web-page.

2.In the Model folder - there is the model server that do all the work behind.

3.In node_models folder there are all the liberys you need.

4.In the files folder - there are the files you may upload to the server - train and test file.

# Installation for running the App:
1. Use git clone https://github.com/Ori-Abramovitch/Web-App.git to downloads the project.
2. Make sure you already has a node on your computer - if not you may downloads from here for free - https://nodejs.org/en/download/.you may use any operation systeam you want.
3. Use node contorller.js to run the server.
4. Try to connect the server from any browser or progream language to connect the server by port - 8080,you may change it if you want.
5. You may use one or any of the function we declare at the REST-API above.

## UML:
We can see in the UML below of the App which based on the MVC architecture. We bulided the View and then put them in the Main Window. Every View has View Model of its own, which is as the model for the View. For the View, it is an abstraction of the Model.It passes commands from the view to the model.

The Views Model Converts model information into view information. The Model and every View Model Implement INotifyPropertyChanged interface and notify about changes for the observers like a View Model or View. The views Model get notifications from the model by adding delegates to its PropertyChangedevent. Eventually we used Data binding within the UI.

If a View want to make change in the model we used with functions.

Also, the Model has a client which resposinble about the connection with the Flight Gear Simulator. In the left side we can see that the View of the Graph has a member of dinamic dll which responsible on the connect of the dll View to the Main Window. The dll can be any algorithm whichimplement the interrface by name IntrfaceDll which contain the 3 function Create,Update,Time(its cut in the picture)


![UML](https://user-images.githubusercontent.com/80414213/120098860-f062b300-c140-11eb-87eb-0e46f113292d.png)





