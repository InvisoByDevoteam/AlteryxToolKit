# Tableau Server API Alteryx Tools


One of the magical things about Tableau and Alteryx is how well they work together. Today we are going to take that even further, and use the Tableau API within Alteryx. With this we can do several magical things, including downloading an image (png. pdf, etc.) of a Tableau view (view = dashboard), downloading the data behind a Tableau view, downloading an entire Tableau workbook, uploading a Tableau workbook, and much more. However, enabling working with tableau server requires a authentication process (authentication token) and information about the dashboard you wish to save as a png. 

This repository includes 3 tools:

* Tableau Server API Authentication
* Tableau Server API Get View ID 
* Tableau Server API Download Image 

As mentioned the two first tools are required in order to be able to extract anything from you Tableau Server. The last tool saves a dashboard locally on your computer. Behind the scene these tools utilised Tableau Server APIs. Hence, making your Alteryx workflow less complicated, safer and increase your work effiency. 

# Tableau Server API Authentication

This tool requires 4 pieces of information: 
* Username 
* Password 
* Server URL 
* Site Name

The username and password are the credentials you use to log into your Tableau Server. The Server URL is the URL of your organisation, e.g. https://tableau.inviso.dk/. While Site Name is can be found in the URL once you have signed in e.g. (marked with "*") https://tableau.inviso.dk/#/site/*Inviso-TorPetersen*/explore




https://user-images.githubusercontent.com/88531833/128858572-f86ad766-58c1-4ae3-9e4e-f584abb5b76c.mov

# Tableau Server API Get View ID 

This tool requires to be connected to the output-stream of the Tableau Server API Authentication tool. It will return a list of your Tableau Server view names, view IDs and view URLs. 


# Tableau Server API Download Image 

This tool allows you to save a you Tableau Server dashboards locally as a png file. It requires to be connected to the output-stream of the Tableau Server API Authentication or Tableau Server API Get View ID -tool. Furthermore, you need to specify where (the path) you want to save locally e.g., C://Useres/<user>/Desktop/<name of file>. 
