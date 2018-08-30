##1.数据类型

### 		1.1 标量类型

```
string、integer、boolean、float、double
```

### 1.2 复合类型

```
array、object
```

###1.3 特殊类型

```
resource、null
```



## 2.超全局变量

```php
$_GLOBAL、$_SERVER、$_POST、$_GET、$_REQUEST、$_FILES、$_COOKIE、$_SESSION、$_ENV
```

`$_GLOBAL`：引用全局作用域中可用的全部变量。

`$_SERVER`：服务器的相关信息。

​	`$_SERVER['GATEWAY_INTERFACE']`：返回服务器使用的CGI规范的版本。

​	`$_SERVER['DOCUMENT_ROOT']`：当前运行脚本所在的文档根目录。在服务器配置文件中定义。

​	`$_SERVER['PHP_SELF']` ：返回当前执行脚本的文件名，与 **document_root** 有关。

​	`$_SERVER['SCRIPT_FILENAME']`：当前执行脚本的绝对路径（**相对于服务器定义的文档根目录**），**CLI** 模式下为相对路径。

​	`$_SERVER['SCRIPT_NAME']`：当前执行脚本的路径。



​	`$_SERVER['REQUEST_METHOD']`：访问页面的请求方法。

​	`$_SERVER['REQUEST_TIME']`：请求服务器的时间戳。



​	`$_SERVER['QUERY_STRING']`：返回查询字符串，如果有的话，通过它进行页面访问。（问号后面的查询字符串）

​	`$_SERVER['REQUEST_URI']`：返回域名后面的字符串。



​	`$_SERVER['SERVER_ADDR']`：返回当前运行脚本所在服务器的IP地址。

​	`$_SERVER['SERVER_NAME']`：返回当前运行脚本所在的服务器的主机名。

​	`$_SERVER['SERVER_PORT']`：返回当前运行脚本所在的服务器的端口号。

​	`$_SERVER['REMOTE_ADDR']`：返回浏览器当前访问用户的IP地址。



​	`$_SERVER['HTTP_ACCEPT']`：返回来自当前请求的请求头。

​	`$_SERVER['HTTP_ACCEPT_CHARSET']`：返回来自当前请求头中的Accept-Charset的内容。

​	`$_SERVER['HTTP_ACCEPT_ENCODING']`：返回来自当前请求头中的Accept-Encoding的内容。如 gzip,deflate

​        `$_SERVER['HTTP_ACCEPT']`：返回来自当前请求头中的Host内容。

​        `$_SERVER['HTTP_REFERER']`：引导用户代理到当前页的前一页的地址。由user agent设置决定。可被伪造。



## 3.PHP全局处理函数

​ `register_shutdown_function`

​	注册一个在PHP中止时执行的函数。



`set_exception_handler`

​	设置用户自定义的异常处理函数。用于没有用try/catch块来捕获的异常。 在**exception_handler** 调用后异常会中止。异常后面的内容不会执行。

​		`exception_handler`：当一个未捕获的异常发生时所调用的函数的名称。该函数需要接受一个参数，该参数是一个抛出的异常对象。



`set_error_handler`

​	设置用户自定义的错误处理函数。 `error_types`里指定的错误类型都回绕过 **PHP** 标准错误处理程序，除非回调函数返回了 **FALSE** 。**如果错误处理程序返回了，脚本讲会继续执行发生错误的后一行**。若此时设置 **error_reporting()** 将不会起作用。不过你仍然可以获取 error_reporting 的当前值。

​	以下级别的错误不能由用户定义的函数来处理：

```PHP
E_ERROR、E_PARSE、 E_CORE_ERROR、 E_CORE_WARNING、 E_COMPLIE_ERROR、 E_COMPLIE_WARNING
```

​	 如果错误发生在脚本执行之前（比如文件上传），将不会调用自定义的错误处理程序。因为它尚未在那时注册。

​	`error_handler` 回调函数4个参数依次为 $errno, $errstr,$errfile,$errline。



`spl_autoload_register`

​	自动加载器， __auto_load() 只能加载一次。

​	

`sessioin_set_save_handler`

​	设置用户自定义会话存储函数。如果想使用PHP内置的会话存储机制之外的方式。



​	