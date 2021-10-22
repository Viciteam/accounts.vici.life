# Accounts Microservice
 - Holds Authentication for users on the vici platform

# API Documentation
- This API uses GraphQL implementation instead of the usual REST

## Several Code Examples:

### Login API

#### PHP cURL

```
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://accounts.vici.test/graphAPI",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"query\":\"mutation {\\n  login(email:\\\"eddie@test.com\\\", password:\\\"password\\\")\\n}\"}",
  CURLOPT_HTTPHEADER => [
    "Content-Type: application/json"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

#### Node.JS / Axios
```
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: 'https://accounts.vici.test/graphAPI',
  headers: {'Content-Type': 'application/json'},
  data: '{"query":"mutation {\n  login(email:\"eddie@test.com\", password:\"password\")\n}"}'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

### Register API

#### PHP cURL

```
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://accounts.vici.test/graphAPI",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"query\":\"mutation {\\n  createUser(\\n    name:\\\"Tikla Lopez\\\"\\n    email:\\\"tikla@test.com\\\"\\n    password: \\\"password\\\"\\n  ) {\\n    id\\n    name\\n    email\\n  }\\n}\"}",
  CURLOPT_HTTPHEADER => [
    "Content-Type: application/json"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

#### Node.JS / Axios
```
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: 'https://accounts.vici.test/graphAPI',
  headers: {'Content-Type': 'application/json'},
  data: '{"query":"mutation {\n  createUser(\n    name:\"Tikla Lopez\"\n    email:\"tikla@test.com\"\n    password: \"password\"\n  ) {\n    id\n    name\n    email\n  }\n}"}'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

### Get All users

#### PHP cURL

```
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://accounts.vici.test/graphAPI?id=&email=&name=",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"query\":\"{\\n  users {\\n    id\\n    email\\n    name\\n  }\\n}\"}",
  CURLOPT_HTTPHEADER => [
    "Content-Type: application/json"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

#### Node.JS / Axios
```
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: 'https://accounts.vici.test/graphAPI',
  params: {id: '', email: '', name: ''},
  headers: {'Content-Type': 'application/json'},
  data: '{"query":"{\n  users {\n    id\n    email\n    name\n  }\n}"}'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

### Get User

#### PHP cURL

```
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://accounts.vici.test/graphAPI?id=&email=&name=",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"query\":\"{\\n  user(id: 13) {\\n    email\\n    name\\n  }\\n}\"}",
  CURLOPT_HTTPHEADER => [
    "Content-Type: application/json"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

#### Node.JS / Axios
```
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: 'https://accounts.vici.test/graphAPI',
  params: {id: '', email: '', name: ''},
  headers: {'Content-Type': 'application/json'},
  data: '{"query":"{\n  user(id: 13) {\n    email\n    name\n  }\n}"}'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

### Get User by email


#### PHP cURL

```
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://accounts.vici.test/graphAPI?id=&email=&name=",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"query\":\"{\\n  getUserfromEmail(email: \\\"eddie@test.com\\\") {\\n    email\\n    name\\n  }\\n}\"}",
  CURLOPT_HTTPHEADER => [
    "Content-Type: application/json"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

#### Node.JS / Axios
```
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: 'https://accounts.vici.test/graphAPI',
  params: {id: '', email: '', name: ''},
  headers: {'Content-Type': 'application/json'},
  data: '{"query":"{\n  getUserfromEmail(email: \"eddie@test.com\") {\n    email\n    name\n  }\n}"}'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```
