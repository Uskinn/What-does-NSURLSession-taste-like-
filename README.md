# What-does-NSURLSession-taste-like-

---

 About a month ago I was a student at Flatiron School. I studied iOS Development. One day we had a lecture about “How the Internet Works”. In this lecture I first time tried NSURLSeesion( a tool which helps you to retrieve data from a server via HTTP/ HTTPS). I remember that it was really confused and I really did not like how it tasted. It’s taste was so complicated and dificult to understand. At that time I said to myself — “Ok. It’s edible. But I’m sure it should be something more delicious than NSURLSession.” I was right. A few days later we were introduced to cocoapod Alamofire. 
 Alamofire is amazing! After NSURSession the whole my class felt in love with Alamofire immediately from the first bite. No one wants to use NSURLSession anymore in their projects, only Alamofire. I wasn’t exception.


---

 Recetly I started a new project and I had a choice what to use there - NSURLSession or Alamofire? I chose NSURLSession. Why? Because I still can feel that NSURLSession’s confusing after taste.  As a person who love to cook and eat I can’t leave it with out attention. 


---

In this example I want to figure out how NSURLSession works. So, let’s get started. I created a new project. Then I created a new Cocoa Touch file where I’m going to work with NSURLSession and OMDB API. Inside my new file I wrote the following lines of code: 
Now line by line what it’s about.
Creating new class function  which has completion block. That completion block is taking NSDictionary and return nothing. It takes NSDictionary because I already checked what type of data I’m getting back from the URL. 
Inside the class function I create a new NSURLSession via NSURLSessionConfiguration and assign it to the defaultSessionConfiguration. DefaultSessionConfiguration because I don’t need any other configurations.
With optional binding I safely  unwrap the URL. Before I inserted this URL in my code, I used Postman to check if this URL was correct and what data I’m getting back. This URL returns a JSON dictionary.
If the URL is valid, I create a new task with that URL. The new task has a complitionHandler with data, response, and error. The data holds our data from the URL. The response shows me the status of the request returned from the server.
At part 5 I checked if data has a value. 
In this part I know that there is data. But it’s a raw data, and it must be serialized to the JSON. In do-try-catch with NSJSONSerialization class and its method JSONDataWithObject I try to serialize raw data into JSON. Then I cast JSON data to NSDictionary because Apple doesn’t know how to work with JSON.
In this part I’m simply saying that 
Catching errors if any occurred in part 6.
Here I call resume() to start data task.