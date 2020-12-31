# PowerShell笔记

#### 查看当前PowerShell版本
```
PS C:\> $PSVersionTable    # 显示完整的版本信息

PS C:\> $PSVersionTable.PSVersion    # 显示版本号相关

PS C:\> $PSVersionTable.PSVersion.Major    # 显示主版本号

PS C:\> $-join($PSVersionTable.PSVersion.Major,".",$PSVersionTable.PSVersion.Minor)    # 连接主次版本号
```

#### 字符串拼接
```
# 方法一：
PS C:\> -join "a","c","e"    # 以逗号间隔字符串
a
c
e

# 方法二：
PS C:\> -join ("a","b","c")
abc

# 方法三：
PS C:\> $x = "a","b","c"
PS C:\> -join $x
abc

# 方法四：
PS C:\> "a"+"b"+"c"
abc

# 方法五：
PS C:\> "Windows","Powershell","5.0" -join " "    # 拼接前三个字符串，并以空格间隔
Windows Powershell 5.0

# 方法六：
PS C:\> $x = "Wind","sP","ershell"
PS C:\> $x -join "ow"
WindowsPowershell
```
```
# 将多行内容转换到一行
PS C:\> $a = @'
>> a
>> b
>> c
>> '@
>>
PS C:\> (-split $a) -join " "
a b c
```

#### 字符串分割
