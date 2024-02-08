---
title: windows修改密码
date: 2021-10-12 01:58:59
categories: windows
tags:
  - Windows
---


在 Windows 中，您可以使用命令行工具来修改用户密码。以下是一些常用的命令和方法：

1. **使用 `net user` 命令**:
   这是修改密码的最常用方法。要使用这个命令，您需要管理员权限。

   修改当前登录用户的密码:
   ```
   net user [用户名] *
   ```
   然后按提示输入新密码。

   直接为指定用户设置新密码:
   ```
   net user [用户名] [新密码]
   ```

   例如，要为用户名为 "JohnDoe" 的用户设置密码为 "newpassword123"，您可以使用以下命令：
   ```
   net user JohnDoe newpassword123
   ```

2. **使用 `wmic` 命令**:
   `wmic` 是一个强大的命令行工具，用于获取和设置系统信息。要使用它来更改密码，您可以执行以下命令：

   ```
   wmic UserAccount where Name='用户名' set Password='新密码'
   ```

   例如，为用户名为 "JohnDoe" 的用户设置密码为 "newpassword123"，您可以使用：
   ```
   wmic UserAccount where Name='JohnDoe' set Password='newpassword123'
   ```

3. **使用 PowerShell**:
   如果您更喜欢使用 PowerShell，您可以使用 `Set-LocalUser` 命令来更改本地用户的密码。

   ```powershell
   $Password = ConvertTo-SecureString '新密码' -AsPlainText -Force
   Set-LocalUser -Name '用户名' -Password $Password
   ```

   请注意，这些命令都需要您以管理员身份运行命令提示符或 PowerShell。在执行任何系统修改之前，请确保您知道自己在做什么，并始终在更改系统设置之前进行备份。