# How to install SSL certificates on **namecheap.com**

## Step 1
- openssl req -new -newkey rsa:2048 -nodes -keyout server.key -out server.csr

## Step 2
- activate ssl on namecheap or reissue ssl with csr file 

## Step 3 
- verify domain with "file upload method"

## Step 4 
- download crt file and ca-bundle and concatenate these together in this way : 
```bash
cat domain.crt domain.ca-bundle >> server.crt
```

we have an error after concatenation and insert "enter character" between two content that made in server.crt to fix it  

from 

```CSR
-----END CERTIFICATE----------BEGIN CERTIFICATE-----
```

to

```CSR
-----END CERTIFICATE-----
-----BEGIN CERTIFICATE-----
```

## Step 5
- we made csr and key file and copy these file on server to this folder : `/root/ssl/`

## Step 6
- config nginx and test it, if everything is ok you can restart nginx 


