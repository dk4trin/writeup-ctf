I was going to call this challenge babynet, but I have that baby shark song stuck in my head... doo doo, doo doo doo baby shark...
> capture.zip

When unpacking the .zip file we find the **capture.pcapng** file


![zip file!](/irisctf2023/network/img/zip-file.png "zip file")

We can open this up in Wireshark and sort the Protocols tab, so we'll see 6 packets with the HTTP protocol


![http-packets!](/irisctf2023/network/img/http-packets.png "http packets")

In this first HTTP packet
`Right-Clik > Follow > HTTP Stream`

So we noticed that there is GET request in a gif file
```
GET /babyshark.gif HTTP/1.1
Host: 192.168.56.169:8000
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive
Referer: http://192.168.56.169:8000/
Upgrade-Insecure-Requests: 1
```

Then we can exfiltrate the HTTP objects to analyze this gif file and thus obtain the flag
`File > Export Objects > HTTP > Click in babyshark.gif`


![http-export!](/irisctf2023/network/img/http-export.png "http export")


![flag!](/irisctf2023/network/img/babyshark-flag.png "flag")

`irisctf{welc0m3_t0_n3tw0rks}`