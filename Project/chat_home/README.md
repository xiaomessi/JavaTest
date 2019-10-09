### 需求分析

#### 	客户端

###### 			

#### 	服务端

​			

### Code Review

##### 	1、服务端出现大量代码冗余

​		由于服务器端在完成用户的注册、私聊、群聊、退出是都需要给用户返回一条信息(PrintStream)，因此可以将PrintStream封装成一个函数

##### 	2、发送者未知

​		发送群聊/私聊消息时，只知道是服务器端发的，不知道具体是谁发送的

##### 	3、一个客户端对应一个号

​		若当前客户端已经注册一个号了，就不能再使用userName:<username>注册其他号了

##### 	4、不要自言自语

​		自己不能给自己发消息，若自己给自己发就提示错误

##### 	5、利用正则表达式进行更加严格的校验

​		只写个userName:/G:/P:，后面啥也不写了，相当于是在注册空信息(进行字符串分割的时候，获取不到正确的userName)，发送空信息	

### Bug

##### 	1、若用户不输入byebye退出而是直接强制退出，服务器端并没有将该用户从用户Map中删除

##### 	2、文件的换行问题

##### 	3、**怎么判断发送的是文件还是消息<输出的文件有点问题，没有完全的截断>