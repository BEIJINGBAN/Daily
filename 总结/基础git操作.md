## 基础Git操作

#### 1.1 基础操作

```cmd
git init    										//初始化
git add .											//增加所有
git commit -m "备注内容" 				  			  //打备注

git clone https://.....								//克隆项目

git status											//查看状态

git restore XX										//撤销某修改
git restore --staged 								//撤销add

git remote -v  										//查看远端git连接到哪个
git remote add origin https:........    			//增加远端
git remote set-url origin https:....... 			//修改远端

git push --force-with-lease origin main 			//强制推送
git pull origin main --allow-unrelated-histories 	//强制拉取

git config user.name 			 					//查看名字
git config user.email  								//查看邮箱

git config user.name "你的名字"   		  			//设置名字
git config user.email "你的邮箱"  		  			//设置邮箱

git log											  	//查看提交历史

git branch 											//查看本地所有分支
git branch XXXX										//新建分支命名XXXX
git branch -m master main							//重命名分支+
git checkout XXXX									//切换到XXXX分支
git checkout -b XXXX								//创建并切换到XXXX分支
git merge XXXX										//将XXXX分支合并到当前分支
```



#### 1.2 备注

```cmd
Commit 		类型
feat: 		新特性或功能
fix: 		缺陷修复
docs:		文档更新
style: 		代码风格或者组件样式更新
refactor: 	代码重构，不引入新功能和缺陷修复
opt: 		性能优化
chore: 		一些不涉及到功能变动的小提交，比如修改文字表述，修改注释等
```

#### 2.详细展示

- 添加所有改动的数据

```
git add .
```

![image-20250815092149634](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250815092149634.png)

- 打上备注

```
git commit -m "备注内容" 	
```

![image-20250815092230170](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250815092230170.png)

- 推送远端

```
git push origin main
```

![image-20250812104835481](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812104835481.png)

- 查看提交历史

```
git log
```

![image-20250812164507627](C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250812164507627.png)

- 查看连接远端

```cmd
git remote -v  										//查看远端git连接到哪个
```

<img src="C:\Users\BRKJ\AppData\Roaming\Typora\typora-user-images\image-20250808085230536.png" alt="image-20250808085230536" style="zoom:150%;" />

