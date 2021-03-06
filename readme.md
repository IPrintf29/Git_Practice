Git用法练习  
========
********

项目简介  
--------
练习Git的常用语句(push, branch, merge)  
仅练习使用
********

Git语句  
--------
* 从建立到第一次提交  
    ```
    //Github新建远程仓库,本地新建文件夹作为本地仓库,进入本地仓库
    git init
    git add .                       //将工作目录所有文件导入暂存区
    git commit -m "commit info"     //暂存区文件上传至本地仓库
    //本地仓库与远程仓库建立连接
    git remote add origin git@github.com:IPrintf29/Git_Practice.git /*ssh*/
    git push -u origin master       //上传至远程仓库 master主分支
    ```
* 查看git管理文件的状态
    ```
    git status
    ```

    * 未跟踪: 文件未加入git仓库, 不参与版本控制 (新建文件并且未git add, 处于此状态)
    * 未修改: 文件已入到git仓库中, 未修改, 文件内容与本地库的文件快照内容完全一致
    * 已修改: 文件已入到git仓库中, 经过修改, 文件内容与本地库的文件快照内容不一致
    * 已暂存: 暂存状态
* 建立分支并提交
    ```
    git branch test                 //建立test分支
    git checkout test               //HEAD切换到test分支

    touch test.txt
    git add .
    git commit -m "test branch"
    git push -u origin test         //上传到远程仓库并在远程仓库创建新分支test
    ```
* 合并分支
    ```
    git checkout master
    git merge test

    git push -u origin              //全部上传至远程仓库
    ```
* 回退至某个版本
    ```
    git log --oneline               //查看commit记录的sha码
    git reset --hard 5bdb28d        //回退到sha码对应版本
    ```