# Linux 生成CA证书



## 1.简介



## 2.创建CA

### 2.1 创建根证书密钥文件(自己做CA)**root.key**

>   [root@root ~]$ openssl genrsa -des3 -out root.key 
>   Generating RSA private key, 512 bit long modulus 
>   ……………..++++++++++++ 
>   ..++++++++++++ 
>   e is 65537 (0×10001) 
>   Enter pass phrase for root.key: ← 输入一个新密码 
>   Verifying – Enter pass phrase for root.key: ← 重新输入一遍密码

### 2.2 创建根证书的申请文件**root.csr**：

>   [lenin@archer ~]$ openssl req -new -key root.key -out root.csr 
>   Enter pass phrase for root.key: ← 输入前面创建的密码 
>   You are about to be asked to enter information that will be incorporated 
>   into your certificate request. 
>   What you are about to enter is what is called a Distinguished Name or a DN. 
>   There are quite a few fields but you can leave some blank 
>   For some fields there will be a default value, 
>   If you enter ‘.’, the field will be left blank. 
>   —– 
>   Country Name (2 letter code) [AU]:CN ← 国家代号，中国输入CN 
>   State or Province Name (full name) [Some-State]:BeiJing ← 省的全名，拼音 
>   Locality Name (eg, city) []:BeiJing ← 市的全名，拼音 
>   Organization Name (eg, company) [Internet Widgits Pty Ltd]:MyCompany Corp. ← 公司英文名 
>   Organizational Unit Name (eg, section) []: ← 可以不输入 
>   Common Name (eg, YOUR name) []: ← 此时不输入 
>   Email Address []:admin@mycompany.com ← 电子邮箱，可随意填
>
>   Please enter the following ‘extra’ attributes 
>   to be sent with your certificate request 
>   A challenge password []: ← 可以不输入 
>   An optional company name []: ← 可以不输入

### 2.3 创建一个自当前日期起为期十年的根证书**root.crt**

>   [lenin@archer ~]$ openssl x509 -req -days 3650 -sha1/md5 -extensions v3_ca -signkey root.key -in root.csr -out root.crt 
>   Signature ok 
>   subject=/C=CN/ST=BeiJing/L=BeiJing/O=MyCompany Corp./emailAddress=admin@mycompany.com 
>   Getting Private key 
>   Enter pass phrase for root.key: ← 输入前面创建的密码

### 2.4 将客户端证书文件**client.crt**和客户端证书密钥文件**client.key**合并成客户端证书安装包**client.pfx**

>   [lenin@archer ~]$ openssl pkcs12 -export -in client.crt -inkey client.key -out client.pfx 
>   Enter pass phrase for client.key: ← 输入上面创建的密码 
>   Enter Export Password: ← 输入一个新的密码，用作客户端证书的保护密码，在客户端安装证书时需要输入此密码 
>   Verifying – Enter Export Password: ← 确认密码

