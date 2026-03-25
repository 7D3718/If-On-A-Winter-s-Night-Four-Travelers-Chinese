## 汉化声明

**版权归属**：本汉化补丁由quietfish独立制作完成并免费发布。本项目仅供学习与交流使用，游戏原名及其素材版权归原作者/开发商所有。汉化补丁作者保留汉化补丁中翻译文本的所有权和一切解释权利。

**禁止商用**：严禁将本汉化补丁用于任何商业用途（包括但不限于打包售卖、付费下载、打赏解锁等）。

**禁止二次分发**：未经许可，禁止将本仓库内容或补丁文件二次上传至其他平台（如各下载站、网盘群等）。转载请注明来源并保留相关声明。

**关于二次修改**：

- **允许**：支持玩家出于个人喜好对文本进行私下修改或润色。
- **禁止**：严禁在未获得授权的情况下，基于本补丁进行所谓的“二改发布”、“修正版发布”或抹除原作者署名后的重新包装。

**汉化补丁链接**：[7D3718/If-On-A-Winter-s-Night-Four-Travelers-Chinese](https://github.com/7D3718/If-On-A-Winter-s-Night-Four-Travelers-Chinese?tab=readme-ov-file)

## 汉化补丁使用教程

以下教程仅适用于windows系统Steam版本的*If On A Winter's Night, Four Travelers*：

1. 下载Github页面的Releases，并解压。
2. 打开Steam，在库中找到*If On A Winter's Night,Four Travelers*，右键-管理-浏览本地文件。
3. 在打开的文件资源管理器中，将解压后的所有文件复制到游戏目录下。应保证acwin.exe等文件和ioawn4t.exe在同一目录下。如图所示： <img width="1076" height="922" alt="image" src="https://github.com/user-attachments/assets/23b9b484-9a37-4f0c-aa5e-b3af0280ba02" />
4. 打开winsetup.exe，设置"Game language"为Chinese，点击"Save"（不要点击"Save and Run"，会报错）。（其他系统可尝试打开acsetup.cfg，找到[language]，将translation设置为Chinese，即translation=Chinese，保存；具体可行性未知）
5. 打开acwin.exe即可运行游戏。
6. 在Steam库中，直接点击“运行游戏”会报错是因为Steam从ioawn4t.exe启动。可在Steam库中找到本游戏，右键-属性…，在启动选项处，复制【"你的游戏路径\acwin.exe" %command%】（以本人的路径举例，我需要修改路径为"D:\SteamLibrary\steamapps\common\If On A Winter's Night Four Travelers\acwin.exe" %command%）修改启动选项，修改后即可从Steam正常启动游戏。

## 使用工具及字体

工具：

AGSUnpacker：[adm244/AGSUnpacker: An unpacker](https://github.com/adm244/AGSUnpacker)

AGS-3.6.2.17：[Adventure Game Studio](https://www.adventuregamestudio.co.uk/)

字体：

缝合像素字体（用于显示游戏内文本）：[TakWolf/fusion-pixel-font](https://github.com/TakWolf/fusion-pixel-font)

京华老宋体（制作每章标题图时使用）：[京華老宋体3.0](https://zhuanlan.zhihu.com/p/1915922891633043436)



## 对Releases中相关文件的说明

actwin.exe, SDL2.dll：来自AGS的3.6.2版本运行引擎和引擎使用的开源多媒体库。ioawn4t.exe为3.5.0引擎+游戏数据的结合程序，运行actwin.exe时，ioawn4t.exe作为游戏数据，actwin.exe作为引擎。
3.5.0版本似乎是单字节逻辑，若我们的tra文件为UTF-8，引擎会将中文当成3个独立字节渲染，导致出现乱码；改为GBK保存同样会乱码。
因为我觉得与其把trs保存为ASCII格式再重新导成tra，不如直接保存为UTF-8格式再引入支持UTF-8渲染的3.6.2版本actwin.exe, SDL2.dll。现在游戏也可以正常渲染中文所以效果差不多……吧？

agsfnt3.ttf, AGSFNT*.ttf：均为缝合像素字体文件（版本为：fusion-pixel-font-8px-proportional）。原版英文游戏自带的wfn字体文件中只有200多个字符，因此需要挂载外部字体文件以渲染中文。AGS3.6会优先加载外部挂载资源，改名便于引擎读取字体，并非二次发布。

acsprset.spr：游戏中的图像，spr格式。我只更改了开头的“1929年二月 亚洲中部某地”和前三章的标题图。如果觉得我做得很丑，那很抱歉，作者不会美工，是用GIMP随便搓的（有就不错了！）。可以在发行版中选择无spr版本。

Chinese.tra：翻译文件本体。

troubleshooting-中文版.md：对troubleshooting.pdf的中文翻译。（另一个不翻是感觉没必要）



## 游玩中可能遇见的汉化问题

1.字体看不清：8px像素字体是我能找到的显示最好的字体了。10px和12px渲染都会出现扭曲，如果使用其他普通字体显示会更加看不清。如果你有更好的字体，可以将向我推荐，或将字体复制到目录下（复制多个，然后一个个修改文件名即可）自行修改字体。

2.在《温特伯恩夫人的消逝》一章中，可能会发现"Hanging cloth（悬挂的布料）"和"Draped cloth（披盖的布料）"两个词没有翻译。原因是因为本章节有“转换场景”的设计，如果翻译了这两个词，会导致转换场景后，明明物品已经更换了形态，却依然显示“悬挂的布料”和“披盖的布料”，不显示转换形态后的中文。个人认为转换形态后的物体是什么更为重要（比如，房间中的Draped cloth下是温特伯恩夫人的竖琴），因此删去了这两处的翻译，并非我遗漏了这两处未翻译。
推测可能的原因是脚本里存在类似 `if (object.Name == "Draped cloth")` 这样的判断逻辑，导致切换场景时不显示切换场景后的物品名称。

3.在《温特伯恩夫人的消逝》一章中，会出现明明点击“谟涅摩绪涅雕像”却显示了【铭牌上写着：“勒忒，遗忘与湮灭之女神。”】的错位描述，并非翻译错误，可能的原因同1。错位的影响感觉没有那么大，因此保留了所有雕像的翻译。

4.在《无名仪式》一章中，“是的……我……来到这里是为了寻求 %s。”这句话中的%s会显示为英文。我确实翻译了三个%s相关的词，但它也确实是不显示。暂时没有搞懂为什么，目前手里没存档，等我下次再玩到这个进度的时候测试一下。目前看来暂时不影响游玩，所以就这样吧。



## 游戏中提到的其他内容

可能是一点汉化考据，如果你比较有文化可以不用看，都是一些你可能知道的东西。

#### 《温特伯恩夫人的消逝》

##### 客厅中的三本书

**'The Prophets' Paradise'《先知的天堂》**

出自《黄衣之王》。

瓦莱丽小姐提到的'Far afield a woman cried, 'I have killed him I loved!' and from a jar she poured blood upon the flowers whose petals are whiter than snow and whose hearts are pure gold.'这一段，出自《先知的天堂》中的《牺牲（The Sacrifice）》小节（想阅读原文，可看：[The King in Yellow/The Prophets' Paradise](https://en.wikisource.org/wiki/The_King_in_Yellow/The_Prophets'_Paradise)）。

此处选择的翻译：“远方的田野中，一个女人在哭喊：‘我已经杀死了我爱的他！’她将一只罐子里的鲜血浇灌在花朵上。那些花瓣比雪更白，花蕊比黄金更纯粹。”是李镭老师的译本[黄衣之王 (豆瓣)](https://book.douban.com/subject/34670056/)。

**'A Treaty on Clocks'《时钟论》**

没找到出处。也有可能是我不搞钟表。如果有知道的可以提出。

**'Without Fear of Wind and Vertigo'《不怕寒风，不顾眩晕》**

本标题出自《如果在冬夜，一个旅人》第四章，我选择了[不怕寒风，不顾眩晕 - 卡尔维诺中文站](https://www.ruanyifeng.com/calvino/2007/09/without_fear_of_wind_or_vertigo.html)这个网站的标题作为游戏内文本，而非选择萧天佑老师的《不怕寒风，不怕眩晕》是因为这个标题感觉比较对称。

瓦莱丽小姐提到的'And so you see this novel so tightly interwoven with sensations suddenly riven by bottomless chasms, as if the claim to portray vital fullness revealed the void beneath.'这段话出自威廉·韦弗的《如果在冬夜，一个旅人》的英译本（如果有人想阅读英译本，可看[If on a Winters Night a Traveller](https://dn710609.ca.archive.org/0/items/ItaloCalvino-DacaIntrONoapteDeIarnaUnCalator/Italo_Calvino_-_If_on_a_Winters_Night_a_Traveller.pdf)）第三章。此处我选择了萧天佑的译本：“这部充满了各种感觉的小说突然被这些不知深浅的漩涡隔断了，犹如你希望生活充实结果却发现了生活中的空虚。”

不知道标题选择第四章但文本是第三章有何深意……。

本章中瓦莱丽小姐和第三章中塞缪尔斯医生都说不认识卡尔维诺，故事发生在1929年（开头）甚至更早，1929年卡尔维诺刚刚6岁，所以故事的主角们都不认识他。

##### 客厅留声机的三首曲子

'Three old Viennese dances' by Fritz Keisler.《三首旧时维也纳圆舞曲》by 弗里茨·克莱斯勒

《无名仪式》中，塞缪尔斯医生也提到了这三首曲子中的一首，也是最知名的一首："The sheet music for Fritz Kreisler's 'Liebesleid'. Of course it is."“弗里茨·克莱斯勒的《爱之忧伤》乐谱。果然如此。”

'Parigi, o cara' by Giuseppe Verdi.《告别巴黎》by 朱塞佩·威尔第

歌剧《茶花女》中的选段。根据readme.pdf，游戏中是Amelita Galli-Curci & Tito Schipa演唱的版本。

此处提供网易云链接：https://music.163.com/song?id=464731834&uct2=U2FsdGVkX1/A+wo/tNA18Ya1kQE5OWxQwrbqMMXRb2s=

'My New York' by Mal Hallett and his Orchestra.《我的纽约》by Mal Hallett and his Orchestra

网易云链接：https://music.163.com/song?id=568542772&uct2=U2FsdGVkX1+UBDW4D5hkazYns0NmCtNgoPLT2XQIaQI=

（可能的）歌词链接：[My New York (ZIEGFELD FOLLIES OF 1927) – Sheet Music Singer](https://www.sheetmusicsinger.com/my-new-york/)

在《无名仪式》中，塞缪尔斯医生听的就是这首《My New York》：'There's a spot in my heart, that's becoming a part of my New York...'“我心中有一处角落，正渐渐融入我的纽约……♪”

##### 结婚报道中提到的两位艺术家

'In a move seen as uncharacteristic for the socialite, whose friendships with avant-garde artists such as Germaine Dulac or Fernand L#ger are well known...'“这位社交名媛素以与谢尔曼·杜拉克和费尔南得·莱热等先锋派艺术家私交甚笃而闻名，此番决定却一反常态……”

谢尔曼·杜拉克（Germaine Dulac，[谢尔曼·杜拉克 Germaine Dulac(豆瓣)](https://www.douban.com/personage/27247646/)），法国女导演，生于亚眠（瓦莱丽小姐的表亲们就在亚眠，大概说明她老家在这里？），20世纪20年代法国先锋派电影理论倡导者与实践者。

费尔南得·莱热（Fernand Léger），法国画家、雕塑家、电影导演。机械立体主义大师。

这三位大概是在巴黎认识并交流的。



#### 《无名仪式》

##### 仪式中的文本与书籍

'Beyond the Veil' by T. Neumann《帷幕之外》T·诺依曼 著

'The Fiery Summons' by H. Zhidkova《炽焰召唤》H·芝德科娃 著

'Planetary Correspondences' by H. Solomon《行星对应法则》H·所罗门 著

均为虚构作品（至少我没找到出处，可能是因为我不搞神秘学吧）。



开头塞缪尔斯先生提到的：

'It is a lower magical process to make the Guardian of the Threshold physically visible by producing a particular mixture of a number of substances.'“通过调配特定比例的多种物质，使‘守门人’显现于物质世界，乃是低阶魔法之路径。”

'A truly terrible spectral being confronts the magician, and he will need all the presence of mind and faith in the security of his path.'“施法者将直面一尊恐怖至极的灵体，他必须心如止水，并坚信自己所行之道。”

'Seek not, then, to cross this Threshold until thou dost feel thyself entirely free from fear and ready for the highest responsibility.'“若心中仍有恐惧，或尚未准备好迎接至高之责，切勿尝试跨越这道门槛。”

危险教堂中，威廉姆斯牧师提到的：

'I must become a perfect and glorious being, or fall a prey to corruption...'“我须成为完美与光辉之躯，否则便会沦为腐化的猎物……”

'...and should this occur, I would drag thee also down with me into a dark and corrupt world.'“……倘若如此，我亦会将你拖入那黑暗腐朽的深渊。”

Yes. And yet, it is also said that 'my Threshold is fashioned out of all the dread of the strength needed to take full responsibility for all thy thoughts and actions.'是的。然而，也有言道：“我的界限，是由担负起思想与行为全责之勇气所需的全部恐惧铸就。”



这两段都出自同一本书，鲁道夫·施泰纳（相关科普可见：[简介 - 鲁道夫·斯坦纳档案](https://rsarchive.org/Steiner/Introduction.html)或[鲁道夫·斯坦纳_百度百科](https://baike.baidu.com/item/鲁道夫·斯坦纳/4643181)）的《更高世界的知识及其获得（*Knowledge of the Higher Worlds and Its Attainment*）》中的第九章（Chapter 9）。

国内似乎暂无本书相关译本。

本书相关链接：[Knowledge of the Higher Worlds and Its Attainment| Internet Sacred Text Archive](https://sacred-texts.com/eso/khw/khw13.htm)

[更高世界的知识及其获得（1947）—鲁道夫·斯坦纳档案馆](https://rsarchive.org/Books/GA010/English/RSPC1947/GA010_c09.html)

##### 图书馆里的书

The Art of War... The Conquest of Gaul... The Treasure That Combines All Arts...《孙子兵法》……《高卢战记》……《汇通诸艺之宝》……

The Art of War，《孙子兵法》：很有名，不用说。

The Conquest of Gaul，《高卢战记》：也很有名。

豆瓣阅读：[高卢战记 (豆瓣)](https://book.douban.com/subject/1511912/)

微信读书：[高卢战记-微信读书](https://weread.qq.com/web/reader/65e329a0717d45e965eef21)

The Treasure That Combines All Arts，《汇通诸艺之宝》：

应该是Kitāb al-makhzūn jāmiʻ al-funūn，一部关于军事艺术的论述，涵盖了训练、骑兵、步兵、射箭和弩等主题。可翻译为《军事艺术论》，但原标题很美，所以保留原标题意境也不错。

国内似乎暂时没有这本书。

相关链接：[Treatise on Military Art. | Library of Congress](https://www.loc.gov/item/2021667392/)

