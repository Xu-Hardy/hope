### windows 管理域

管理windows自带的AD域,需要启动一台windows sever进行,如果自动加域没有生效,那么需要手动去加域

![](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240206182416054-20240206182456948.png)



### 手动加域

(最好是使用英文的winsever)

如果需要手动加域的话,需要两个步骤1. 修改DNS 2. 修改OS内部的域的名字.

#### 添加DNS

```cmd
%SystemRoot%\system32\control.exe ncpa.cpl
```

使用上述命令找到系统内部的网卡,然后把DNS地址修改成AD的DNS

![image-20240207151849136](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240207151849136.png)

![image-20240207151915093](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240207151915093.png)







#### 修改域名字

```powershell
%SystemRoot%\system32\control.exe sysdm.cpl
```

![image-20240207154251609](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240207154251609.png)

需要注意的是,这里需要域管理员输入用户密码,而且修改完域需要重启才能生效,在系统加入域之后就可以使用域账户来登陆.格式是corp.example.com\admin

### 安装AD管理工具

这里一定是要使用windows sever,如果是windows client则不能使用这个工具.

这里推荐使用英文的OS版本,不然汉化的系统和文档顺序对不上.安装下列组件即可.

![安装 Microsoft AD 工具时，“添加角色和功能向导” 功能树中包含所选工具。                     ](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/ms-install-ad-tools.png)

### 新建用户和用户组

安装完组件之后即可使用这个命令:

```cmd
%SystemRoot%\system32\dsa.msc
```

然后在这里找到新建的AD,就可以进行新建用户,新建用户组,然把用户关联到组了.

![           显示示例组织结构的 Active Directory 用户和计算机工具。         ](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/create-security-groups-OU.png)



### EC2 windows 加入域的文档：



自动加入

https://docs.aws.amazon.com/zh_cn/directoryservice/latest/admin-guide/join_windows_instance.html



手动加入

https://docs.aws.amazon.com/zh_cn/directoryservice/latest/admin-guide/join_windows_instance.html



安装管理工具

https://docs.aws.amazon.com/zh_cn/directoryservice/latest/admin-guide/ms_ad_install_ad_tools.html



创建用户

https://docs.aws.amazon.com/zh_cn/directoryservice/latest/admin-guide/ms_ad_manage_users_groups_create_user.html
