

#### Generate CA's private key and self signed cert
```shell script
openssl req -x509 -newkey rsa:4096 -days 365 -keyout ca-key.pem -out ca-cert.pem

// validate cert
openssl x509 -in ca-cert.pem -noout -text
```
#### Generate web server's private key and certificate cigining request (CSR)
```shell script
openssl req -newkey rsa:4096 -keyout server-key.pem -out server-req.pem

```

#### Generate server certificate based on the CSR file. 
```shell script
openssl openssl x509 -req -in server-req.pem -CA ca-cert.pem -CAkey ca-key.pem -CAcreateserial -out server-cert.pen
```

#### Use
#### Frequently used commands

```shell script
openssl req // for creating CSRs


```



#FAQ
- What is X.509
   standard defininig th eformat for public key certs
   


#### Note:
- private key will have Begin encrypted private key. 
- Self signed cert will have issuer and subject as the same content. 



#### Questions:
