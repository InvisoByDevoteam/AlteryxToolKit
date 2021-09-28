# Introduction

One of the magical things about Tableau and Alteryx is how well they work together. In this past blog post, we walked through how to use the Tableau API with Alteryx from scratch using the download tool. To do this there are 3 steps: 

* Log into the tableau server through the API to get an access key
* Find out which view ID you want to work with
* Download the view as an image

Today, we want to introduce you to new Alteryx tools we have built to make this 3-step process soooooo much easier.


## Download the tools
* Download the tools from github here: https://github.com/InvisoByDevoteam/TableauServerAPIAlteryxTools by clicking the green code button and then “download to zip”
* Unzip the file and click on the .yxi files one at a time. This will install them in Alteryx. You will not receive a “successfully installed” note, but it only takes a second to install them and you can then find them in your toolbar by searching “Tableau Server”

** note - to use these on the server the tools must also be installed on the server.

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



# Step 1: Log into your Tableau Server

*To log into the tableau server you will have to submit a request to Tableau, and they send you back a token. For the next 240 minutes (unless you change this     setting) you can use this token in all of your other requests you submit.*

*To summarize: First we send our username and password to tableau, they send back a token which will then count as our pseudo username and password when using     the API.*
 
But you can ignore this, because you have tool number 1 - The Tableau Server API Authentication Tool. Simply drag to your canvas and fill in the required information and you are ready for step 2. 

<img width="779" alt="image5" src="https://user-images.githubusercontent.com/88531833/135097976-ad29ee17-61d9-4f75-95f1-5811b47e7e47.png">


https://user-images.githubusercontent.com/88531833/135090970-b14b03d6-c054-4eca-ac17-f1f78f2d5059.mp4





# Step 2: Find our View ID


In step 2, we will ask Tableau to give us a list of all of the views on our site. It will return the list and include a numeric view_id which we will then use to ask Tableau to download our view. Unfortunately, this is the only way to get the view_id. You can not find it on the Tableau Server. 

To summarize, you need to use the Tableau Server API Get View ID tool **ONE** time to get the view_id that you need. It will not change, even if you move the workbook inside the same site, rename it, etc. 

There are no configurations, just attach it to the previous tool and run. You can see all of the views on your site in the output. I have copied the View ID from row 2 as that is the view I want to download, and continue to step 3.

<img width="675" alt="image7" src="https://user-images.githubusercontent.com/88531833/135098266-cd8e7434-84d0-4529-8a72-ed4be40e5b81.png">

https://user-images.githubusercontent.com/88531833/135091077-bbb397d8-1d82-49bd-af1d-2d2025abd032.mp4





# Step 3: Download your dashboard

After finding your view ID, you simply plug that into our last tool, the Tableau Server API Download Image tool,  tell Alteryx where to download the image to and run! 

<img width="812" alt="image4" src="https://user-images.githubusercontent.com/88531833/135098714-8ea78a4e-3cb1-4a9e-be28-2c1009bf90ff.png">


https://user-images.githubusercontent.com/88531833/135091112-a31a1bbd-9284-4790-ab31-5ca599bb197b.mp4

# More information

We are looking forward to hearing your feedback on these tools and your use cases.

You’re always welcome to reach out to info@inviso.dk with ideas or feedback. These tools are a 1.0 version, but we know that so much else can be built. If your use case goes outside the scope of downloading a dashboard as a png, let us know and we could build that functionality in.

Until then though, you can always use tools 1 and 2, and continue the old custom approach for part 3. This might be relevant if you want to:

- Download data from a view
- Download as something other than png


