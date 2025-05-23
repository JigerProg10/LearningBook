# making nodejs api


#### initialize node app.
```
npm init
```

#### install express js
```
npm install express
```

#### import needed dependency with a const name
```
const express = require(‘express’);
```

#### use express to create app ,then other line tells to parse requests with JSON payload.
```
const app = express();
app.use(express.json());
``` 

#### we need a port where node app should listen request for.
```
const PORT = process.env.PORT || 3000;
```
`process.env.PORT` means it overtakes any port it is provided , good for hosting on cloud services.


#### now setup node api app

```
app.listen(PORT, () => {
  console.log("Server Listening on PORT:", PORT);
});
```

#### define endpoints

use GET , POST , UPDATE , DELETE

```
app.get(“/status”, ());
```


#### add callback function for endpoints
Next, we’ll add a callback function as the second parameter, which defines what we will do when the request is called. This function has two parameters: the request object (which contains details like the HTTP method, headers, and request body) and the response object (which defines the information that we want to send). The response (res) object contains different methods of sending a response to the client, such as res.send(), res.json(), and res.render().

```
app.get(“/status”, (request, response));
```


With response.send(), we then define the response we want to return. But since we want to send back JSON, we’ll need to first define a JSON object. So, we define a status variable and create an object:
```
response.send(status) is now a function that takes the JSON object as the argument.

app.get(“/status”, (request, response) => {
   const status = {
      “Status”: “Running”
   };
   
   response.send(status);
});
```


