---
title: Testing
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```curl cURL
curl --request GET \
     --url https://petstore.swagger.io/v2/pet/findByStatus \
     --header 'accept: application/json' \
     --header 'authorization: Bearer <<apiKey>>'
```

```http HTTP
GET /v2/pet/findByStatus HTTP/1.1
Accept: application/json
Authorization: Bearer <<apiKey>>
Host: petstore.swagger.io


```

```c C
CURL *hnd = curl_easy_init();

curl_easy_setopt(hnd, CURLOPT_CUSTOMREQUEST, "GET");
curl_easy_setopt(hnd, CURLOPT_WRITEDATA, stdout);
curl_easy_setopt(hnd, CURLOPT_URL, "https://petstore.swagger.io/v2/pet/findByStatus");

struct curl_slist *headers = NULL;
headers = curl_slist_append(headers, "accept: application/json");
headers = curl_slist_append(headers, "authorization: Bearer <<apiKey>>");
curl_easy_setopt(hnd, CURLOPT_HTTPHEADER, headers);

CURLcode ret = curl_easy_perform(hnd);
```

```json Response Example
{"success":true}
```

# First set

<!-- curl@1,3 -->
<!-- http@1-3 -->

highlight lines 1 and 3 to add a description

# Second set

<!-- curl@3,4 -->
<!-- http@3,4 -->
<!-- c@7-10 -->

writing a description for 3 and 4