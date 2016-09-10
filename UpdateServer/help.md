使用说明
=======

- - -

**通用功能**
- - -

* 冻结应用

	* 可以将用不到的应用冻结起来，被冻结的应用无法在桌面上看到，也不会被任何手段启动。

* 组件管理

	* 就如我们所熟知的，Android 系统拥有四大组件，当一个应用拥有很多组件，并且都在后台运行时，就会造成大量的耗电或者让系统变卡等情况。针对每一个应用，禁用不需要的组件，可以省电并保持系统流畅。
	* 什么样的组件是可以禁用的？这个问题仁者见仁，需要大家自己去摸索。应用内提供了下载组件配置的功能，可以下载他人的配置方案，如果你对自己的配置方案很有信心，也可以将你的方案提交到服务器，从而方便其他的用户。这个功能的完善是需要群策群力的。

* 清理系统

	* 清理 data 分区内的数据，主要会清理掉应用内的 cache，ANR 日志，以及 ART 内因卸载应用而残留的二进制文件。

* 核心校验破解

	* 破解 Android 的签名校验，使不同签名的应用可以覆盖安装，允许降级覆盖等。

* 模拟设备

	* 通过修改 build.prop 将手机模拟成其他设备，对于需要校验设备的游戏或是应用，使用此功能可以帮助绕开校验。

* 终端模拟器

	* 给你一个终端，你就可以为所欲为，当然前提是你会玩

- - -
**MIUI 专属功能**
- - -

* 主题破解

	* 嘘~~

* 移除广告

	* 目前已可以移除大部分 MIUI 自带的广告了，也能去除音乐视频等广告闪屏页。如果发现不能移除的，请提交 Issue 到 Github。
	* 这个模块会跟随 MIUI 版本的更新而不断更新，目前只跟进 MIUI8。

* 移除通知栏搜索

	* 去掉 MIUI8 通知栏上的搜索框。

* 状态栏图标数

	* 采用主题的方式进行修改，在 SD 卡根目录下生成一个主题文件，将该文件导入系统的主题中，并混搭通知栏即可。
	* 修改后的通知栏，单页模式拥有 5 个图标，双页模式每行 4 个图标。

* 移除 Root 等待

	* 每次等 25 秒太让人捉急了，还是去掉吧。

* 屏蔽更新

	* 对于刷了 Xposed 的 MIUI 来说，每周的更新是一件痛苦的事，因为无法 OTA，只能刷全量。因此建议选择一个稳定的版本，开启 Root 并刷了 Xposed 之后，将更新屏蔽，以免去一直被提示更新的困扰。

- - -
**额外说明**
- - -

* 破解 system 分区

	* 由于 MIUI 锁了 system 分区，使得 mount 命令无法将分区重新挂载为可读写，在这种情况下，会引起程序工作不正常，需要破解 system 分区。
		* Root 设备：无论是刷开发版获取官方 Root，还是自行刷入 SuperUser 均可以，但是系统内必须已有 Root 权限
		* 在终端执行以下命令：

		```
		$ adb root
		$ adb disable-verity
		$ adb reboot
		```

* 关于 Android N

	* 以 CM14 为代表的 Android N 已经可以刷了，但是目前的 N 并不稳定，特别是对于 su 的权限处理还有问题，这会导致应用无法正常的启动一个 su 进程，也就是拿不到 Root 权限了。
	* 对于因 su 权限引起的问题，目前已判为无 Root。
	* 目前还没有针对 Android N 的 Xposed 框架，因此需要 Xposed 的全部功能均不可用。