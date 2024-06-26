# Fishing AntiCheats - 高性能反作弊插件
> 当前支持的版本 1.14.60 - 1.20.73

 该项目是为防止bds服务器玩家作弊而创造，插件讲究极简原则（使用尽量少的代码直接解决问题，未引用第三方库），所有功能完全由c/c++及和汇编底层代码技术实现，从2018年开始开发，历史5年，不断的测试和完善至今，可以防止绝大部分作弊方式（如toolbox、gg修改器、horion、pc端各种外挂、原版自带的bug等）。

## 使用说明
* 第一步
联系作者（qq：651287998，tg：@JFishing）获取插件及授权，或者直接[赞助获取↑](http://ac.jfishing.top/donate.html "点击")
* 第二步
在bds服务器中安装加载器，例如bdx(c)、liteloader（包含lxl）、elementzero均可，如果是bdsx加载器，可以采用嵌套bdxc加载器方式，具体安装方式见各种加载器的使用说明
* 第三步
将插件（AntiCheats.dll）放入插件目录，例如liteloader的插件目录是`plugins`，bdxc的插件目录是`bdxcore_mod`
，如果是LeviLamina（LL3）加载器，同时还需将插件下载时附带的winhttp.dll文件放入bedrock_server目录（服务端根目录）
* 第四步
1.20.73及以上版本，采取文件方式录入激活码，在插件同文件夹下，创建`ac.txt`文件，将激活码输入在该文件中，启动后插件将自动激活，控制台提示了插件logo，则激活成功（激活后创建的ac.txt可删除）。
  之前的版本激活方式为：按照各加载器的方式正常启动服务器（不要使用外壳的程序启动，建议第一次直接通过bedrock_server.exe或者bedrock_server_mod.exe启动），在控制台会英文（避免乱码）提示输入激活码，如：`Please input AntiCheats auth code:`，直接输入激活码再回车（千万别在前后增加多余的字符包括回车），最后控制台提示`AntiCheats loaded success`，即激活完成。如果是面板启动的情况下，可能会有缓冲导致提示未显示，当启动卡住不动时，也可尝试输入激活码。

## 插件功能介绍
1. 修复原版各种bug（例如信标复制、猪灵刷物、经修复制、矿车刷物、空区块刷方块、荆棘复制及各种崩服等）
2. 反外挂药水快速破坏
3. 反外挂地形破坏
4. 反外挂破坏和放置创造方块（例如基岩、屏障）
5. 反外挂获取任意物品（包括副手、切石机、锻造台等）
6. 反外挂附魔
7. 反聊天刷屏、及指令刷屏
8. 反在线更换隐身皮肤
9. 反外挂刷经验
10. 反外挂飞天遁地
11. 反外挂炸服（dis包、move包、auth包等）
12. 反外挂伪昵称
13. 反外挂追踪宝箱
14. 反外挂长臂猿
15. 反外挂nbt数据修改
16. 反游戏加速功能
17. 反外挂快速自动攻击
18. 隐藏真实地图种子
19. 反物品异常堆叠
20. 清除异常附魔物品
21. 清除危险NBT物品（如nbt执行命令）
22. 红石电路速度控制
23. 弓箭自动瞄准检测
24. 支持离线登录功能（不乱背包数据）
25. 杀戮光环检测
26. 自定义禁用物品
27. 反矿透功能
28. 无落地伤害检测
29. 玩家停止发包检测
30. 防小流量dos攻击

## 配置文件（插件目录/AntiCheats/AntiCheats.conf）说明
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

#it will be executed when player cheat more than max_cheats_times, the dynamic variables are as follows：{player_name} {cheat_cause}
#当玩家作弊次数超过选项“max_cheats_times”设置的值时执行此命令, 其中可设置2个动态参数有：玩家名字-{player_name} 作弊行为-{cheat_cause}
ban_command=ban {player_name}

# it will be executed before player is baned, the dynamic variables are as follows: {player_name} {cheat_cause}
# 以下命令将在玩家被拉黑之前执行，其中可设置2个动态参数有：玩家名字-{player_name} 作弊行为-{cheat_cause}
before_ban_command=msg "{player_name}" "system detects cheating and you will be blocked"

#custom set the fake map seed, if the value is 0, it is disabled. Prevent players from creating the same map as the server locally, and then use the "/locate" command to get the building location
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
#是否允许toolbox客户端（挂端）登录，默认false是禁止toolbox登录
allow_toolbox=false

#whether the player is allowed to destroy blocks faster
#是否允许玩家快速破坏单个方块
allow_fast_destroy=true

#configure the display of cheat codes
#配置作弊代码显示，可自定义显示玩家看到的作弊内容
cheat_cause_display=001:FAC001,002:FAC002,003:FAC003,004:FAC004,005:FAC005,006:FAC006,007:FAC007,008:FAC008,009:FAC009,010:FAC010,011:FAC011,012:FAC012,013:FAC013,014:FAC0014,015:FAC015,016:FAC016,017:FAC017,018:FAC018,019:FAC019,020:FAC020,021:FAC021,022:FAC022,023:FAC023,024:FAC024,025:FAC025,026:FAC026,027:FAC027,028:FAC028,029:FAC029,030:FAC030

#whether to allow players to use custom skins
#是否允许玩家使用自定义皮肤，默认true为允许
allow_custom_skin=true

﻿#whether to enable anti-hacker mode to prevent dos attacks
#是否启用反黑客攻击模式，默认false不启用，当服务器经常网络流量异常增加或登录不了服务器时，可尝试启阻止黑客攻击，有一点性能损失
enable_anti_hacking=false
```

## 常见问题  
1. 如何更新插件？  
答：群文件下载新版，停止bds，然后删除旧版插件(AntiCheats-版本号.dll)，同目录下上传新版插件，再启动bds。（只动这一个文件就行，其他文件不要动）
2. 如何更换服务端？  
答：旧的服务端千万不要删，安装好新的服务端，确保新服务端一切正常后，再移植本插件。移植本插件需要将本插件的相关文件全部平移到新的服务端对应目录，具体文件有：
   * AntiCheats-版本号.dll（插件文件夹）
   * AntiCheats.conf（[插件文件夹]/AntiCheats/，1.19.70之前的版本在服务端文件夹）
   * anti_cheats.db（worlds文件夹下，随地图迁移，换新地图不需要迁）
   * anti_cheats.log（可选）
3. 如何自动拉黑玩家？   
答：反作弊主要目的是防止作弊，并未直接实现黑名单功能，需要通过配置文件`ban_command`参数，设置拉黑玩家指令，指令依赖第三方插件实现。例如liteloader黑名单插件：[https://github.com/lgc-LLSEDev/LLBlackBEEx/releases
](https://github.com/lgc-LLSEDev/LLBlackBEEx/releases)

## 作弊代码清单
|  代码   | 作弊行为  |
|  ----  | ----  |
| 001  | 非法客户端，如toolbox、blocklauncher  |
| 002  | 使用已禁用的物品  |
| 003  | 使用非法附魔物品  |
| 004  | 使用带有命令执行NBT的物品  |
| 005  | 破坏地形  |
| 006  | 非法破坏方块  |
| 007  | 破坏创造模式才能破坏的方块  |
| 008  | 非法放置方块  |
| 009  | 放置已禁用的方块  |
| 010  | 非法获取物品  |
| 011  | 非法附魔物品  |
| 012  | 非法合成物品  |
| 013  | 副手非法获取物品  |
| 014  | 非法堆叠物品  |
| 015  | 发送异常崩服包  |
| 016  | 昵称异常  |
| 017  | 非法修改命令方块  |
| 018  | 非法获取经验  |
| 019  | 非法增加等级  |
| 020  | 暂停发包作弊  |
| 021  | 异常位置传送  |
| 022  | 身体深入方块异常  |
| 023  | 鞘翅飞行  |
| 024  | 游泳飞行  |
| 025  | 爬墙飞行  |
| 026  | 无跌落伤害  |
| 027  | 开启游戏变速齿轮  |
| 028  | 自动瞄准  |
| 029  | 自动攻击（杀戮光环）  |
| 030  | 使用特性刷物品  |
