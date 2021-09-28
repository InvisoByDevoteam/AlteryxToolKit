# Tableau Server API Alteryx Tools

One of the magical things about Tableau and Alteryx is how well they work together. Today we are going to take that even further, and use the Tableau API within Alteryx. With this we can do several magical things, including downloading an image (png. pdf, etc.) of a Tableau view (view = dashboard). However, enabling working with tableau server requires a authentication process (authentication token) and information about the dashboard you wish to save as a png. 

This repository includes 3 tools:

* Tableau Server API Authentication
* Tableau Server API Get View ID 
* Tableau Server API Download Image 

As mentioned the two first tools are required in order to be able to extract anything from you Tableau Server. The last tool saves a dashboard locally on your computer. Behind the scene these tools utilised Tableau Server APIs. Hence, making your Alteryx workflow less complicated, safer and increase your work effiency. 


https://user-images.githubusercontent.com/88531833/135091150-416473fc-08e3-467a-aeec-d655d0446928.mp4



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

