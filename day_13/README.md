# Day 13: The North Pole Update 

Well, the future is here, and kids learn how to send letters less and less, let along even know how to write them! Santa recognizes that giving kids the opportunity to write to him is an important experience for them, and he doesn't want to let his lack of technology get in the way. 

In order to allow Santa to receive letters from the newer generation, create a webserver that can receive requests from kids and respond.

We plan to open up an api to all major service providers that has just two endpoints **GET /santaletter** and **POST /santaletter**. 

**GET /santaletter**: This endpoint should return html explaining how the children should format their letters. The expected format for a letter is:
```
Dear Santa,
[Body of Letter] 
 
[List of Desired Presents] 
 
Thank you!
[Child Name]
```

**POST /santaletter**: This endpoint should expect a body that contains children's letters. Parse out the child's name and what items they want for Christmas. Log out to the console the child's name followed by the first letter of each item they want for Christmas before returning with a successful response.

Three files are included with post-request bodies to test against your server. Give the output from those requests.