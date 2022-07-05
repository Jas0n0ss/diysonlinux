#### 斗鱼直播源
> 准备工作

- Apple TV +IPlay TV(或者其他任何支持导入m3u直播源的app)
- 参考项目：https://github.com/wbt5/real-url

> 演示以及环境准备

获取对应的直播源获取脚本：https://github.com/wbt5/real-url

```bash
[root@wangyuan scripts]# yum install nodejs -y && yum install python-pip python3-pip
[root@wangyuan scripts]# pip install pyexecjs && pip3 install pyexecjs
[root@wangyuan scripts]# python3 douyu.py 
输入斗鱼直播间号：
2758565
{'flv': 'http://dyscdnali1.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=', 'x-p2p': 'http://tx2play1.douyucdn.cn/live/2758565rghjMAcIL.xs?uuid='}
```
⚠️注意事项：
脚本输出的播放地址可能会有问题，需要将对应的主机名修改为以下cdn的任何一个（自己测试那个效果最好）：
```bash
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
```bash
[root@wangyuan scripts]#  head -n5 ../m3u/douyu.m3u 
#EXTM3U

#EXTINF:-1,牛叔说电影---斗鱼
http://hls1a-akm.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=
```
> 添加直播源

Apple TV 上可以通过IPlay TV 或者Obox这样的app，在线添加或者本地添加即可

> 汇总

以下是个人偶尔看的一些节目，仅供参考：
```yaml
2758565:牛叔说电影:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/2758565rghjMAcIL.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/2758565rghjMAcIL.xs?uuid='}
3652542:神秘嘉宾橙子:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/3652542rDfEFTgw2.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/3652542rDfEFTgw2.xs?uuid='}
7940025:chogod虫王:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/7940025rdJVbh461.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/7940025rdJVbh461.xs?uuid='}
288016:英雄联盟赛事:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/288016rlols5.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/288016rlols5.xs?uuid='}
252802:科幻灾难:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/252802r4adW4jo5L.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/252802r4adW4jo5L.xs?uuid='}
248753:动作灾难:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/248753r9wHEgtgT1.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/248753r9wHEgtgT1.xs?uuid='}
537772:放逐大帝:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/5377721rsUFS6nGI.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/5377721rsUFS6nGI.xs?uuid='}
6717704:酱油瓶:
{'flv': 'http://dyscdnali3.douyucdn.cn/live/6717704r2j1dUqpo.flv?uuid=', 'x-p2p': 'http://hlsa-akm.douyucdn.cn/live/6717704r2j1dUqpo.xs?uuid='}
```
