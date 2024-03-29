🌈HuiTongJiuZhi-auto-sign

[![](https://img.shields.io/badge/Author-ReaJason-red "作者")](https://github.com/YANGNIGHT)

## ✨项目介绍

&emsp;&emsp;伴随着疫情的到来，学校为了解在校师生的健康状况，全校师生都规定在特定的时间进行健康打卡 or 校内打卡，本项目旨在帮助使用慧通九职打卡的在校师生提供帮助，每天指定时间进行自动打卡，从每天指定时间打卡的压力中解放出来，全身心地投入到社会主义建设之中去。

&emsp;&emsp;本项目使用了 `requests`、`zmail`、`datetime` 第三方库。


## 🔰更新日志

- 2022.5.25： 本地打卡程序完成，实现单人本地打卡
- 2022.5.26： 实现邮箱推送功能，实现多人登录
- 2022.5.27： github action 自动运行
- 2022.6.2 ： 修复bug，添加账号密码错误提醒，多次打卡不在发邮件提醒


## 🎨配置文件

### 💃用户配置

- 打卡用户配置文件位于：`user.dat`
- 整个 dat 文件采用特定格式进行放置用户数据，修改用户配置务必按照文本内所提供的基础格式进行修改：**学号**、**密码**、**自己的邮箱**（每个数据之间务必使用空格来隔开数据）
- 如果多人打卡，则在上一个用户后换行输入，紧接在上个用户其后即可。


### 🤝统一推送配置
- 默认进行单独推送
- 发送消息的邮箱请在auto.py第5,6行进行修改，注意（常见邮箱中只支持QQ邮箱以及网易邮箱，其他邮箱可能报错）
- 统一推送请修改：
     （括号中的email为推送邮箱为user.dat中每一行的第三个数据）
     `server.send_mail(email, mail_content)  # email为收件人 #发送邮件`
      
     将email换为统一推送的邮箱，例如替换为'12345678@qq.com',注意引号不要删除
     `server.send_mail('12345678@qq.com', mail_content)  # email为收件人 #发送邮件`
  



## 💦使用方法（github action）

1、fork本仓库

2、将fork下来的仓库在仓库设置中调为私密仓库（所有账户信息直接放在了user.dat内，未进行任何加密，防止隐私泄露请务必进行私密设置）

3、将  auto-huitongjiuzhi/.github/workflows/auto-sign.yml 第3,4,5行前的#号去掉
    #schedule:
    #- cron: '05 23 * * *'
     
4、脚本默认在每天早上7:05进行打卡，加上延迟排队之类的大概是在7:17左右，若要进行自定义请修改.github/workflows/auto-sign.yml第六行的`- cron: '05 23 * * *'`，cron表达式请自行百度
     


## 🙋‍脚本有问题
* 有问题可提 [issue](https://github.com/YANGNIGHT/HuiTongJiuZhi-auto-sign/issues)


## 🎯ToDo

> 本人初学python，没有任何经验，全部自学然后边写边学将此脚本拼凑了出来，在写这个脚本的时候甚至连requests这些第三方库的一点相关知识都没有看过，所以程序写的很杂乱，很多重复代码，甚至连异常处理都没有（出现任何异常整个程序就崩了），只是确保了程序能勉强运行，所以如果你有任何指点或想与我交流都可以加我QQ联系。



## 📜FQA

