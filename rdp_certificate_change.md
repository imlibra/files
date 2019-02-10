Windows RDP换SSL证书的方法

1. 从Let’s Encrypt什么的去申请一个证书然后导入系统证书库，双击详情获取指纹，去掉中间的空格。
2. 执行
wmic /namespace:\\root\cimv2\TerminalServices PATH Win32_TSGeneralSetting Set SSLCertificateSHA1Hash="THUMBPRINT"
如 
wmic /namespace:\\root\cimv2\TerminalServices PATH Win32_TSGeneralSetting Set SSLCertificateSHA1Hash="8347ea0ec44f3c3bbf7e138a7480921f66cb2f5e"

3. 指纹最好手动输入，因为Windows下容易出现乱码。