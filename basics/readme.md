




#### Generating a private ca authority cert

```shell script
#Generate private key
openssl genrsa -out ca.key 2048

# Generate a CSR
openssl req -new -key ca.key -subj "/CN=KUBERNETES-CA" -out ca.csr

#Sign the certificate
openssl x509 -req -n n ca.csr -signkey ca.key -out ca.crt
```

#### Signing a user cert with the ca cert created above

```shell script
# Create a private key for the admin user
openssl genrsa -out admin.key 2048

# Create the CSR 
openssl req -new -key admin.key -subj \
    "/CN=kube-admin/O=system.masters" -out admin.csr

# Sign the CSR with the ca public key
openssl x509 -req -in admin.csr -CA ca.crt -CAKey ca.key -out admin.crt
```

