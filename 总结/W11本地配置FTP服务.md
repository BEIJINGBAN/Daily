# 用ISS 在Windows 11上安装FTP



在Windows 11上设置本地FTP服务器。以下是详细指南：



## 第一部分：安装FTP服务器(IIS)



1. **启用IIS和FTP功能**：

- 打开"控制面板" > "程序" > "启用或关闭Windows功能"

  （1）先进入自带的搜素

  **![image-20250812085544415](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812085544415.png)**

  （2）进入控制面板

  ![image-20250812084417479](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812084417479.png)

  （3）点击 或右上角搜索 程序---点击 启用或关闭Windows功能

![image-20250812084503952](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812084503952.png)

- 展开"Internet Information Services" > "FTP服务器"，勾选"FTP服务"和"FTP扩展性"

- 展开"Web管理工具"，全选（结果如下图）

  ![image-20250812085339435](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812085339435.png)

- 点击"确定"并等待安装完成

![image-20250812085028487](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812085028487.png)

2. **创建FTP站点**：

- 打开"IIS管理器"(在开始菜单搜索)

  ![image-20250812085812119](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812085812119.png)

- 右键点击"站点" > "添加FTP站点"

  ![image-20250812085907049](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812085907049.png)

  ![image-20250812091008003](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812091008003.png)

- 输入站点名称和物理路径(用于存储文件的目录)

  ![image-20250812091310835](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812091310835.png)

  ![image-20250812091251922](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812091251922.png)

- 设置绑定和SSL选项(建议使用"无SSL"或"允许SSL")

  IP，下拉框选择本地，我没有SSL证书就选择无了如果有SSL的可以加上

  

  ![image-20250812091644556](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812091644556.png)

- 设置身份验证和授权信息

![image-20250812091917536](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812091917536.png)

## 防火墙配置



确保防火墙允许FTP(端口21)和SFTP(端口22)流量：



1. windows搜索栏-打开"Windows Defender防火墙" > "高级设置"

   ![image-20250812111317697](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111317697.png)

2. 添加入站规则允许TCP端口21(FTP)和22(SFTP)

3. ![image-20250812111451241](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111451241.png

   ![image-20250812111358998](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111358998.png)

   image-20250812111451241

   ![image-20250812093118687](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812093118687.png)

   ![image-20250812111527145](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111527145.png)

   ![image-20250812111557018](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111557018.png)

   ![image-20250812111620586](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111620586.png)

   

## 设置用户账号密码

- 进入IIS管理器

![image-20250812110207013](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110207013.png)

- 点击FTP身份验证

  - 禁用匿名身份验证

    ![image-20250812110342682](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110342682.png)

- 点击FTP授权规则

  - 点击添加允许规则

    ![image-20250812110450297](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110450297.png)

  - 点击指定用户-输入用户名-给定权限

    ![image-20250812110608725](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110608725.png![image-20250812110632244](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110632244.png)

- 添加 用户/密码

  - 右键此电脑-管理

  ![image-20250812110730418](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110730418.png)

  - 计算机管理-本地用户和组-用户

    ![image-20250812110859952](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110859952.png)

  - 右键-新用户

    ![image-20250812110937753](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110937753.png)

  - 输入用户名-描述（可不写）-账号密码-用户不能更改/密码永不过期-创建

    ![image-20250812111151639](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812111151639.png)





## 测试连接



- 测试FTP：在本地文件管理系统中输入你设置的IP和端口可访问该服务器

  ![image-20250812114351674](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812114351674.png)

```
ftp://XX.XX.XX.XX：22/
```

![image-20250812110111170](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812110111170.png)

## 安全建议



1. 使用强密码或密钥认证

2. 考虑限制访问IP范围

3. 定期更新服务器软件

4. 对于生产环境，建议使用SSL/TLS加密的FTPS而非普通FTP



注意：SFTP和FTPS是不同的协议，SFTP基于SSH，而FTPS是FTP over SSL。