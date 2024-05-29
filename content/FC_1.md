<h1>CORS</h1>
<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/28559296-5847-453e-aea4-96b130c7a96b" width="100%" height="50%">
</center>

<!-- ![A4 - 19](https://github.com/priyajani028/Funtent/assets/87660206/28559296-5847-453e-aea4-96b130c7a96b) 
![A4 - 18](https://github.com/priyajani028/Funtent/assets/87660206/6ba6c0a8-2f12-4150-a5d7-28ba4574deee)
![A4 - 17](https://github.com/priyajani028/Funtent/assets/87660206/29190d18-1295-44d2-9fe0-85d8477f7e94)
![A4 - 16](https://github.com/priyajani028/Funtent/assets/87660206/1d1e4ec1-4434-495c-b150-26828bc2bad4)
![A4 - 15](https://github.com/priyajani028/Funtent/assets/87660206/ce4e3764-fc6b-4c5c-8df1-b599144f5d42)
![A4 - 14](https://github.com/priyajani028/Funtent/assets/87660206/e6576c8d-f4e3-4177-aaa3-21d4d66df208)
![A4 - 13](https://github.com/priyajani028/Funtent/assets/87660206/eabb7022-88cb-4db1-a494-16b51afbd336)
![A4 - 12](https://github.com/priyajani028/Funtent/assets/87660206/2a585638-e10d-4729-9551-151ae5ad9e9b)
![A4 - 11](https://github.com/priyajani028/Funtent/assets/87660206/ad1e5ab1-9d61-4160-84c7-8a34576b0af0)
![A4 - 10](https://github.com/priyajani028/Funtent/assets/87660206/3da10d0f-83bd-487b-aca6-4a2d7053567b)
![A4 - 9](https://github.com/priyajani028/Funtent/assets/87660206/6643b45c-7496-4ef3-812a-8547d6a2330f)
![A4 - 8](https://github.com/priyajani028/Funtent/assets/87660206/f9268c3d-c68d-45d0-843c-d722ac02236d)
![A4 - 7](https://github.com/priyajani028/Funtent/assets/87660206/4b4441c4-e198-4374-bbdd-d89288f853d7)
![A4 - 6](https://github.com/priyajani028/Funtent/assets/87660206/5e870d42-a877-41f9-a049-5dcaee155a72)
![A4 - 5](https://github.com/priyajani028/Funtent/assets/87660206/0be14010-d9be-47c4-ba99-e9202b94a2e4)
![A4 - 4](https://github.com/priyajani028/Funtent/assets/87660206/8d8b31e4-a23b-4ca0-85b8-87cba88fb784)
![A4 - 3](https://github.com/priyajani028/Funtent/assets/87660206/75078fdb-75e6-4c5f-bef4-b207b5fd9d59)
![A4 - 2](https://github.com/priyajani028/Funtent/assets/87660206/014de1b9-dcc5-459b-8261-2916079b2edd)
![A4 - 1](https://github.com/priyajani028/Funtent/assets/87660206/76066ec5-acee-4ddc-89f3-d03800bd3bf4)-->

</br>
</br>
Developers and CORS error... it's like a bad dream which everytime becomes true. These errors seem to be difficult to understand first. And we often get stuck debugging and solving the issue without knowing what CORS is... 
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/76066ec5-acee-4ddc-89f3-d03800bd3bf4" width="100%" height="50%">
</center>

</br>
</br>
CORS stands for Cross-Origin Recource Sharing. It is a browser mechanism which enables controlled access to resources located outside of a given domain.
</br>
</br>

<h2>How CORS work?</h2>
</br>
When we request any resource from our own domain, there's no issue in that, because the domains are same. But when you want to perform some action based on another server, it becomes a cross-origin request. 
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/014de1b9-dcc5-459b-8261-2916079b2edd" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/75078fdb-75e6-4c5f-bef4-b207b5fd9d59" width="100%" height="50%">
</center>

</br>
</br>
To understand the cors error, let's understand what happens behind the scenes...
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/8d8b31e4-a23b-4ca0-85b8-87cba88fb784" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/0be14010-d9be-47c4-ba99-e9202b94a2e4" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/5e870d42-a877-41f9-a049-5dcaee155a72" width="100%" height="50%">
</center>

</br>
</br>
If server thinks that it is not a legit domain, then it will throw error.
</br>
</br>
The very first request that browser makes is the Preflight request. When a web application makes a cross-origin request that is not a simple request (like using custom headers, non-GET/POST/HEAD methods, etc.), the browser sends an OPTIONS request to the server before the actual request. This is to check if the server permits the cross-origin request.

The server sends 200 and sends Access-Control-Allow-Origin info & some other headers along with it.

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://domain-x.com
Access-Control-Allow-Methods: GET, POST, OPTIONS
Access-Control-Max-Age: 3600
```
This means that only domain X is only allowed to make GET and POST requests. The server will not allow any other domain request and will throw cors error.
</br>
</br>
<hr>

<h2>Different CORS HTTP headers</h2>

To understand different type of headers from the preflight request and response, let's understand with an example.

</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/4b4441c4-e198-4374-bbdd-d89288f853d7" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/f9268c3d-c68d-45d0-843c-d722ac02236d" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/6643b45c-7496-4ef3-812a-8547d6a2330f" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/3da10d0f-83bd-487b-aca6-4a2d7053567b" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/ad1e5ab1-9d61-4160-84c7-8a34576b0af0" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/2a585638-e10d-4729-9551-151ae5ad9e9b" width="100%" height="50%">
</center>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/eabb7022-88cb-4db1-a494-16b51afbd336" width="100%" height="50%">
</center>
</br>
<h3>Access-Control-Allow-Origin</h3>
The Access-Control-Allow-Origin header specifies which origins are allowed to access the resource. If the server allows any origin, it can use the wildcard *. For specific origins, it will list the exact origin.
</br>
</br>

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://example.com
```

This response indicates that the resource can be accessed by web pages from https://example.com.
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/e6576c8d-f4e3-4177-aaa3-21d4d66df208" width="100%" height="50%">
</center>

</br>
<h3>Access-Control-Allow-Credentials</h3>
The Access-Control-Allow-Credentials response header tells browsers whether the server allows cross-origin HTTP requests to include credentials.
It indicates whether the response to the request can be exposed when the credentials flag is true. It is used in conjunction with the withCredentials property of XMLHttpRequest or the credentials option of the Fetch API.
</br>
</br>

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Credentials: true
```

This response indicates that the resource can be accessed by https://example.com and allows the inclusion of credentials such as cookies or HTTP authentication.
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/ce4e3764-fc6b-4c5c-8df1-b599144f5d42" width="100%" height="50%">
</center>

</br>
<h3>Access-Control-Allow-Methods</h3>
The Access-Control-Allow-Methods header specifies the methods allowed when accessing the resource in response to a preflight request. This is necessary when the client wants to use HTTP methods other than the simple methods (GET, POST, and HEAD).
</br>
</br>

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
```

This response indicates that the methods GET, POST, PUT, and DELETE are allowed when accessing the resource from https://example.com.
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/1d1e4ec1-4434-495c-b150-26828bc2bad4" width="100%" height="50%">
</center>

</br>
<h3>Access-Control-Max-Age</h3>
The Access-Control-Max-Age header specifies how long the results of a preflight request can be cached. This reduces the number of preflight requests that need to be made.
</br>
</br>

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
Access-Control-Max-Age: 3600
```

This response indicates that the preflight request results can be cached for 3600 seconds (1 hour).
</br>
</br>

<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/29190d18-1295-44d2-9fe0-85d8477f7e94" width="100%" height="50%">
</center>


<center>
  <img src="https://github.com/priyajani028/Funtent/assets/87660206/6ba6c0a8-2f12-4150-a5d7-28ba4574deee" width="100%" height="50%">
</center>
