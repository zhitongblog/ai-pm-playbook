# FreeID Photo：三天，15 个 build，进 App Store

[English](freeid-photo.md) · [简体中文](freeid-photo.zh.md) · [全部案例](README.zh.md)

> App Store：[id6779873542](https://apps.apple.com/app/id6779873542) · 仓库：[github.com/zhitongblog/freeid-photo](https://github.com/zhitongblog/freeid-photo)（公开）
> 下面的数字均以 doaipm 手册所载为准，截至 2026 年 8 月。

## 它是什么

一个拍证件照、按官方规格裁切的 iOS 应用，用 Swift 和苹果的 Vision 框架做。四个案例里体量最小：**21 个提交，其中 14 个是编号 build**，一个原生 iOS App 上架。想知道从零到上架最少要经历什么，看这一个就够。

## 时间线

- **2026-06-13：** 建仓。第一个提交是「FreeID Photo: core, Vision engine, export, CLI, MCP, iOS app」
- **2026-06-13 至 06-15：** build 2 到 build 15，三天
- **2026-06-15：** 可复用的 App Store 上架自动化（`scripts/asc`）
- **2026-06-30：** 解决拒审，上架

## 几个关键决定

**CLI 和 MCP 出现在第一个提交里。** 不是 App 做完之后补的。因为一开始就有，后来「换白底、不裁切」「导出任意毫米尺寸」这类需求直接加进了 `freeidctl` 命令行，不用动 App 界面，脚本和 AI 也能直接调用。

**规格对照官方来源核实。** 第二个提交不是代码，是「对照官方来源核实规格尺寸，扩展到 16 种规格、10 个国家」。证件照差一毫米就废了。AI 能查资料，但「这个必须对照官方来源核实」是人做的决定。

**两次减法，都很早。** build 3 去掉了表情检测：检测不准，用户被卡着拍不了照，一个不可靠的校验比没有校验更糟。build 11 把 build 8 刚加的背景色选择收窄到合规场景，因为证件照的底色有规定。两次减法都发生在功能刚做出来之后，只有每个 build 单独验过才可能这么快。

## 出过的问题

- **方向修了两次。** build 6 让全链路尊重 EXIF 方向，修竖拍导出变横；build 7 又用 RotationCoordinator 修了一次。这个问题横跨采集、元数据、导出三层，第一次没修干净，小步让这一点露了出来
- **护照照片裁到头顶、没有留白。** build 14、15 连着修。只有把成品照片跟真实要求比对才看得出来，AI 只知道裁切参数执行了
- **2026-06-30 被拒，两条同时中招。** 条款 2.3.7：副标题、关键词、宣传文案、描述里都有「免费」，第一张截图的大标题是 "Truly free"。条款 2.1：应用用了人脸检测，于是隐私页加了「人脸数据」小节（在设备上处理、不存储、不共享、不留存），回答写进审核备注。这次只改元数据，同一个 build 15 重新提交

## 留下了什么

上架脚本的说明里写着 "built during the v1.0 submission and reusable for every future update"。SoloPDF 后来那套 `scripts/asc/` 就是从这里搬过去的。最后一个 build 到过审之间那半个月，只要最后变成了一条能重跑的命令，就只付一次。

---

逐个 build 的完整表格和拒审细节在[手册](https://doaipm.com/zh/presale/)里。相关：[上线自查清单](../../templates/launch-checklist.zh.md)、[上架前审元数据提示词](../../prompts/app-store-review.zh.md)。
