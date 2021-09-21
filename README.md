# AntiCheats 
 该项目是为防止bds服务器玩家作弊而创造

## 配置文件说明
#提示："="后面的"true"的意思为"是"，"false"的意思为"否"
···
#please contact the author(qq:651287998,tg:@JFishing) for the register_code, otherwise, it cannot be used
#请联系作者（qq：651287998，tg：@JFishing）获取授权码，否则将无法使用
···
register_code=

#allow players to fly illegally
#允许玩家非法飞行
allow_fly=false

#allow players to move abnormally, provided that allow_fly=true
#允许玩家异常移动，前提是 allow_fly=true
allow_abnormal_movement=false

#allow illegal enchantments
#允许非法附魔
allow_enchant=false

#Enchantments above this level will be reset
#超过此等级的附魔将会重置
max_enchant_level=5

#allow use creative block, example: bedrock
#允许使用创造方块，例如：基岩
allow_use_creative_block=false

#player cheats more than this value will be kicked, 0 means no limit, it will reset when restart server
#玩家作弊次数超过此值将被踢出，0表示没有限制，它将在重启服务器时重置
max_cheats_times=0

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
