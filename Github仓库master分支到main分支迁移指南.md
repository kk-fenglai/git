# Github仓库master分支到main分支迁移指南

2020年10月1日后，`Github`会将所有新建的仓库的默认分支从`master`修改为`main`，这就导致了一些旧仓库主分支是`master`，新仓库主分支是`main`的问题，这在有时候会带来一些麻烦，因此这里提供一种方案将旧仓库的`master`分支迁移到`main`分支。

## 2 具体步骤

四步：

- 克隆原仓库
- 创建并推送`main`分支
- 修改默认分支
- 删除`master`分支

## 2.1 克隆

首先克隆一份原仓库到本地进行操作：

```bash
git clone xxxxxxx.git
```

## 2.2 创建并推送`main`

创建并切换到`main`：

```bash
git checkout -b main
```

推送`main`：

```bash
git push origin main
```

## 2.3 修改默认分支

这一步需要到`Github`中进行操作，进入仓库的设置，点击分支选项：



![img](https://pic3.zhimg.com/80/v2-a1d028f677f615d7a41a7d76a9669c1a_1440w.webp)



将其中的默认分支修改为`main`，并点击右边的`Update`，点击`Update`后会有提示有可能会影响`PR`和克隆：



![img](https://pic1.zhimg.com/80/v2-96d4409ee3f387f9ceef840d790dad30_1440w.webp)



确认修改后可以看到默认分支已经修改为了`main`：



![img](https://pic2.zhimg.com/80/v2-93b7ffacaf8504ad6093246387a5bd5d_1440w.webp)





![img](https://pic4.zhimg.com/80/v2-befa1d29eedac9af0dc20a5c66317703_1440w.webp)



## 2.4 删除`master`

删除本地`master`：

```bash
git branch -d master
```

删除远程`master`：

```bash
git push origin :master
```

这样就算成功迁移到`main`分支了。

## 2.5 测试

在仓库做一些修改后进行提交：

```bash
git add -A 
git commit -m "test main branch"
git push origin main
```

可以看到`Github`上会有对应更新。