# ToolBoxPi——一个自助工具箱  

## 初衷  

每次要找工具的时候总是找不到，往往花在找工具上的时间比真正做事的时间还要长。

前段时间一怒之下，自己买了一整套的工具私用。但这终究不是解决大家问题的办法。

其实，本来我们工具箱里的工具是齐全的。只是，用着用着就找不到了。它们并没有消失，只是躲在了世界的某个角落。

就像一个走失的孩子，需要一点线索他就能走回来。

对于我们的工具，这个线索就是——到底是谁借了他。

本来我们可以做一个表格，由专人管理，借还都在管理员处登记。

但是，对于这个长着双脚的管理员，我们不一定总能在需要的时候找得到他。

并且，在人力成本日益增长的今天，为20个人的小团队配专员管理工具，还不如人手一套工具来的便宜。

但人手一套工具，显然逆了“共享经济”这个时代的主流。且不符合我朝勤俭节约的美德。

于是，有人要搞出一点事情，解决这个问题……

## 草稿  

![这里有张图](https://github.com/qomo/ToolBoxPi/blob/master/res/skechup.jpg)

首先，要有面工具挂板墙，规划好各种工具挂置的位置与编号。

每个位置贴上对应工具的大头照片，和一个唯一的二维码。照片方便人将工具对号入座，二维码是借还登记的方便之门。

本来打算像当初搞“微信门锁”一样，搞个服务器，搞个微信公众平台，擦个越来越火热的IoT的边。

但这需要一个能够时刻连上Internet的硬件终端，可以是Arduino，可以是Raspberry Pi，或者是我们那多得不要不要的手机。还需要养一个服务器。

对于我司这样一个红线连起来可以要地球21圈，讲究多快好省的公司来说，这显然不是最佳的解决方案。同时，也不符合我勤俭节约的气质。

于是就有了第二个方案：

每个工具挂钩上有一个触动开关，挂上工具后开关被闭合。树莓派通过检查开关闭合状态来判断工具在位情况。当然，考虑到树莓派的IO数量，我们还要加一两块IO扩展板。

树莓派里面跑一个小的服务程序，开通一个Wi-Fi热点。

在树莓派里面的某个位置，存储这每个工具位的基本信息，包括：位置编号、工具名称、是否可借、在谁手上、价格、图片、借用次数等。（本着多快好省的原则，就不搞数据库了，随便来个json格式的文件就好）

当某人想借用某个工具的时候，只需拿手机扫描对应位置上的二维码，就可以借取那个工具。同时，树莓派自动登记借用者的手机号码，并修改对应工具的对应信息。

同样，归还时也只需借用者用手机扫描对应位置的二维码，同时将工具放回即可。

如果某个工具已经被借走，你也可以用手机扫描对应位置的二维码，获取借用者的电话号码。然后写一个程序，一天到晚拉他espace，催他归还。

我们还要在树莓派上面装个高音喇叭（一块钱的蜂鸣器就好了）。如果有人斗胆不扫码就取货，就用高音喇叭骂他：“蠢猪，请扫码！蠢猪，请扫码！”

让实验室的所有人都用鄙夷的眼光注视他。( ¯ □ ¯ )

## 欢迎来找茬

可能有人会说，这里面有Bug。

比如，有人借的时候，拿走一台示波器，还的时候挂上一个万用表，你这个树莓派根本无法识别。  

Whattttttttt？

你说啥？

我们都是年收入超12万的高收入人群，有必要吗？  
[国务院重磅政策：年收入12万以上的人要注意了！](http://business.sohu.com/20161023/n471084192.shtml)

