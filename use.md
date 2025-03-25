# Git的配置与使用
https://blog.csdn.net/stage98/article/details/125741395


##### 从远程仓库克隆项目至工作台
```git clone xxxx ```
 
##### 工作台上对项目进行修改后，提交到暂存区
``` git add . ```
 
##### 将暂存区的文件，提交至本地仓库
``` git commit -m "消息内容" ```
 
##### 将本地仓库上的文件，提交至远程仓库
``` git push ```


git add xx 命令可以将xx文件添加到暂存区，如果有很多改动可以通过 git add -A . 来一次添加所有改变的文件。

注意 -A 选项后面还有一个句点。 git add -A 表示添加所有内容， git add . 表示添加新文件和编辑过的文件不包括删除的文件; git add -u 表示添加编辑或者删除的文件，不包括新添加的文件


使用说明：
git add .

git commit -m "提交注释"

git push origin  分支名称
或者直接 git push

正常来说这三部就够了

# 示例：
git add .
git commit -m "note"
git push 



