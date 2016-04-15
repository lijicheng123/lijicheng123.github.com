#git分支简单总结
git分支在平时开发中是非常重要的，特别是多人开发，经常涉及到代码的提交，拉取，分支的创建和合并等，下面简单介绍一下分支的创建和合并
#git分支创建
1、先到你的母分支（一般是master）    git checkout master
2、创建分支，比如命名为：dev_1      git branch dev_1

#切换分支到dev_1
git checkout dev_1

.
.
.开发代码啦
.

.
.



#提交代码
git add . 
git commit -a -m '填写你提交的描述，如改了什么，创建了什么'
#拉取代码
git pull
#push代码
git push


#合并分支
需求：将dev_1合并到master上
1、确保两个分支都提交了
2、切换到master分支上 git checkout master
3、开始合并 git dev_1 merge master
此时如果没有冲突就算合并完了
然后提交就可以，如果有冲突就先解决冲突  然后提交代码


