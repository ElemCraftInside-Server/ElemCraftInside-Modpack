# 自动更新部署流程

由于HMCL是通过比对本地与云端`server-manifest.json`文件中的内容来进行更新；直接在仓库中更改文件会导致`server-manifest.json`的记录值与实际文件不符，导致报错；所以每次升级版本都需要重新导出整合包后解压至仓库目录。

### 具体操作如下：

先在HMCL中安装要修改的整合包，然后在安装好的游戏文件夹里面进行修改，修改好后导出整合包，然后删除本地仓库中除`LICENSE`和`README.md`之外的所有文件，将整合包文件解压至仓库目录，然后进行git push操作。

### 更新规范

- 文件名：以ElemCraftInside-Modpack开头，后接版本号，文件名与版本号中间用`_`连接
	- 版本号规范：以Ver开头，后接数字版本号，数字版本号只有一个小数点，如果为测试版，需加上beta标，数字版本号与beta标之间用`-`连接

		> 例：ElemCraftInside-Modpack_Ver1.1-beta
	- **此文件名规范同时适用于整合包文件名与Github Release Title**

- HMCL整合包参数填写：
	- 作者：ECIS  Core Management
	- 版本：仅填写数字版本号与beta标（若有）
	- 整合包下载链接前缀：https://gitee.com/numerousx/ElemCraftInside-Modpack/raw/main
	- 整合包包含的文件：**不要**勾选`XaeroWaypoints`,`XaeroWorldMap`,`saves`,`natives-windows-x86_64`,`schematics`文件；**需要**勾选`servers.dat`,`options.txt`,`.qmenu_opened.marker`，剩余请保持默认。

- Github发行规范

	> 由于Gitee的发行版文件大小限制为100M一下，故不在Gitee发行

	- Tag写法：将“版本号规范”中的Ver简写为v，剩余保持一致即可

		> 例：v1.1-beta
	- ChangeLog：
		- 内容：请按[在线表格](https://www.kdocs.cn/l/cfGvthYbQxLB)中ChangeLog一栏填写
		- 格式：使用Markdown语法
			ChangeLog示例
		- 
			### Change Log:
			- voicechat配置
			- new age配置
			- 将默认字体改为梦源黑体
			- BetterCompatbilityChecker配置
			- 自动更新支持
			- 默认开启自动跳跃
			- 添加默认服务器
			- 更改MOTD
			- 添加模组CustomWindowTitle



