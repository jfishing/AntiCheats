# Fishing AntiCheats - 高性能反作弊插件
 该项目是为防止bds服务器玩家作弊而创造，插件讲究极简原则（有人问我为什么不加白名单功能，只能告诉你因为性能），所有功能完全由c/c++及和汇编底层代码技术实现，从2018年开始开发，历史3年，不断的测试和完善至今，可以防止绝大部分作弊方式（如toolbox、gg修改器、pc端各种外挂、原版自带的bug等）。

## 使用说明
* 第一步
联系作者（qq：651287998，tg：@JFishing）获取插件（AntiCheats.dll）及授权
* 第二步
在bds服务器中安装加载器，例如bdx(c)、liteloader（包含lxl）、elementzero均可，如果是csr加载器，可以采用嵌套bdxc加载器方式，具体安装方式见各种加载器的使用说明
* 第三步
将插件（AntiCheats.dll）放入插件目录，例如liteloader的插件目录是`plugins`，bdxc的插件目录是`bdxcore_mod`
* 第四步
按照各加载器的方式正常启动服务器，在控制台会英文（避免乱码）提示输入激活码，如：`Please input AntiCheats auth code:`，直接输入激活码再回车（千万别在前后增加多余的字符包括回车），最后控制台提示`AntiCheats loaded success`，即激活完成。

## 插件功能介绍
1. 修复原版各种bug（例如信标复制、猪灵刷物、经修复制、矿车刷物等）
2. 反外挂药水快速破坏
3. 反外挂地形破坏
4. 反外挂破坏和放置创造方块（例如基岩、屏障）
5. 反外挂获取任意物品（包括副手、切石机）
6. 反外挂附魔
7. 反聊天刷屏、及指令刷屏
8. 反在线更换隐身皮肤
9. 反外挂刷经验
10. 反外挂飞天遁地
11. 反外挂炸服（dis包、move包等）
12. 反外挂伪昵称
13. 反外挂追踪宝箱
14. 反外挂长臂猿
15. 反外挂nbt数据修改
16. 反游戏加速功能
17. 反外挂快速自动攻击
18. 隐藏真实地图种子
19. 反物品异常堆叠
20. 清除异常附魔物品
21. 红石电路速度控制
22. 弓箭自动瞄准检测
23. 支持离线登录功能（不乱背包数据）
24. 杀戮光环检测
25. 自定义禁用物品
26. 反矿透功能

## 配置文件（BDS_SERVER/anti_cheats.conf）说明
提示："="后面的"true"的意思为"是"，"false"的意思为"否"
```
#please contact the author(qq:651287998,tg:@JFishing) for the register_code, otherwise, it cannot be used
#请联系作者（qq：651287998，tg：@JFishing）获取授权码，否则将无法使用
register_code=

#allow players to fly illegally
#允许玩家非法飞行
allow_fly=false

#allow players to move abnormally, provided that allow_fly=true
#允许玩家异常移动（钻地、远距离移动），前提是 allow_fly=true
allow_abnormal_movement=false

#allow illegal enchantments
#允许非法附魔
allow_enchant=false

#Enchantments above this level will be reset
#超过此等级的附魔将会重置
max_enchant_level=5

#customize illegal items, only numeric id are supported,such as bedrock:7
#自定义禁用物品，仅支持数字id格式，例如：基岩(7)
disabled_items=7,90,119,120,416,137,188,189

#player cheats more than this value will be kicked, 0 means no limit, it will reset when restart server
#玩家作弊次数超过此值将被踢出，0表示没有限制，它将在重启服务器时重置
max_cheats_times=20

#it will be show when player be kicked
#当玩家被踢出时此消息将显示在玩家的屏幕上
kick_message=Do not cheat!
#示例：你是作弊者吗?请问你这样作弊有什么意义?能享受游戏竞技中带来的乐趣吗?我劝你少作弊，正如生活中的欺骗，多了则失去他人信任，网络世界中也如此。这样的作弊久而久之换来的只有他人的唾弃与无尽的空虚。

#it will be executed when player cheat more than max_cheats_times
#当玩家作弊次数超过选项“max_cheats_times”设置的值时执行此命令
ban_command=ban {player_name}

#custom set the fake map seed. Prevent players from creating the same map as the server locally, and then use the "/locate" command to get the building location
#自定义在客户端显示的服务器地图种子，防止玩家本地创建一模一样的地图并使用“/locate”命令获取建筑物位置
fake_map_seed=644654234

#is it the bioelectrical server, this means no limit for special redstone machine
#是否为生电服务器，如果选项为“true”。则意味着对某些特殊红石装置无限制，可能导致卡服乃至崩服
bioelectrical_server=true

#Whether to fix the original BUG. For example, using beacons or piglins to illegally copy items
#是否修复原版“特性”，例如利用信标或猪灵非法复制物品
fix_original_bug=true

#Whether to print log to console
#是否打印日志到控制台
log_to_console=true

#The overworld chest obfuscation (anti ChestESP)
#主世界箱子混淆（反箱子透视）
chest_obfuscation=false

#The switch of online-mode. After the value of this item is changed to false, it can solve the problem of "You need to authenticate to Microsoft services" when the player logs in to the server, and ensure that the player's backpack will not be affected by closing the authentication. The premise is the server configuration file "server.properties", "whitelist=false" is configured in
#在线验证开关。此项的值修改为false后，可以解决玩家登录服务器时出现“您必须通过 Microsoft 服务身份验证”的问题，同时保证玩家背包不受关闭验证的影响。前提是服务器配置文件“server.properties”中配置了“whitelist=false”
online_authentication=true

#The tick of redstone. The range is from 0 to 20. Set to 0 to disable redstone tick. The smaller the value is, the slower the redstone machine runs and the smoother the server is. Note: that the setting value is too small will affect the player's game experience, On high performance servers, it is recommended to set the default 20
#红石的tick速度，范围为0～20。设置为0以禁用红石。值越小，红石电路运转越缓慢，服务器就越流畅。注意，设置的值过小会影响到玩家的游戏体验，在高配置服务器默认为20即可
redstone_tick_speed=20

#whether to set a lot of the virtual chest
#是否开户虚拟箱子功能，混淆真假宝箱，防止玩家通透箱子透视快速搜寻宝箱
chest_obfuscation=true

#whether to enable minecraft online authentication
#是否开启xbox在线验证，如果大量玩家进服务器过不了验证，可以考虑设置为false
online_authentication=true

#in order to prevent xray, you can set ore block offset, values range from 16 to 48
#为了防止矿透射线，可以开启矿物偏移，建议值 16 到 48，如果设置为 0 则关闭该功能
ore_block_offset=36

#whether the Toolbox client is allowed to log in
#是否禁止toolbox客户端（挂端）登录
allow_toolbox=true
```

## 常见问题  
1. 如何更新插件？  
答：群文件下载新版，停止bds，然后删除旧版插件(AntiCheats-版本号.dll)，同目录下上传新版插件，再启动bds。（只动这一个文件就行，其他文件不要动）
2. 如何更换服务端？  
答：旧的服务端千万不要删，安装好新的服务端，确保新服务端一切正常后，再移植本插件。移植本插件需要将本插件的相关文件全部平移到新的服务端对应目录，具体文件有：
   * AntiCheats-版本号.dll（插件目录）
   * anti_cheats.conf（服务端根目录）
   * anti_cheats.db（worlds）
   * anti_cheats.log（可选）
