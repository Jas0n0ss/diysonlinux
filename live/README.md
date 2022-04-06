#### 斗鱼直播源
> 准备工作

- Apple TV +IPlay TV(或者其他任何支持导入m3u直播源的app)
- 参考项目：https://github.com/wbt5/real-url

> 演示

```python
[root@wangyuan scripts]# python3 douyu.py 
输入斗鱼直播间号：
2758565
{'flv': 'http://dyscdnali1.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=', 'x-p2p': 'http://tx2play1.douyucdn.cn/live/2758565rghjMAcIL.xs?uuid='}
```
⚠️注意事项：
脚本输出的`x-p2p`播放会有问题，需要将对应的主机名修改为以下任何一个（自己测试那个效果最好）：
```
# 两个阿里的CDN：
    dyscdnali1.douyucdn.cn
    dyscdnali3.douyucdn.cn
# 墙外不用带尾巴的akm cdn：
    hls3-akm.douyucdn.cn
    hlsa-akm.douyucdn.cn
    hls1a-akm.douyucdn.cn
```
> 生成m3u文件

- 将输出的两个链接中的主机名作修改之后，转换成可以识别的格式：
```
[root@wangyuan scripts]#  head -n5 ../m3u/douyu.m3u 
#EXTM3U

#EXTINF:-1,牛叔说电影---斗鱼
http://hls1a-akm.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=
```
> 添加直播源

Apple TV 上可以通过IPlay TV 或者Obox这样的app，在线添加或者本地添加即可

> 汇总

以下是个人偶尔看的一些节目，仅供参考：
```
[root@wangyuan scripts]# cat ../m3u/douyu.m3u 
#EXTM3U

#EXTINF:-1,牛叔说电影---斗鱼
http://hls1a-akm.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=

#EXTINF:-1,放逐大帝灬---斗鱼

http://hlsa-akm.douyucdn.cn/live/5377721rsUFS6nGI.flv?uuid=

#EXTINF:-1,神秘嘉宾橙子---斗鱼
http://dyscdnali1.douyucdn.cn/live/3652542rDfEFTgw2.flv?uuid=

#EXTINF:-1,科幻漫威---斗鱼

http://hlsa-akm.douyucdn.cn/live/252802r4adW4jo5L.flv?uuid=

#EXTINF:-1,科幻灾难---斗鱼

http://hlsa-akm.douyucdn.cn/live/248753r9wHEgtgT1.flv?uuid=

#EXTINF:-1,英雄联盟赛事---斗鱼

http://hlsa-akm.douyucdn.cn/live/288016rlols5.flv?uuid=

#EXTINF:-1,斗鱼酱油瓶---斗鱼
http://hlsa-akm.douyucdn.cn/live/6717704r2j1dUqpo.xs?uuid=

#EXTINF:-1,小片片说大片---斗鱼
http://hlsa-akm.douyucdn.cn/live/4258555r3isvDdlq.xs?uuid=

#EXTINF:-1,PDD---斗鱼
http://hlsa-akm.douyucdn.cn/live/24422rJZDUzZKbCt.xs?uuid=

#EXTINF:-1,邦Sa---斗鱼
http://hlsa-akm.douyucdn.cn/live/5720533rttUaMPs1.xs?uuid=

#EXTINF:-1,文森特---虎牙
http://v-replay.cdn.huya.com/record/huyalive/1608993854-1608993854-6910575982394998784-3218111164-10057-A-0-1-imgplus/2022-04-04-19:02:45_2022-04-05-00:16:35.m3u8?bitrate=0&client=81&definition=yuanhua&pid=1608993854&scene=vodreplay&vid=690292159
```
