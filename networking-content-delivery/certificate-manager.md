### AWS Certificate Manager Export Certificate(AWS Blogpost)
```
https://aws.amazon.com/blogs/aws/aws-certificate-manager-introduces-exportable-public-ssl-tls-certificates-to-use-anywhere/
```

### CAM export certificate
- Request Certificate in acm with exported enable
- Validate domain name to prove that it is your own or control the domain for which you are requesting the 
  certificate. 
- Assign passphrase for encrypting the private key.
- Export the certificate

### 
```
openssl rsa -in /etc/nginx/certificates/your_key.pem -out /etc/nginx/certificates/your_key_nopass.pem
```


