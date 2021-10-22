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