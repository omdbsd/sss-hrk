使用WebSocket，而不是shadowsocks本身的协议。

通过命令行部署
--------------

将代码clone到本地

```
$ git clone https://github.com/omdbsd/sss-hrk.git
```

创建heroku app

```
$ cd sss-hrk
$ heroku create my_sss
```

将代码push到Heroku

```
$ git push heroku main
```

配置参数

```
$ heroku config:set METHOD=rc4 KEY=whatever
```

打开 https://my_sss.herokuapp.com 即可使用。

 


客户端使用
----------

使用 `npm install` 安装相关依赖

```
$ npm install
…
```

运行客户端

```
$ node local.js -s my_sss.herokuapp.com -l 1080 -m rc4 -k whatever -r 80
server listening at { address: '127.0.0.1', family: 'IPv4', port: 1080 }
```

查看日志

```
$ heroku logs -t --app my_sss
```

支持加密方式
-----------------

- rc4
- rc4-md5
- table
- bf-cfb
- des-cfb
- rc2-cfb
- idea-cfb
- seed-cfb
- cast5-cfb
- aes-128-cfb
- aes-192-cfb
- aes-256-cfb
- camellia-256-cfb
- camellia-192-cfb
- camellia-128-cfb
