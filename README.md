# javascript-doc
javascript-doc


# fetch 

```
// Create a JSON object with the data you want to send
let data = {
  name: "John",
  age: 25,
  hobbies: ["reading", "gaming", "coding"]
};

// Stringify the JSON object
let jsonData = JSON.stringify(data);

// Use the fetch () method with the URL of the server endpoint
fetch("https://example.com/api/users", {
  // Set the HTTP method to POST
  method: "POST",
  // Set the content-type header to application/json
  headers: {
    "Content-Type": "application/json"
  },
  // Set the body to the stringified JSON object
  body: jsonData
})
  // Handle the response from the server
  .then(response => {
    // Check if the response is ok
    if (response.ok) {
      // Parse the response into a native JavaScript object
      return response.json();
    } else {
      // Throw an error if the response is not ok
      throw new Error("Something went wrong");
    }
  })
  // Do something with the parsed response
  .then(data => {
    // For example, log the data to the console
    console.log(data);
  })
  // Catch any error that might occur
  .catch(error => {
    // For example, log the error to the console
    console.error(error);
  });
```
