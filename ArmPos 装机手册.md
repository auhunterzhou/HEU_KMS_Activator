# ArmPos 装机手册

## 装WIN7 英文版本

- 删除分区(Alt+D)
- PC name 设置为 `Aclas`
- 安装驱动（A3目录下)
    显卡，网卡
- 设置 [Region and Langauge]

    1. Formats : English(Australia)
    2. Location: Australia
    3. Adminstrative / change system locale : Chinese(RPC)

## 安装Teamview

    1. 设置开机启动
    2. 设置内网访问
    3. 设置密码 3277xxxx
    4. 去掉自动更新
    5. 加入防火墙   
     -- 进入【Inbound Rules】，选择Teamviewer Remote Control Application -> Advanced -> 勾选 profiles 下的全部选项：Domain, Private, Public
     -- 4个 Teamviewer Remote Control Application/Service 都要选择


## 安装 SQL Server （x86）

- Engine

    安装方式可参考安装手册

- Mangement

    安装过程中需勾选 mangement Tools(Basic)

## 安装AnyDesk

    - 设置密码 Aclas3277xxxx
    - 关闭网页后下载，并关闭自动更新

## 安装Chrome

## 系统设置

- 关闭系统通知

    `Control Panel\All Control Panel Items` 下， 设置 User Account Contol Settings 为最低

- 设置时区为 Brisbane

- 设置电源选项

    1. `Control Panel\All Control Panel Items\Power Options` 选择 [High performance] 并更改计划为全部 `never`

    2. 在`Change advanced power settings` 中将`Hard disk - Turn off hard disk after Setting:` 改为 `0`

- 关闭系统更新

    1. 右键 `Computer`，`Computer Management`, `Services and Applications`, `Service` 中，选择 【Windows Update 】 `STOP` 并选择 `Disable`

    2. 输入 `gpedit.msc` , 关闭[Administrative Templates]->[Windows Components]->[Windows Update]下九个 Setting 改为 `Disabled`

- 关闭 System Protection  

## 安装 ArmPos(CS同CY)  

- 创建数据库前需修改：  
    1. 运行权限 Shortcut 右键 Advanced, 选择 [Run as administrator]
    2. 文件夹权限: 打开安装文件夹，右键-属性-Security
       将所有用户和组都添加 Allow 权限
    3. 安装路径选择 Program Fils(x86) - CYEcrPC - UpdateDB  

## 设置防火墙权限 [Windows Firewall] - [Advanced settings]  

- Inbound Rules 添加 New Rules

1. Port `1433` - allow
2. Program `C:\Program Files (x86) \CSEcrPC\CSEcrPC.exe` - allow
3. Program `C:\Program Files (x86)\CYEcrPC\CYEcrPC.exe` - allow

- Outbound Rules 添加 New Rules  

1. Port `1433` - allow
2. Program `C:\Program Files (x86) \CSEcrPC\CSEcrPC.exe` - allow
3. Program `C:\Program Files (x86)\CYEcrPC\CYEcrPC.exe` - allow

## 设置SQL SERVER 连接

- 【SQL Server Configuration Manager】 Protocols for MSSQLSERVER 下的所有协议 Enabled  

## 设置双屏

- 【Intel HD Graphics】 Graphics Options - Output To - Extended Desktop - 任选一个