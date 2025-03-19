## 怎么使用git拉取github代码

##### 第一步：检查本地主机是否已经存在ssh key

```
cd ~/.ssh
ls
//看是否存在 id_rsa 和 id_rsa.pub文件，如果存在，说明已经有SSH Key
```

如下图所示，则表明没有所需要这俩文件

[<img src="[D:\Users\User\Desktop\git练习\images\image-20250319090259049.png](https://github.com/zjxxsr/zjx_git/blob/main/images/image-20250319090259049.png)" alt="image-20250319090259049" />](https://github.com/zjxxsr/zjx_git/blob/main/images/image-20250319090259049.png)

##### 第二步：生成ssh key

```
ssh-keygen -t rsa -C "xxx@xxx.com"
//执行后一直回车即可
ssh-keygen: 这是命令的主程序，用于生成、管理和转换认证密钥。
-t rsa: 这个参数指定了要生成的密钥类型。在这里，rsa 表示生成一个 RSA 密钥。RSA 是一种常用的加密算法，适用于大多数场景。（默认就是rsa）
-C "xxx@xxx.com": 这个参数用于为生成的密钥添加一个注释。通常，这个注释是一个电子邮件地址，用于标识密钥的用途或所有者。这里的 "xxx@xxx.com" 是一个占位符，实际使用时应替换为你的电子邮件地址。
```

生成后效果如下

![image-20250319091111437](D:\Users\User\Desktop\git练习\images\image-20250319091111437.png)

##### 第三步：获取ssh key公钥内容（id_rsa.pub）

```
cd ~/.ssh
cat id_rsa.pub
```

效果如下（由于隐私问题所以随机部分打了马赛克）

![image-20250319091300519](D:\Users\User\Desktop\git练习\images\image-20250319091300519.png)

图一

##### 第四步：Github账号上添加公钥

![image-20250319091514937](D:\Users\User\Desktop\git练习\images\image-20250319091514937.png)

![image-20250319091544485](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20250319091544485.png)

![image-20250319091731856](D:\Users\User\Desktop\git练习\images\image-20250319091731856.png)

点击New SSH key

![image-20250319091840417](D:\Users\User\Desktop\git练习\images\image-20250319091840417.png)

```
title：去一个标题

key：把cat id_rsa.pub命令的内容粘贴到输入框

然后点击Add SSH key
```

##### 5、配置你的⽤户名和邮箱

```
git config user.name 起个名称
git config user.email 邮箱，方便联系，也可以随便填
```

##### 6、添加远程仓库`origin`

![image-20250319094734528](D:\Users\User\Desktop\git练习\images\image-20250319094734528.png)

找到自己的仓库，然后点击左边的code，选择ssh，然后复制

然后在git里输入

```
git remote add origin  git@github.com:zjxxsr/zjx_git.git
//然后回车
```

##### 7、然后就是上传三件套

```
git add .
git commit -m "注释"
git push -u origin main  //main是分支名
//需要注意的是命令右边查看一下自己是在什么分支
git branch 查看当前分支
git branch 分支名  切换分支
git checkout 分支名  创建分支 
```

