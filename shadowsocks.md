

## shadowsocks的使用



#### 0x1: vps 安装shadowsocks

```php
apt install python-pip
pip install shadowsocks

#如果电脑上安装了多个python版本以及pip，注意使用的是哪个

```

  安装之后进行配置，一般使用json文件来存储，例子\(/etc/shadowsocks.josn/  可以自定义这个文件的名字和路径\)

```php
{
    "server":"xxx.xxx.xxx.xxx",#你自己的服务器ip
    "local_address":"127.0.0.1",
    "local_port":1080,#这个端口不变
    "port_password":{
    	"4567":"passwd_1",
	"5678":"passwd_2",
	"6789":"passwd_3",
	"7891":"passwd_4",
	"7879":"passwd_5"
    },
    "timeout":300,
    "method":"camellia-128-cfb",#自己选择
    "fast_open":false
}

```

 json中的server 是写你自己vps的ip地址，如果进行多个端口配置，port\_password 中 前边是端口，后边是这个端口对应的密码。

methon对应的是加密方式，一般选择 camellia-128-cfb



####  0x2：启动shadowsocks

```php
ssserver -c /etc/shadowsocks.json --log-file=/tmp/shadowsocks.log -d start
```

   -c 指定了我们配置文件的路径，这个路径上边说了可以自定义的，

   --log-file = /tmp/shadowsocks.log   是我们运行的日志文件存放位置

   -d  start后台启动   -d stop/restart



#### 0x3 : 可能遇到的问题

```php
Traceback (most recent call last):
  File "/root/miniconda3/bin/ssserver", line 10, in <module>
    sys.exit(main())
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/server.py", line 34, in main
    config = shell.get_config(False)
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/shell.py", line 262, in get_config
    check_config(config, is_local)
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/shell.py", line 124, in check_config
    encrypt.try_cipher(config['password'], config['method'])
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/encrypt.py", line 44, in try_cipher
    Encryptor(key, method)
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/encrypt.py", line 83, in __init__
    random_string(self._method_info[1]))
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/encrypt.py", line 109, in get_cipher
    return m[2](method, key, iv, op)
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/crypto/rc4_md5.py", line 33, in create_cipher
    return openssl.OpenSSLCrypto(b'rc4', rc4_key, b'', op)
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/crypto/openssl.py", line 76, in __init__
    load_openssl()
  File "/root/miniconda3/lib/python3.7/site-packages/shadowsocks/crypto/openssl.py", line 52, in load_openssl
    libcrypto.EVP_CIPHER_CTX_cleanup.argtypes = (c_void_p,)
  File "/root/miniconda3/lib/python3.7/ctypes/__init__.py", line 369, in __getattr__
    func = self.__getitem__(name)
  File "/root/miniconda3/lib/python3.7/ctypes/__init__.py", line 374, in __getitem__
    func = self._FuncPtr((name_or_ordinal, self))
AttributeError: /root/miniconda3/lib/python3.7/lib-dynload/../../libcrypto.so.1.1: undefined symbol: EVP_CIPHER_CTX_cleanup
##这个报错来自来自于网上，自己的当时没复制,链接
https://blog.csdn.net/weixin_38950807/article/details/93489381
```



