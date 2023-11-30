#JS POST

```
const url = 'https://api.example.com/data';
const data = { username: 'example' };

fetch(url, {
    method: 'POST', 
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify(data), 
})
.then(response => response.json())
.then(data => console.log(data))
.catch((error) => {
    console.error('Error:', error);
});
```

#Handling Errors in Fetch API 
```
fetch('https://api.example.com/data')
    .then(response => {
        if (!response.ok) {
            throw new Error('HTTP error ' + response.status);
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

#ajax post 
```
function set_session(response){
    $.ajax({
        url: host_url+'login/session',
        method: 'post',
        header: {
          Accept: "application/json",
          "Content-Type": "application/json",
        },
        data: JSON.stringify(response),
        dataType: "html",
        success: function (data) {
         if(data=='error'){
            errorAlert('invalid request');
            return false;
         }
          window.location.href = host_url+"home";
        },
        error: function (data) {
            console.log(JSON.stringify(data));
            errorAlert(data.statusText);
        },
    });
}
```

```
function profile() {
	// loader();
	$.ajax({
		url: host_url + "_route/profile",
		dataType: "html",
		success: function (data) {
			// removeLoad();
			$("#body-profile").html(data);
		},
		error: function (data) {
			console.log(JSON.stringify(data));
			errorAlert(data.statusText);
			// removeLoad();
		},
	});
}
```

```
function profile() {
	// loader();
	$.ajax({
		url: host_url + "_route/profile",
        method: 'post',
		data: {old_pass: old_pass, new_pass: new_pass},
		dataType: "html",
		success: function (data) {
			// removeLoad();
			$("#body-profile").html(data);
		},
		error: function (data) {
			console.log(JSON.stringify(data));
			errorAlert(data.statusText);
			// removeLoad();
		},
	});
}
```

#php save response
```
$json = file_get_contents('php://input');
$obj = json_decode($json, true);
$username = $obj['username'];
$pass = ltrim($obj['password']);
``
