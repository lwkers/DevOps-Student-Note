在[[Github\] Github简易使用指南](https://zhuanlan.zhihu.com/p/54127454)这篇文章我们知道了如何利用git将自己的代码库上传到Github。很多时候，我们还想要复制别人的代码库，那么该如何操作呢？

## **使用fork**

想要复制别人的代码库，然后自己做修改，就一定要用到**fork**，fork和clone的区别是，clone是把远程的代码库下载到本地计算机上，而fork则是把远程的是别人的代码复制到远程的自己的Github上，成为一个**副本**，而这个副本就是你的了。

**如果用clone，当自己在本地对代码做了修改之后，是无法push的！！**

![img](https://pic2.zhimg.com/80/v2-f292f386aaa1240df76a5fb0357be791_720w.webp)



因为fork是Github上的行为，因此在git上并没有fork的命令

------



## **流程**

正确的做法如下

**1.fork别人的代码库**

转到你要使用的那个Github页面，然后**点击fork**，等待几秒钟就OK了

![img](https://pic1.zhimg.com/80/v2-c6fcf21281ab031ea8af5fe396782ef0_720w.webp)



例如我fork的项目是：[https://github.com/udacity/ud120-projects](https://link.zhihu.com/?target=https%3A//github.com/udacity/ud120-projects)，fork之后就会在我的Github上也出现了这个项目

![img](https://pic2.zhimg.com/80/v2-0347446c00a9226781c70db0a85ccbb5_720w.webp)

![img](https://pic1.zhimg.com/80/v2-5fc76c90b31c42d88fc41fcdde0815ac_720w.webp)



**2.clone到本地**

此时我们的clone就是clone自己Github空间的代码啦

![动图](https://pic1.zhimg.com/v2-7c0e55eb2dbfacefa7ded5d103f60e5c_b.webp)





**3.创建分支**

此时最好的做法是创建一个自己的分支，这样子就不会影响到原来的代码，这将是一个好习惯，虽然不创建也OK。

```text
#创建分支并且转到这个分支
git checkout -b [分支名]
```

![img](https://pic3.zhimg.com/80/v2-e3e3e18b341abc1a2b0c581feb83225e_720w.webp)



**4.在此分支下做出你的修改**

然后就可以愉快的玩耍啦~ 尽情修改代码吧

修改完可以通过`git diff`来查看修改了些什么

![img](https://pic3.zhimg.com/80/v2-3c344480945d15d5a52d74cccf450c16_720w.webp)



**5.提交你的修改**

不同的修改方式，可以用不同的命令来提交，（你也可以一个文件一个文件的提交，但是比较慢嘛）

**5.1 将有变化的文件加入暂存区**

```text
#提交所有变化
git add -A  

#提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)
git add -u    

#提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件
git add .  
```

这里我使用了`git add .`

![img](https://pic1.zhimg.com/80/v2-15761c826ff6bebf9c6a01db887fbc30_720w.webp)



**5.2 提交**

然后通过`git commit`来提交，并写简单的comments表明本次做了哪些修改

或者也可以用`git commit -m '你的comments'`直接编写





**5.3 查看提交日志**

可以用`git log --oneline --graph --decorate --all`查看提交日志

![img](https://pic2.zhimg.com/80/v2-5d98d89636784e302c5f44615805f1b5_720w.webp)



**6.push推送你的修改到Github**

然后我们可以把自己的branch推送到Github`git push origin [你的分支名]`

![img](https://pic3.zhimg.com/80/v2-9e20b8263c485d405c80f7dbcb5f410a_720w.webp)



首次push可能需要登陆Github的用户名和密码

然后打开你的Github页面，转到自己的分支，就可以看到自己的代码修改了！！哦耶~

![动图封面](https://pic3.zhimg.com/v2-04bb6feb7b022d5f4bd6f6808121aede_b.jpg)