

# git学习新手入门：

<a name="xmwVk"></a>

### 4.配置作者信息：

ctrl+l 清屏<br />subl <br />ll 显示详细列表 mkdir创建目录  pwd 查看当前在那个文件夹   cd 回家目录 ls目录列表<br />git init：在本地创建了一个版本仓库<br />这个版本仓库也可以配置信息比如我在 edu 是我创建的目录在它里面创建了版本仓库<br />我在edu这个目录下面创建了一个本地版本库，它里面也会有一个git 是edu里面的git<br />要先标识自己是谁，否则git没法用<br />![](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675578110728-51a82a14-abd0-462a-a811-941c159f0728.png%23averageHue=%233c9935&clientId=u7ce65d28-8575-4&from=paste&height=274&id=u18186263&name=image.png&originHeight=342&originWidth=1632&originalType=binary&ratio=1&rotation=0&showTitle=false&size=64153&status=done&style=none&taskId=u5c08191f-4572-4cc7-9e5d-4dc1ed22751&title=&width=1305.6)<br />global 全局的意思<br />我们创建的shou目录里面还有一个版本库 这个版本库里面有一个git文件 只要 get init 就会出现这个文件 然后给这个文件声明一下 信息<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675671914469-393538d5-4efc-4953-9cdd-1eb6d1dfd45e.png#averageHue=%23c4a968&clientId=u8dd25671-9526-4&from=paste&height=501&id=uf7a43ee7&name=image.png&originHeight=501&originWidth=1355&originalType=binary&ratio=1&rotation=0&showTitle=false&size=112294&status=done&style=none&taskId=u64dadf90-dda3-489c-8ecf-3b3c0ae09ad&title=&width=1355)

当我们写了很多项目的时候，提交都可以用全局这个帐号。

```
git config --global user.email "204628476@qq.com"
git config --global user.name "ayaj"

```

<a name="ameze"></a>

### 创建新仓库与维护久仓库：

<br />rm -rf 是删除所有的文件夹 用的时候谨慎

记住 git下面的文件一般都是项目的文件夹，项目文件夹才会放一些项目 所以主目录是不会存放项目文件的。<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675579208680-63588c18-0277-4ed8-9f59-4b691bc297ba.png#averageHue=%23020100&clientId=u7ce65d28-8575-4&from=paste&height=50&id=ud349678f&name=image.png&originHeight=63&originWidth=310&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4022&status=done&style=none&taskId=u415659bf-88f9-49ba-80c4-ef1eef2f4a3&title=&width=248)<br />维护久仓库 比如我们现在去网上想维护一个久仓库 直接复制http地址 用git命令克隆下来就可以<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675579298819-28b79f7e-528d-4663-b1f2-283ce3ea7939.png#averageHue=%23090705&clientId=u7ce65d28-8575-4&from=paste&height=181&id=ub6cbda31&name=image.png&originHeight=226&originWidth=574&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24073&status=done&style=none&taskId=ufae94ce5-8893-480c-acb3-a7e17757ea2&title=&width=459.2)<br />可以看到我去向军大叔网址扒了一个项目下来 项目的文夹名字会以v2023保存，当我们查看git下面就会有这个文件其他两个 是自己创建的
<a name="hpPM7"></a>

### git流水线操作分析：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675602884532-0a3fd0b2-724f-4fe3-b5f6-d7dab601fb5d.png#averageHue=%23f5f5f5&clientId=u7ce65d28-8575-4&from=paste&height=474&id=uea6a24c2&name=image.png&originHeight=592&originWidth=1151&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13577&status=done&style=none&taskId=ufb36d5d6-d11d-403c-9660-131d5106c00&title=&width=920.8)<br />git就是一个仓库，我们所写的一些代码都会放到git里面，来保存我们的代码<br />那么我们就想知道 代码是怎么放到仓库里面去的，它有个怎么样的流程。<br />好比现实当中 git是仓库 我们写的代码都是一件件货物我们要把货物放到仓库里面去 就要有一个车子，把货物放到车子里面运到仓库里去 那么 add 就是这个车子 把我们的代码放到车子里面 然后通过 commit 发送到git。<br />git status查看代码区，代码区可以理解就是生产的车间 生产完以后装到车然后运往仓库
<a name="NZFli"></a>

### 使用命令完成git流水线操作分析：

**touch** 创建一个空白的文夹<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675603891407-16e5a878-c486-4940-8331-cd0ff03797e3.png#averageHue=%23040303&clientId=u7ce65d28-8575-4&from=paste&height=218&id=u375f0265&name=image.png&originHeight=273&originWidth=1026&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18114&status=done&style=none&taskId=ucf1a8452-813a-412d-bb15-41b828668a4&title=&width=820.8)<br />查看代码区的状态 上面代码标识 这个文件没有被跟踪 就是没有提交到git仓库<br />查看提交到车上样子<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675604236758-5e2af66e-511f-4d1d-8ccc-d519e2ad01f6.png#averageHue=%23090707&clientId=u7ce65d28-8575-4&from=paste&height=73&id=u89dbe2e8&name=image.png&originHeight=91&originWidth=422&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5534&status=done&style=none&taskId=u3f485031-abbd-48de-93ae-a815e0ea5ab&title=&width=337.6)<br />就是绿色的 下一步就是使用 commit发送到git

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675604665074-a79793cb-9951-4d28-b134-27d2e864ebfc.png#averageHue=%23100d0a&clientId=u7ce65d28-8575-4&from=paste&height=107&id=u21f729cc&name=image.png&originHeight=134&originWidth=593&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17707&status=done&style=none&taskId=ubfa8d0da-51d3-4adf-9aac-dddcc8b0ec0&title=&width=474.4)<br />利用 commit发送到git 仓库，我们货物送到仓库都要登记吧，这是什么货物 程序也一样 用-m写一张表。<br />如果我修改了本地的文件会发生上面呢？<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675605069738-ee30d3c7-1260-434a-ab12-65bde342dd70.png#averageHue=%230a0706&clientId=u7ce65d28-8575-4&from=paste&height=129&id=u51973703&name=image.png&originHeight=161&originWidth=828&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13680&status=done&style=none&taskId=u59f1693d-c1d3-4f83-9d82-e3ebeae4175&title=&width=662.4)<br />modified a.php 表示这个文件修改了，我们重新把它放到车里发送到git仓库<br />有时候我创建了很多文件不可能一个个打上去提交 此时可以利用 git add . 就可以全部提交到车里，车里就可以直接全部发送到git仓库<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675605436651-060b9d68-316c-472e-be0e-87ccf63d7878.png#averageHue=%23050303&clientId=u7ce65d28-8575-4&from=paste&height=345&id=uad71687b&name=image.png&originHeight=431&originWidth=474&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23056&status=done&style=none&taskId=u081d2b8c-fb9a-46e2-ae3e-599943b991b&title=&width=379.2)<br />那么又会有一个疑问 有时候我并不想文件全部上传有一些我不想上传 这就会引出另一个问题
<a name="lCJ3X"></a>

### gitignore详解控制版本库文件管理：

接着上面留的疑问，有些文件我们不想上传 就需要一个版本库忽略文件配置<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675606287278-4bcdf103-af83-462b-83b2-ed416e022533.png#averageHue=%23329f13&clientId=u7ce65d28-8575-4&from=paste&height=621&id=ua23ae7df&name=image.png&originHeight=776&originWidth=1442&originalType=binary&ratio=1&rotation=0&showTitle=false&size=72730&status=done&style=none&taskId=ua45d562b-1d5c-47dd-903f-d8f1cc4ef79&title=&width=1153.6)<br />通过subl .gitignore 创建这个版本库配置，这里就可以配置那些文件不要提交<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675606860542-9cd85ab7-c569-403f-a8f0-ff3f91222612.png#averageHue=%23ae8b56&clientId=u7ce65d28-8575-4&from=paste&height=176&id=u7b8c238f&name=image.png&originHeight=220&originWidth=1204&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18836&status=done&style=none&taskId=u3e220045-b0cc-4166-a02e-41d97573b12&title=&width=963.2)<br />此时可以看到我们创建了三个文件，我们放到版本库忽略文件当中<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675606977459-3d64a5e3-18f0-4d08-b170-075a8648201d.png#averageHue=%230a0706&clientId=u7ce65d28-8575-4&from=paste&height=166&id=uc4165bdd&name=image.png&originHeight=208&originWidth=292&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7877&status=done&style=none&taskId=ube62687d-6ae8-4fc0-85a6-f9a63d5fa6e&title=&width=233.6)![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675607062925-7b508842-d643-4c24-b0c1-fbfb02e7b877.png#averageHue=%2339414a&clientId=u7ce65d28-8575-4&from=paste&height=61&id=u323a8a6c&name=image.png&originHeight=76&originWidth=276&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2974&status=done&style=none&taskId=u46757135-6ac3-4f89-bc74-baaecbac492&title=&width=220.8)<br />可以看到这样只会存放后缀名txt的文件。<br />反过来我只想 存放 b 和 c 不想存放 a<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675607912374-74059a14-8b57-46ee-a910-ab9d10f435b1.png#averageHue=%23abbc89&clientId=u7ce65d28-8575-4&from=paste&height=86&id=u9f6eb251&name=image.png&originHeight=108&originWidth=559&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6525&status=done&style=none&taskId=u66b5bf01-fa83-42c6-ad64-11bf13e5427&title=&width=447.2)<br />如果我在这个目录里面又创建了一个目录，那么如果不添加也会现实在外面所以我们也要加上![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675608571696-caf09cab-ece5-432a-a482-07972c58e1a2.png#averageHue=%230a0908&clientId=u7ce65d28-8575-4&from=paste&height=442&id=u252d0ca4&name=image.png&originHeight=553&originWidth=1250&originalType=binary&ratio=1&rotation=0&showTitle=false&size=46675&status=done&style=none&taskId=u0423e6f9-0d6b-481c-a91d-45303212074&title=&width=1000)
<a name="GRex6"></a>

### 从版本库中删除资源技巧：<br />rm 移除版本库

我们提交了文件到版本库，如果使用rm删除 这时候本地的文件也会一起删除的<br />那么有时候我提交的到版本库的文件想删除掉但是本地不想删除怎么办 不慌有这个命令git rm --cached<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675689314628-fbfb5af3-a5eb-43ba-b4e1-8375e10473ac.png#averageHue=%23080705&clientId=u8dd25671-9526-4&from=paste&height=593&id=u45a55055&name=image.png&originHeight=593&originWidth=355&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44930&status=done&style=none&taskId=u3491a78d-085d-41fe-a593-a5fbb11c699&title=&width=355)<br />可以看到本地还是存在的，只是把版本库里面的删除了
<a name="lW8bT"></a>

### 版本库中修改资料名称：

mv 改名<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675690213754-7d0e5241-fd8e-418c-8547-8c3dbf3ddad7.png#averageHue=%23090705&clientId=u8dd25671-9526-4&from=paste&height=526&id=u0bc75b36&name=image.png&originHeight=526&originWidth=607&originalType=binary&ratio=1&rotation=0&showTitle=false&size=66913&status=done&style=none&taskId=ub9f62e37-bc8d-4ab2-b2f0-5c94a1bb5e7&title=&width=607)
<a name="vQ0Gb"></a>

### 11.使用log日志查看历史操作：

每次提交都会给一个哈系字符串<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675691974379-bf3c701c-4664-4b6e-9089-56457cbacd51.png#averageHue=%23080603&clientId=u8dd25671-9526-4&from=paste&height=302&id=ue847fbd5&name=image.png&originHeight=302&originWidth=802&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30955&status=done&style=none&taskId=ua31c1b07-8a84-4673-b598-b2eaca51ed1&title=&width=802)<br />加山-p 就可以看到详细信息 还可以看到我们修改里什么内容<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675692045174-5cbd6fbb-9dd1-4c98-a7aa-15b379cc1d2d.png#averageHue=%23080604&clientId=u8dd25671-9526-4&from=paste&height=587&id=u1b397df6&name=image.png&originHeight=587&originWidth=793&originalType=binary&ratio=1&rotation=0&showTitle=false&size=51250&status=done&style=none&taskId=u1f1da7d9-e20a-4c2d-b3fa-675e3b7ddda&title=&width=793)<br />git log -p -1 --oneline --name--only    --name-status<br /> 后面的 p 是显示段落 还可以跟 数字几就是几条 --oneline 简短  --name--only 那些文件发生变化<br />--name-status 文件发生了什么变化 修改还是删除<br />git log 查看最近提交的日志 简单来说就是你最近提交里什么东西 谁提交的 什么时候提交的
<a name="SnUYe"></a>

### 12.利用amend修改最新一次提交事件

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675693351777-dc0c2901-5a6e-458e-af01-53f2f50b9fba.png#averageHue=%231b1918&clientId=u8dd25671-9526-4&from=paste&height=287&id=u70e0d96b&name=image.png&originHeight=287&originWidth=611&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30154&status=done&style=none&taskId=uc93156f7-c87a-4201-8746-b5bbc201304&title=&width=611)<br />调出vim界面 然后修改事件的名称就可以里<br />此时我们想把这两个文件也放到刚刚的日志里面怎么办<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675693793903-0b7fb62e-7dc1-4af4-9d14-6907fadfc318.png#averageHue=%23080605&clientId=u8dd25671-9526-4&from=paste&height=60&id=ud224af7e&name=image.png&originHeight=60&originWidth=309&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5513&status=done&style=none&taskId=ucfe85676-4cd8-40ce-b6c1-e4fd982b3c6&title=&width=309)<br />先把这两个放到暂存区![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675693836893-2d60242e-276c-48cf-9acd-1b896ce8ee5c.png#averageHue=%23080706&clientId=u8dd25671-9526-4&from=paste&height=55&id=ua609f788&name=image.png&originHeight=55&originWidth=287&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3274&status=done&style=none&taskId=uf64dd976-26a7-4378-badf-a86f95629d9&title=&width=287)<br />利用--amend![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675693867201-30c72c0d-b24d-4c41-80c3-c72a1a2d99f6.png#averageHue=%230e0b09&clientId=u8dd25671-9526-4&from=paste&height=43&id=ud7ce9321&name=image.png&originHeight=43&originWidth=287&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4220&status=done&style=none&taskId=u9aff77c9-4963-4f8c-9641-f2d3ab59ef5&title=&width=287)进入vim加入这两个文件就可以<br />查看日志看到      添加成功<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675693975933-e9110941-9853-4759-b7a5-ba7b431ac782.png#averageHue=%230c0a07&clientId=u8dd25671-9526-4&from=paste&height=282&id=ue980034e&name=image.png&originHeight=282&originWidth=485&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28627&status=done&style=none&taskId=u4869b945-9bfd-4867-8d4d-36856ae5642&title=&width=485)
<a name="XDeKG"></a>

### 13.占存区中文件的管理：<br /><br />

有时候呢，我们可能有些文件不想放到占存区里面都是手快了，怎么移回去呢，利用<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675755059437-b552ec56-246d-4380-84bd-c5a9d749379f.png#averageHue=%23100e0c&clientId=u8dd25671-9526-4&from=paste&height=57&id=u29949a80&name=image.png&originHeight=57&originWidth=329&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4887&status=done&style=none&taskId=u1e5bdb9c-80ce-47e8-81db-9c0247b681f&title=&width=329)git rm --cacher 文件名<br />这个时候如果我们这个文件已经提交到仓库里了，我们在本地里又改了一下这个文件，那么我们第二次上传这个文件又想移出来怎么办<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675755220422-8e94824e-83b5-43e8-b7ea-7dc2704820f4.png#averageHue=%230c0a08&clientId=u8dd25671-9526-4&from=paste&height=318&id=ud8f21d68&name=image.png&originHeight=318&originWidth=369&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23917&status=done&style=none&taskId=u75a38025-f6b1-4b76-b9ae-4fe28c8f8f5&title=&width=369)第二次提交 利用 git restore --staged 文件名就可以移出来<br />如果想让这次文件里面的内容也变成第一次提交的内容就可以用![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675755301123-0c8c7337-3d20-437d-b95d-44aa935764a5.png#averageHue=%230a0907&clientId=u8dd25671-9526-4&from=paste&height=55&id=ue9a36394&name=image.png&originHeight=55&originWidth=208&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3147&status=done&style=none&taskId=u7eac9e60-669d-4dbf-9d33-c4019aa2e78&title=&width=208)
<a name="Tu8XY"></a>

### 14.利用alias命令起别名提高效率：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675757038627-dfaa9829-04ae-4360-9687-4b946bdfb742.png#averageHue=%23298d11&clientId=u8dd25671-9526-4&from=paste&height=680&id=u16d4045c&name=image.png&originHeight=680&originWidth=919&originalType=binary&ratio=1&rotation=0&showTitle=false&size=76376&status=done&style=none&taskId=ua68e3740-e736-4b9c-a8ff-50ab5693519&title=&width=919)<br />可以提高效率，节省这些重复利用的关键字
<a name="oZoNT"></a>

### 15.git分支：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675768194663-c51cc018-ef37-4ade-9aa3-aba62d580c93.png#averageHue=%23f4f3f3&clientId=u8dd25671-9526-4&from=paste&height=637&id=u4b28c489&name=image.png&originHeight=637&originWidth=1150&originalType=binary&ratio=1&rotation=0&showTitle=false&size=101776&status=done&style=none&taskId=u6b731a6c-9b8a-42b1-8978-c49e7e7de77&title=&width=1150)<br />分支就是我们一次次提交代码会形成一条主分支 master 然后我们可能会遇到一些bug或者错误可以开辟一些分支来添加功能 每个分支也是隔开的，完成以后重新添加到主分支
<a name="llRg5"></a>

### 16.branch分支基本管理操作：

使用branch可以查看分支 前面的星号就是表示你当前在那个分支：<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675768625025-39fbdee6-75f9-4c21-8287-b1423878d2c8.png#averageHue=%23090706&clientId=u8dd25671-9526-4&from=paste&height=45&id=u5f6d559f&name=image.png&originHeight=45&originWidth=185&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2287&status=done&style=none&taskId=uc793c254-6267-4d6d-b268-5e0f2510da6&title=&width=185)<br />创建分支 git branch 分支名<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675768732136-5f7270b3-43e7-4027-a605-0f0e2ff191bb.png#averageHue=%23050403&clientId=u8dd25671-9526-4&from=paste&height=148&id=ub1fbee78&name=image.png&originHeight=148&originWidth=254&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7344&status=done&style=none&taskId=u26dcc9f0-9b38-4925-9260-c6c00452e16&title=&width=254)<br />切换分支<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675768775768-3e460abc-7924-4778-9faf-0119c2faca62.png#averageHue=%230a0807&clientId=u8dd25671-9526-4&from=paste&height=173&id=u8eaa7cc2&name=image.png&originHeight=173&originWidth=328&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13752&status=done&style=none&taskId=u65ba3de9-ce8b-4958-afe5-1592c7eea16&title=&width=328)<br />不同分支下面创建的代码都是不相通的 在ask下面创建的文件 提交里 回到主分支里面是不会显示的<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675769355243-a2ba82d0-6d24-41af-9640-7882bfcffb96.png#averageHue=%23050403&clientId=u8dd25671-9526-4&from=paste&height=790&id=u0df42371&name=image.png&originHeight=790&originWidth=750&originalType=binary&ratio=1&rotation=0&showTitle=false&size=117992&status=done&style=none&taskId=uffa4de70-8731-4f7b-8bd7-96e96151826&title=&width=750)<br />这里就执行里两个命令创建bbs分支 并切换到这个分支<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675769493444-bbfe6f68-ae21-43fe-bc4d-adde33fb549e.png#averageHue=%230b0907&clientId=u8dd25671-9526-4&from=paste&height=68&id=ue6585784&name=image.png&originHeight=68&originWidth=412&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5281&status=done&style=none&taskId=u5141e0ac-988b-438f-82f7-4268ba6969e&title=&width=412)
<a name="fJEY7"></a>

### 17.合并分支删除分支：

总结当我们这块分支代码已经结束写完了我们就可以把它添加到主分支里面，添加完这个分支就没用里然后删除就可。<br />利用 merge 跟上分支名 就可以合并这个分支到主分支里面<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675770034994-bcf9eb0a-327f-4cd0-93da-efae3ff62a94.png#averageHue=%230c0a08&clientId=u8dd25671-9526-4&from=paste&height=258&id=udb2eddaa&name=image.png&originHeight=258&originWidth=343&originalType=binary&ratio=1&rotation=0&showTitle=false&size=21331&status=done&style=none&taskId=u9939cb74-4cec-47c7-99f0-8bd21fab83c&title=&width=343)<br />删除分支<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675770116880-a1f8ccd1-3ae2-4a0d-9316-bf29695229f6.png#averageHue=%23090705&clientId=u8dd25671-9526-4&from=paste&height=179&id=u400fca9e&name=image.png&originHeight=179&originWidth=403&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16999&status=done&style=none&taskId=ubf85fa09-6a16-4e8a-b923-0c527dde21d&title=&width=403)
<a name="cECcv"></a>

### 18.正确处理分支冲突：

怎么看待分支冲突 主分支提交里一个文件 然后我创建里两个分支 ask 和bbs 然后在这两个分支里面都改变了这个文件注意一点 这个时候文件里面的内容就是 你主分支提交的内容 我们在两个分支改这个文件是没有问题的 但是当我们合并的话就会出现问题，比如下方我先合并里 ask 发现正常 然后合并bbs里面就报错里 显示有冲突让你解决，然后我们使用vim打开就可以看到 我们可以选择要保存那个文件，如果都保存也可以。<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675772056162-638fa8b1-b0cc-4aa8-b3b7-a838031c4eff.png#averageHue=%23937953&clientId=u8dd25671-9526-4&from=paste&height=780&id=u18178b37&name=image.png&originHeight=780&originWidth=646&originalType=binary&ratio=1&rotation=0&showTitle=false&size=252626&status=done&style=none&taskId=u0b2df5e0-5748-47f6-8a62-217ad229e43&title=&width=646)
<a name="Hn8ma"></a>

### 19.分支管理merged及分支强制删除：

:::info
git branch --merged //查看已经合并的分支<br />git branch --no-merger 查看没有合并的分支<br />git branch -D      一般来说没有合并的分支是不可以删除的 这是git提醒你有时候怕你删错但如果你是真的不想这个分支就加上大D

:::
<a name="cnPc9"></a>

### 20.标准的分支操作工作流：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675830795298-d5f80337-06fe-49af-b045-48aad211f1f6.png#averageHue=%23f3f3f3&clientId=u8dd25671-9526-4&from=paste&height=574&id=u9205ffbc&name=image.png&originHeight=574&originWidth=1225&originalType=binary&ratio=1&rotation=0&showTitle=false&size=67216&status=done&style=none&taskId=ue4633c84-4740-4884-96ed-3c1a5a8dafb&title=&width=1225)<br />首先肯定有稳定分支，然后稳定分支会有一个develog这个一看就是项目 然后这个项目肯定还有各种各样的功能在生成各种各样的分支 每个分支 写完以后在放到项目分支里面
<a name="nngh3"></a>

# git进阶：

<a name="NScH1"></a>

### stash临时储存区：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675831583466-2569e2b3-77b8-4990-93c5-64e9397b1d03.png#averageHue=%23070605&clientId=u8dd25671-9526-4&from=paste&height=916&id=u4632a425&name=image.png&originHeight=916&originWidth=900&originalType=binary&ratio=1&rotation=0&showTitle=false&size=93393&status=done&style=none&taskId=u01bea6d5-3c7e-41ed-abce-2fa0f3b1608&title=&width=900)<br />我们在ask分支里面已经提交里一次，但是这个时候我想修改一下然后修改完以后提交第二次的时候 我想切换到别的分支是切换不了的 会报错 让你解决ask分支，这个时候我不想结束这个暂存区里面的文件，但是我又想切换到别的分支该怎么办，就出现了临时储存区。<br />利用git stash就临时暂存起来了，git stash list 查看<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675831767009-b18d36be-6c47-4fb1-892e-6911d9faff4a.png#averageHue=%23070605&clientId=u8dd25671-9526-4&from=paste&height=206&id=ude9cb834&name=image.png&originHeight=206&originWidth=1162&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24359&status=done&style=none&taskId=ubf5e0fba-911a-4277-aec5-3366d2de405&title=&width=1162)<br />此时我们就可以切换到别的分支进行操作，操作完以后回到分支 然后利用<br />git stash apply 就可以恢复分区<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675834448246-807c6ded-7f68-4d81-8315-c397dcfc2f6a.png#averageHue=%23090807&clientId=u8dd25671-9526-4&from=paste&height=272&id=u72ce2d8f&name=image.png&originHeight=272&originWidth=1132&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28967&status=done&style=none&taskId=u09cef4e6-866b-47cf-8f92-3ff9ea95539&title=&width=1132)<br />如果不想要这个占存区可以利用git stash drop stash@{0} 后面的是第几个暂存<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675834624859-60e66f80-5333-4769-853a-88fcfc6224d8.png#averageHue=%23100e0d&clientId=u8dd25671-9526-4&from=paste&height=59&id=u17547207&name=image.png&originHeight=74&originWidth=1020&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10254&status=done&style=none&taskId=u26ca003a-f79c-4ceb-a46f-2e527a6a5ab&title=&width=816)
<a name="iIFxi"></a>

### 生成zip代码发布压缩包：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675836289391-081ab7b4-d66f-417c-8684-15627feb8cdb.png#averageHue=%23080706&clientId=u8dd25671-9526-4&from=paste&height=64&id=uce2383b0&name=image.png&originHeight=80&originWidth=1163&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9678&status=done&style=none&taskId=u4fcd37e9-5f1c-46a4-8fdc-78dfe8419e9&title=&width=930.4)
<a name="CjlVP"></a>

### 使用系统别名定义git全局指令：

<a name="KxxvZ"></a>

### ![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675837017265-2391d431-64d3-4aee-aa0f-20fc17310b70.png#averageHue=%23384049&clientId=u8dd25671-9526-4&from=paste&height=643&id=ucbed7328&name=image.png&originHeight=804&originWidth=1009&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42384&status=done&style=none&taskId=uafc6f65b-ab62-44c4-b862-00f52616877&title=&width=807.2)

gs 查看代码状态<br />gc 提交代码 并填信息<br />gl 查看日志<br />gb 查看分支<br />ga 提交到暂存区<br />go 切换分支 后面跟分支名<br />gp 
<a name="LU2Ze"></a>

### 合并分支产生的问题：

我们在主分支master写了一个master.php的文件 然后提交 提交完以后创建里一个分支交ask分支 然后ask分支也写了一个文件 叫ask.php文件 我们也提交 这个时候主分支合并是没有什么问题的，那么怎么样会产生分支合并的问题呢，我们回到里主分支 又修改里一些内容提交 这个时候我们在合并分支就会产生分支合并的问题<br />这张图是没有问题的 主分支没有修改：<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675839203321-94f12d38-2972-4160-ae3e-74386aaffd91.png#averageHue=%23060504&clientId=u8dd25671-9526-4&from=paste&height=298&id=ue73f84a2&name=image.png&originHeight=372&originWidth=1308&originalType=binary&ratio=1&rotation=0&showTitle=false&size=51339&status=done&style=none&taskId=ue94dd4a0-8a0d-4906-b8c6-86c28b0e9d3&title=&width=1046.4)<br />修改里主分支内容并提交，并合并ask子分支，可以看到下面发生里变化合并了<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675840900074-014587c0-520c-4e09-889b-3edaba032a8f.png#averageHue=%23040303&clientId=u8dd25671-9526-4&from=paste&height=706&id=ud40e6d87&name=image.png&originHeight=883&originWidth=1560&originalType=binary&ratio=1&rotation=0&showTitle=false&size=127771&status=done&style=none&taskId=u140f04b6-f4ad-4650-957d-c7366d4f22a&title=&width=1248)<br />利用rebase把提交点往后面移<br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675841181567-59ade711-4936-4442-ba2a-5069a1236520.png#averageHue=%231d1e22&clientId=u8dd25671-9526-4&from=paste&height=193&id=uecb96cbe&name=image.png&originHeight=241&originWidth=843&originalType=binary&ratio=1&rotation=0&showTitle=false&size=224324&status=done&style=none&taskId=u3b3ead0c-9a07-40ef-ad76-3d9019c1aea&title=&width=674.4)
<a name="pxlx8"></a>

### 国内国外项目托管平台：

给github添加ssh密钥 然后拉取到本地 本地提交一些文件肯定是没用的 要利用git push推送的服务器上面就有里，这里只是克隆下来  <br />![image.png](https://cdn.nlark.com/yuque/0/2023/png/34941651/1675845716809-61644b93-83d8-44e2-bf73-1cfa9c3d921c.png#averageHue=%2382817f&clientId=u8dd25671-9526-4&from=paste&height=302&id=u8ecb1a52&name=image.png&originHeight=378&originWidth=1304&originalType=binary&ratio=1&rotation=0&showTitle=false&size=63920&status=done&style=none&taskId=u1968e1a6-3f02-4bd9-b658-8362b3c7a66&title=&width=1043.2)

ls 查看当前目录<br />**touch** 创建一个空白的文夹<br />ll 显示详细列表 mkdir创建目录  pwd 查看当前在那个文件夹   cd 回家目录<br />git init：在本地创建了一个版本仓库<br />git status查看代码区<br />subl .gitignore 版本库
