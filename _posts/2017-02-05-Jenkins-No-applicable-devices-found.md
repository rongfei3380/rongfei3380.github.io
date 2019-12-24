---
layout:     post
title:      "Jenkins -- No applicable devices found"
subtitle:   "CFPropertyList 导致打包失败问题"
date:       2017-02-05 15:20:00
author:     "chengfeir"
header-img: "img/post-bg-alitrip.jpg"
catalog: true
tags:
- Jenkins
- iOS
---
Jenkins 打包遇到问题log如下：

    2017-02-03 16:33:50.722 xcodebuild[20625:7527545] [MT] IDEDistribution: Step failed: <IDEDistributionThinningStep: 0x7f7fa8ab6c00>: Error Domain=IDEDistributionErrorDomain Code=14 "No applicable devices found." UserInfo={NSLocalizedDescription=No applicable devices found.}
    error: exportArchive: No applicable devices found.
    Error Domain=IDEDistributionErrorDomain Code=14 "No applicable devices found." UserInfo={NSLocalizedDescription=No applicable devices found.}

http://stackoverflow.com/questions/33041109/xcodebuild-no-applicable-devices-found-when-exporting-archive 给出了问题，是说rvm的冲突问题，但是使用的 system ruby之后，仍然是同样的错误导致打包失败。

再次google之后发现实际上是 CFPropertyList的问题，gem update一下就OK了。
参考 https://github.com/fastlane-old/gym/issues/104
或者单独处理 CFPropertyList

    $ gem install CFPropertyList
    $ gem install sqlite3

可以解决问题
