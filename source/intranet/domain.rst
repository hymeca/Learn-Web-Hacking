域渗透
========================================

域
----------------------------------------
域指将网络中多台计算机逻辑上组织到一起，进行集中管理的逻辑环境。域是组织与存储资源的核心管理单元，在域中，至少有一台域控制器，域控制器中保存着整个域的用户帐号和安全数据库。

NTLM认证
----------------------------------------
NTLM是NT LAN Manager的缩写，NTLM是基于挑战/应答的身份验证协议，是 Windows NT 早期版本中的标准安全协议，基本流程为：

- 客户端在本地加密当前用户的密码成为密码散列
- 客户端向服务器明文发送账号
- 服务器端产生一个16位的随机数字发送给客户端，作为一个challenge
- 客户端用加密后的密码散列来加密challenge，然后返回给服务器，作为response
- 服务器端将用户名、challenge、response发送给域控制器
- 域控制器用这个用户名在SAM密码管理库中找到这个用户的密码散列，然后使用这个密码散列来加密chellenge
- 域控制器比较两次加密的challenge，如果一样那么认证成功，反之认证失败

kerboser认证
----------------------------------------
见认证机制章中Kerberos一节。

Pass The Hash
----------------------------------------
Pass The Hash (PtH) 是攻击者捕获帐号登录凭证后，复用凭证Hash进行攻击的方式。


Pass The Key
----------------------------------------
