# 青年大学习/团课自动打卡

![](https://github.com/838239178/tk-auto-study/workflows/auto-study/badge.svg) ![](https://img.shields.io/github/stars/838239178/tk-auto-study) ![](https://img.shields.io/github/forks/838239178/tk-auto-study) ![](https://img.shields.io/badge/Python-3.7+-green.svg) ![](https://img.shields.io/badge/License-Apache2.0-green.svg)

> 2021.04.24：添加失败重试功能，使用针对性更强的OCR识别接口  
> 
> 2021.07.09：官方服务器服务采用了https协议 导致发生bug 已修复
> 
> 2021.09.28：修复登录异常问题 更换了 **密钥(pubKey)** 和加密方法 请务必fork此最新版本并更换配置文件的public或github_secret的pub_key！
>
> 2021.10.01: 为Pull Request创造workflow检查因此注释了run.yml中的定时执行条件 新fork用户需自行取消注释

🤺妈妈再也不用担心我团课没看被团支书赶着催了

### 点个:star:再走吧,❤感谢大家的Star和Fork,有问题可以发issue

**仅供福建共青团团员学习交流使用** 

**浙江团员可以点击这里[青春浙江](https://gist.github.com/838239178/ddad90e8c5e52f5fa8f0febea6109f24)**

*如果你有新的或更好OCR识别方式 请参考 [OCR贡献文档](./doc/OCR_Module_Rule.md) 做出你的贡献！*

## 使用方法

#### 🍎pub_key:

```
A7E74D2B6282AEB1C5EA3C28D25660A7
```

#### 0. 申请Ocr识别接口的权限

[详细教程请点击这里](https://blog.pressed.top/2021/02/14/signUpBaiduOcr/)

*请选择使用一种可以识别文字的api，建议使用BaiduAI的Ocr接口，否则需要自行修改代码*

- 首先要有一个百度账号，进入[这个网址](https://ai.baidu.com/)，点击控制台并登录
- 完成个人实名认证，申请文字识别的使用权
- 点击管理应用，点击创建应用，按要求填一些信息，创建完成后记住**API KEY**和**SECRET KEY**

#### 1. 部署在平台上定时执行

可以是服务器，本地，和GitHubActions，这里只介绍如何在GitHubActions中运行，其他运行方式请参考main.py中的注释

- fork该项目到你的库中

- 添加五个secrets，分别为：username,  pwd,  pub_key,  ocr_api_key,  ocr_secret_key

- **将.github/workflows/run.yml中的注释部分(`#`号)取消**并cron为你想要触发的时间，默认是每周三14点运行一次，cron如何写请自行百度
- 进入Action中手动触发一次，测试是否成功

## 可选识别类型

GithubAction（可选）添加新的secrets OCR_TYPE 来指定识别类型

其他方式在config.json中修改指定配置项即可

- baidu_image [默认方法,需要到百度AI中申请](https://blog.pressed.top/2021/02/14/signUpBaiduOcr/)

