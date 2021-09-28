# Introduction

One of the magical things about Tableau and Alteryx is how well they work together. In this past blog post, we walked through how to use the Tableau API with Alteryx from scratch using the download tool. To do this there are 3 steps: 

* Log into the tableau server through the API to get an access key
* Find out which view ID you want to work with
* Download the view as an image

Today, we want to introduce you to new Alteryx tools we have built to make this 3-step process soooooo much easier.


## Download the tools
* Download the tools from github here: https://github.com/InvisoByDevoteam/TableauServerAPIAlteryxTools by clicking the green code button and then “download to zip”
* Unzip the file and click on the .yxi files one at a time. This will install them in Alteryx. You will not receive a “successfully installed” note, but it only takes a second to install them and you can then find them in your toolbar by searching “Tableau Server”

* note - to use these on the server the tools must also be installed on the server.

https://user-images.githubusercontent.com/88531833/135091150-416473fc-08e3-467a-aeec-d655d0446928.mp4


Find the information you need: 

* Your Tableau Server URL without http/https
* Your username
* Your password
* The URL of the view you would like to work with
* Your site name (see below how to find this)

 In my demonstration here I will be using the following values::
* Tableau Server URL without http/https: tableau.inviso.dk
* Username: tor@inviso.dk
* Password: nice try ;)
* URL of the view: : https://tableau.inviso.dk/#/site/Inviso-TorPetersen/views/test2/Sheet1?:iid=1
* Site name: Inviso-TorPetersen (you can find the site name in the highlighted section of your views’s URL - marked in red above)


Now we are ready to go! 



# Tableau Server API Authentication
This tool returns an Tableau Server Authentication Token and Site-ID.
It requires 4 pieces of information: 
* Username 
* Password 
* Server URL 
* Site Name

The username and password are the credentials you use to log into your Tableau Server. The Server URL is the URL of your organisation, e.g. https://tableau.inviso.dk/. While Site Name is can be found in the URL once you have signed in e.g. (marked with "*") https://tableau.inviso.dk/#/site/*Inviso-TorPetersen*/explore


https://user-images.githubusercontent.com/88531833/135090970-b14b03d6-c054-4eca-ac17-f1f78f2d5059.mp4




# Tableau Server API Get View ID 

This tool requires to be connected to the output-stream of the Tableau Server API Authentication tool. It will return a list of your Tableau Server view names, view IDs and view URLs. 


https://user-images.githubusercontent.com/88531833/135091077-bbb397d8-1d82-49bd-af1d-2d2025abd032.mp4



# Tableau Server API Download Image 

This tool allows you to save a you Tableau Server dashboards locally as a png file. It requires to be connected to the output-stream of the Tableau Server API Authentication or Tableau Server API Get View ID -tool. Furthermore, you need to specify where (the path) you want to save locally e.g., C://Useres/user/Desktop/nameOfFile.png. Lastly, you need to specify which dashboard you wish to save as a png by specifying its _View ID_, which can be found in the output-stream of the Tableau Server API Get View ID tool. 



https://user-images.githubusercontent.com/88531833/135091112-a31a1bbd-9284-4790-ab31-5ca599bb197b.mp4

