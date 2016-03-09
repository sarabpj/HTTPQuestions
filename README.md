## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.
  
  ```
  * protocol - it indicates the name of the protocol to be used to fetch the resource
  * domain - the main name of website, or the resource name
  * port- the port number to connect to, 
  * path - the file path from the main page. 
  * query selector- adds additional paramentos to a request comes after ?
  * anchor - uses # to set an anchor on the page, where you want to jump
  ```
  
* Name the pieces of the following urls:
  * `https://www.google.com/`
   
    ```
    * protocol - https
    * domain - www.google.com
    ```
  * `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
  
    ```
    * protocol - https
    * domain - workbook.galvanize.com
    * path - cohorts/41/learning_experiences/367`
    ```
  * `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
  
```
    * protocol - http
    * domain - localhost
    * port - 5000
    * path - /animals/puppies
    * query - onlycute=1&size=medium
    * anchor - firstpuppy
``` 

  * `https://en.wikipedia.org/wiki/
    List_of_HTTP_status_codes#4xx_Client_Error`

    
```   
    * protocal - https
    * domain - en.wikipedia.org
    * path - wiki/List_of_HTTP_status_codes
    * anchor - 4xx_Client_Error
```
    
* Can a server use more than 1 port? 

```
Yes... not sure why. A port is just a number
```
* Why is https different than http?

``` 
Https is the sercure version of HTTP. S stands for secure, and encrypts all communications between the browswer and website. 
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?


```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

```
It creates an array of puppies, the specific puppies are fido, max, and moxie

```

__HTTP Request/Response__

* Name at least 4 http verbs

```
get, delete, post, put

```

* What is each verb useful for in your own words

 ```
 Get - fetches a tartgeted resource, this does not change the server state
 
 Delete - used for removing a resource
 
 post - used to send the server information
 
 put - used to update information that was sent to server
 
 ```

* What does idempotent mean?

```
it represents an element of a set that remains unchanged in value, when operated on. 

layman: no matter what you do to it, it stays the same

```

* Name the 5 http status code ranges.  What are they used for in general?

```
It indicated whether a specific TTP request has been successfully completed. 

100 - process of being okay/ informational, request received, continuing process
200 - Success! this indicates the action requested by client was received, understood, accepted, and processed successfully.
300 - redirection, the client must take additional action to complete the request.
400 - client side error
500 - server side error


```


* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
301 means Moved Permanently, it could redirect you a  the new page, or just give you an error

```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
  
```
  * Accept - request
  * Content-type - both
  * User-agent - request
  * Set-cookies - response
  * Cache-control - both
  * Cookie - request


```
  
* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```


```
The top is a response, because it has the code 200 and the html followers. 


The bottom is a request, the give away is the Delete verb
```

__JSON__

* Describe what JSON is.  What is it used for.

```
Stands for JavaScript object Notation, it is a 'lightweight data-interchange format'. It is used to send data from the server and to client, and vice versa.

```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"} //this is already a javascript obj, HTTP does not know JS exsists so it cannot read the object as is, it needs to be parsed as JSON as a string 
```

```

var allCompany = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}')

allCompany.age

```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var allCompany = JSON.parse('{"Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}')


allCompany.Companies.map(function(x) { 
  return x.company;
});
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
```
var school = JSON.stringify(myObj)
console.log(school);
```



__MISC__

* Describe what DNS is.

```
Domanin Name System - distributed set of servers that looks up an IP address for a human readable domain


https://en.wikipedia.org/wiki/Domain_Name_System

it is a hierarchical decentralized naming system for computers, services, or any resource connected to the Internet or private network
```


* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v
--verbose is useful for debugging and to see what is happening under the hood. A line with > means "header data" sent by curl. A < is the "header data" receipved by curl. A * mean addition info provide by curl 


--X creates a custom request method to use when communicating with the HTTP server

```



* What is TCP/IP?  How does it interact with HTTP?

```
TCP/IP is the foundation protocols of the Internet, and is a two layer program. The higher layer TCP (Transmission Control Protocol) manages the assembling of a message or file into smaller packets that are transmitted over the Internet and received by a TCP layer that reassembles the packets into the original message.The lower layer IP (Internet protocal), handles the address part of each packet so it gets to the right destination. 


HTTP runs on top of TCP/IP. 

TCP/IP is a the more reliable to to exchange data, and ensure it is going to the rigth place?


```



* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No it doesn't, TCP breaks it into smaller packets. 
```