# go_iris_hello_world
> go语言web框架iris学习的第一个程序

<ol>
<li>git clone https://github.com/wynnforthework/go_iris_hello_world.git</li>
<li>go get -u github.com/kataras/iris</li>
<li>go run main.go</li>
</ol>

### 服务器部署过程中的问题  

app.Run(iris.Addr(":8080"))  

第一次在本机上go run main.go时，用localhost:8080 是可以访问的  
上传到vrltu服务器上后，用外网ip访问不了，误以为时因为ip简写的问题，  

改成app.Run(iris.Addr("0.0.0.0:8080"))还是访问不了，以为是端口问题

改成app.Run(iris.Addr("0.0.0.0:12345"))还是访问不了，暂时不知道什么问题，于是想传到腾讯云上试一下

腾讯云用的时centos 7,默认或用yum install git的git的版本都是1.7，git clone 会出错，更新到2.15后还是出错了，yum update nss后可以clone了。

腾讯云上成功看到hello world，可以确定是vrltu的问题了。

最后发现问题是引文防火墙引起的。。。