# adb-uninstalls-Huawei-phone-pre-installed-apps

通过手机连接电脑的方式卸载华为预装应用

## 中国政府相关规定

* [**《移动智能终端应用软件(APP)预置和分发管理暂行规定》**](https://www.miit.gov.cn/jgsj/xgj/wjfb/art/2020/art_212af2d042a240ae968100f485776b24.html)

  第七条明确规定：生产企业和互联网信息服务提供者应确保除基本功能软件外的移动智能终端应用软件可卸载。

## adb操作步骤

### 电脑端操作准备

1. 在[adb shell官网](https://adbshell.com/upload/adb.zip)下载调试工具包（ADB Kits）并解压
2. 打开win10的命令提示符执行以下操作
   1. 通过cd命令进入刚才解压好的文件夹[^示例] 
   2. 输入`adb devices`命令

### 手机端操作准备

1. 在手机设置中打开”开发者模式“[`如何打开？`](https://developer.huawei.com/consumer/cn/doc/quickapp-open-developer-option)
2. 在“开发人员选项”中，激活以下选项
   - “USB调试”
   - “连接USB时总是弹出提示”
   - “仅充电模式下允许USB调试”

### 数据线链接电脑与手机，准备卸载

1. 根据手机提示依次点击“仅充电”—“始终允许”[^如果没有弹出USB调试授权窗口]

2. 再次在命令提示符中执行`adb devices`命令

   如果出现你的手机信息，表示连接成功

### 卸载

#### 卸载通用命令

`adb shell pm uninstall --user 0` + 软件包名

#### 禁用通用命令

`adb shell pm disable-user` + 软件包名

## 华为应用预装包名表（更新于2020.1.20）

|       应用名称       |            应用包名             |
| :------------------: | :-----------------------------: |
|     华为旅行助手     |      com.huawei.scenepack       |
|       华为音乐       |     com.android.mediacenter     |
|       华为主题       | com.huawei.android.thememanager |
|     华为应用市场     |      com.huawei.appmarket       |
|       学生模式       |    com.huawei.parentcontrol     |
|       华为钱包       |        com.huawei.wallet        |
|     华为会员服务     |     com.huawei.phoneservice     |
|   旅行助手服务管理   |   com.huawei.hwpolicyservice    |
|      华为输入法      |     com.baidu.input_huawei      |
|       语音助手       |      com.huawei.vassistant      |
|       华为助手       |       com.huawei.hisuite        |
|     华为系统更新     |    com.huawei.android.hwouc     |
| 华为钱包支付防护中心 |    com.huawei.android.hwpay     |
|      天际通服务      |       com.huawei.skytone        |
|    华为自带浏览器    |       com.android.browser       |
|       推送服务       |  com.huawei.android.pushagent   |
|   主页下拉搜索功能   |       com. huawei.search        |

[更多](https://club.huawei.com/thread-20677864-1-1.html)

[^示例]: C:\Users\zzq20>cd /d D:\Computer plug-in\adb
[^如果没有弹出USB调试授权窗口]:这时候再检查“开发人员选项”中是否已经开启上述三个选项，华为这里很毒瘤，有时候会关闭