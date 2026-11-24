# 聚合接口生成报告

生成时间：2026-11-24 22:11:04（北京时间）

## 直播接口 hub/live.m3u

- 央视卫视：23 个频道
- 卫视频道：210 个频道
- 港澳台：81 个频道
- 金鹰动画：29 个频道
- 候选源总数：2322
- 探测确认存活：245
- 探测失败原因分布：
  - URLError：446
  - ct：281
  - http-403：73
  - http-404：40
  - http-500：26
  - TimeoutError：21
  - m3u8-body：14
  - http-502：10
  - http-429：6
  - unknown-ct：4
  - http-523：4
  - http-304：3
  - html-page：2
  - http-302：1
  - RemoteDisconnected：1
  - http-418：1
  - http-504：1
  - http-409：1

## 点播接口 hub/tvbox.json

- 点播站点 sites：140
- 直播源 lives：7
- 解析器 parses：41

## 配置源探测结果

- OK  http://xhztv.top/xhz  sites+54 lives+1 parses+6
- OK  https://dxawi.github.io/0/0.json  sites+41 lives+4 parses+0
- OK  https://www.yingm.cc/dm/dm.json  sites+23 lives+0 parses+20
- OK  http://home.jundie.top:81/top98.json  sites+22 lives+2 parses+15

## 说明

- 双源池：iptv-org 官方元数据（权威分类）+ 中文公开直播清单（国内可播源、中文台名）。
- 分组共 4 个：央视 / 卫视 / 港台 / 金鹰动画。
- 金鹰动画组含湖南金鹰卡通卫视及国内其它动画/少儿台。
- 存活探测只剔除明确 HTTP 错误码（404/410/451）；网络层失败保留，因其通常与探测节点位置相关。
- 本项目仅作个人学习研究：只聚合公开播放列表与公开配置中声明的站点地址，不存储、不解析、不转播影视内容。
