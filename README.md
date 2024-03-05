# Discuz X3.4 with Ldap

## 说明

公司要部署一套论坛系统, 我选择了 Discuz.

公司要求需要使用 Ldap 登录, 但是 Discuz 的 Ldap 插件居然要收费, 而且一个小插件居然要收两百多, 真是服!

财大气粗的朋友可以访问以下链接购买:

https://addon.dismall.com/plugins/tshuz_ldap.html

https://addon.dismall.com/plugins/dzw_tshuz_ldap.html

---

网上找了好久, 找到一个开源的:

http://www.codeeel.com/?p=365

但是我装到 Discuz X3.4 上之后无法使用.

---

阅读别人的代码还不如自己重新写....

本着开源开放, 互利共赢, 互通有无的精神, 我将我改好的代码开放出来供大家使用.

希望能帮助到有需要的朋友!



## 已有功能

- [x] 使用 Ldap 账号认证登录
- [x] 第一次登录会自动创建账号
- [x] 不影响 Discuz 原有的用户认证机制
- [x] 支持 Discuz X3.4 简体中文版



## 使用方法

1. 下载官方安装包: [Discuz_X3.4_SC_UTF8_20230520.zip](https://github.com/zogodo/discuz_with_ldap/raw/master/Discuz_X3.4_SC_UTF8_20230520.zip) 并安装. (安装方法请自行搜索)
2. 修改本项目 `upload/uc_client/control/user.php` 的 116~119 行配置成你们公司 Ldap 的情况.
3. 将原来的 `upload/uc_client/control/user.php` 换成本项目的 `upload/uc_client/control/user.php`
4. 完成.



## 注意事项

1. `upload/uc_client/control/user.php` 的修改记录可以查看: [add ldap](https://github.com/zogodo/discuz_with_ldap/commit/37b231d57202eec05a2cd0b7c6f20d328800a04c)
2. Discuz 限制用户名长度最多15位, 写死在代码里的无法配置, 如果你们公司的 Ldap 用户名有超过15位的, 还需要修改 `upload/uc_client/model/user.php` 和修改数据库表 `common_member` 的 `username` 字段最大长度.
3. `upload/uc_client/model/user.php` 的修改方法请查看: [fix max username len](https://github.com/zogodo/discuz_with_ldap/commit/fb1cb0a37b96a32ee072d3420dce4f408f2f27b2)

