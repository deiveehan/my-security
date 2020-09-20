
### Creating CSR

#### Create a csr.conf file 

#### Generate the CSR
```shell script
openssl req -out <my-csr>.csr -newkey rsa:2048 -nodes -keyout <my-private-key>.key -config <csr>.conf
```

#### Validating csr
openssl req -noout -text -in <my-csr>.csr | grep DNS

