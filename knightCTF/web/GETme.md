When we access **http://167.99.8.90:9009/** we can see a JSON Response

![json!](/knightCTF/web/img/json-200-ok.png "json")

We can open this link using Burp Suite to work better with JSON.

As a first test, we changed the HTTP request method to see how the server behaves. Then, we send a POST Request:

![post-request!](/knightCTF/web/img/post-request.png "post request")

At this point it's very easy, we just supply what the server asks us, we add a URL parameter in our POST request

![url!](/knightCTF/web/img/url.png "url")

So we get this Response from server 

`{"success":false,"message":"Looking for flag ? Visit https:\/\/hackenproof.com\/user\/security"}`

Luckily I already had an account created at HackenProof, so I simply logged into my account and went to **https://hackenproof.com/user/security** to get the flag

![flag!](/knightCTF/web/img/kctf-flag.png "flag")
