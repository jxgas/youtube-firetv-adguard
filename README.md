# YouTube Fire TV AdGuard

专门针对 Amazon Fire TV / Fire TV Stick / Fire TV Cube 上 YouTube App 的 AdGuard/DNS 过滤规则。

## 项目地址

https://github.com/jxgas/youtube-firetv-adguard

## 订阅地址

Raw：

https://raw.githubusercontent.com/jxgas/youtube-firetv-adguard/main/youtube-firetv.txt

在 AdGuard Home 中可以将上面的 Raw 地址作为自定义过滤器添加。

## 支持设备

* Amazon Fire TV
* Fire TV Stick
* Fire TV Cube
* Amazon Fire TV 上的 YouTube App

## 过滤目标

本项目主要针对：

* YouTube 广告相关域名
* Google 广告服务
* DoubleClick
* 广告追踪
* 广告统计
* Amazon 广告服务
* 常见第三方广告网络

## 重要说明

这是一个 DNS/域名级过滤器。

YouTube 的广告系统与正常视频服务高度关联，因此 DNS 过滤无法保证官方 YouTube App 中的所有视频广告都能被拦截。

本项目采用“尽量拦截广告、尽量避免 YouTube 视频无法播放”的策略。

因此不会直接封锁：

* youtube.com
* googlevideo.com
* ytimg.com
* youtubei.googleapis.com

尤其不要将：

```text
||googlevideo.com^
```

加入黑名单。

否则可能导致正常 YouTube 视频无法播放。

## 使用方法

### AdGuard Home

进入：

```text
Filters
→ DNS blocklists
→ Add blocklist
→ Add a custom list
```

添加：

```text
https://raw.githubusercontent.com/jxgas/youtube-firetv-adguard/main/youtube-firetv.txt
```

保存后更新过滤器。

### AdGuard

如果使用支持自定义过滤器订阅的 AdGuard 产品，可以直接添加：

```text
https://raw.githubusercontent.com/jxgas/youtube-firetv-adguard/main/youtube-firetv.txt
```

## 测试方法

建议先在 Fire TV 上播放 YouTube。

如果：

1. YouTube 正常打开
2. 视频正常播放
3. 广告减少
4. 没有出现无限加载

说明规则工作正常。

如果视频无法播放，首先删除最近增加的规则，而不是直接封锁 YouTube 视频 CDN。

## 规则维护

本项目不会简单复制 EasyList。

规则优先根据：

1. Amazon Fire TV 实际 DNS 查询
2. YouTube App 实际请求
3. 广告出现时的 DNS 请求
4. 误杀测试
5. 用户反馈

逐步增加。

## 免责声明

本项目仅用于广告过滤、隐私保护和网络管理研究。

由于 YouTube 服务端广告机制会持续变化，规则不能保证永久有效。
