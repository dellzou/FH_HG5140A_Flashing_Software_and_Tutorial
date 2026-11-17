# 烽火 HG5140A（10G-EPON 天翼网关）工具与操作存档

配套文章：[烽火 HG5140A 光猫：开 Telnet、取超密与改地区](https://xiaozou123.cn/fh-hg5140a-telnet-super-password/)

HG5140A 是电信的 10G-EPON 定制网关。开 Telnet 的地址要带 `8080` 端口，key 有两种写法；超密要用 `su` 提权后进工厂模式读。仓库里是一套改区工具（含运行库）、烽火通用工具和四张操作截图。

## 目录

- `tools/一键改区工具/`：改区工具 Ver24.1.3 与 `App/` 运行库，**必须整体解压，exe 和 App 在同一层**
- `tools/tftpd64.exe`：TFTP 服务端
- `tools/一键获取烽火光猫超密.exe`：界面化读超密
- `tools/烽火光猫密码解算工具.exe`：解加密配置
- `docs/`：四张操作截图，带红圈标注

## 工具的使用边界

截图里的「特别声明」写得很清楚：按福建电信 2023 年 4 月出厂的 HG5140A 实机开发，只在那一台验证过；工具有使用次数限制，仅限恩山论坛发布，到期联系作者授权。**换到别的固件版本上，命令可能对不上，且不一定报错。**

## 文件与 SHA256

| 文件 | 字节 |
|---|---|
| `tools/tftpd64.exe` | 146,656 |
| `tools/一键获取烽火光猫超密.exe` | 50,176 |
| `tools/烽火光猫密码解算工具.exe` | 262,144 |
| `tools/说明.txt` | 338 |
| `tools/一键改区工具/新版电信HG5140A 一键改区工具.exe` | 3,112,960 |
| `tools/一键改区工具/App/ClientConfigUI65U.dll` | 888,320 |
| `tools/一键改区工具/App/CommonUI65U.dll` | 260,608 |
| `tools/一键改区工具/App/ConnectDialog65U.dll` | 435,200 |
| `tools/一键改区工具/App/MFC90ENU.dll` | 54,272 |
| `tools/一键改区工具/App/Ont.dll` | 3,392,000 |
| `tools/一键改区工具/App/Telnet.dll` | 206,336 |
| `tools/一键改区工具/App/mfc90u.dll` | 3,780,424 |
| `tools/一键改区工具/App/msvcp80.dll` | 548,864 |
| `tools/一键改区工具/App/msvcp90.dll` | 569,664 |
| `tools/一键改区工具/App/msvcr80.dll` | 626,688 |
| `tools/一键改区工具/App/msvcr90.dll` | 653,120 |
| `tools/一键改区工具/App/Microsoft.VC80.CRT.manifest` | 1,869 |
| `tools/一键改区工具/App/Microsoft.VC90.CRT.manifest` | 1,860 |
| `tools/一键改区工具/App/Microsoft.VC90.MFC.manifest` | 2,357 |
| `tools/一键改区工具/App/Microsoft.VC90.MFCLOC.manifest` | 5,377 |
| `tools/一键改区工具/App/Config/ButtonBar.ini` | 135 |
| `tools/一键改区工具/App/Config/Color Schemes.ini` | 1,885 |
| `tools/一键改区工具/App/Config/Global.ini` | 9,910 |
| `tools/一键改区工具/App/Config/SCRTMenuToolbar.ini` | 5,588 |
| `tools/一键改区工具/App/Config/Sessions/Default.ini` | 8,806 |
| `docs/使用说明 第一步.png` | 67,358 |
| `docs/使用说明 第二步.png` | 75,952 |
| `docs/支持型号.png` | 127,844 |
| `docs/改区后方案变更.png` | 49,900 |
| `docs/工具主界面.png` | 33,558 |

```
988292db5e71fa50b090ce2bfe66813791d944cde64c19b7f0ecda8892392a15  tools/tftpd64.exe
787848aa26c91eaa1c689fc8e9ffe8dc11af64e51c87d1d5797d0df2e75c9286  tools/一键获取烽火光猫超密.exe
30a9cdeaa43e329e137555499f5e498ad275eef3391b6eea3bf08f25aa4531ba  tools/烽火光猫密码解算工具.exe
8f68ec75437a6eb688c0578c3c8659dd354f1b774e625dbefd62a1db32b69f51  tools/说明.txt
0b97f7929614591dc9626110a8c5132c16179a4f60786a0e94650a2a9dd3e4f1  tools/一键改区工具/新版电信HG5140A 一键改区工具.exe
eb9f413eec1c77ae168d320ad58591fa249af6fd0778a90193cd6e3c01a7c692  tools/一键改区工具/App/ClientConfigUI65U.dll
fe4d63d26005e0a24b90a3939b9606aecd5e17971bbcf7e7100e316f731ab8bb  tools/一键改区工具/App/CommonUI65U.dll
bf639208e62fc7bf683f11cebdeea7e123b60e2f8ef2f8f5e1d4846b988a4cc7  tools/一键改区工具/App/ConnectDialog65U.dll
a3e2c202e556791dee9d18962ca6780761b415313bcd104c2e621ba4089801a4  tools/一键改区工具/App/MFC90ENU.dll
fa1c769afddf0411090338cbfb682bb237f4af3706eff54a943e4654fc2e57ed  tools/一键改区工具/App/Ont.dll
8d3a082d5cfa57f01cbd143e7bfff97d47ae5d99714ac450895afd8a2214772e  tools/一键改区工具/App/Telnet.dll
314ef0e1c636ac553c0e09f992b34573da4a89accb759bda27335e8125c08e35  tools/一键改区工具/App/mfc90u.dll
2026f3c4f830dff6883b88e2647272a52a132f25eb42c0d423e36b3f65a94d08  tools/一键改区工具/App/msvcp80.dll
4608beedd8cf9c3fc5ab03716b4ab6f01c7b7d65a7c072af04f514ffb0e02d01  tools/一键改区工具/App/msvcp90.dll
02bdde38e4c6bd795a092d496b8d6060cdbe71e22ef4d7a204e3050c1be44fa9  tools/一键改区工具/App/msvcr80.dll
e16bc9b66642151de612ee045c2810ca6146975015bd9679a354567f56da2099  tools/一键改区工具/App/msvcr90.dll
17ad1a64ba1c382abf89341b40950f9b31f95015c6b0d3e25925bfebc1b53eb5  tools/一键改区工具/App/Microsoft.VC80.CRT.manifest
03d0776812368478ce60e8160ec3c6938782db1832f5cb53b7842e5840f9dbc5  tools/一键改区工具/App/Microsoft.VC90.CRT.manifest
1fed2074ab9f90d9fccc5a49b6aa42c917674c2b5c7b1bb93fb67b0e0c944818  tools/一键改区工具/App/Microsoft.VC90.MFC.manifest
81e13dc44e21fca2b095e82c34294c199d37428f32de36d5ffa6cd3b54f88d7b  tools/一键改区工具/App/Microsoft.VC90.MFCLOC.manifest
496cb3c8a6677a93d9821f0346fb2adb9152ef959f23d224607833ed63a304ba  tools/一键改区工具/App/Config/ButtonBar.ini
3f77b3c7fe57a9d645fe6f5fe92b134404318bb2466452bd6f22c24d82862696  tools/一键改区工具/App/Config/Color Schemes.ini
d6b586c3c71b1059d03bd2284a7eb1bb4ef072514629877c860b21ab8c1f9b90  tools/一键改区工具/App/Config/Global.ini
dc0ae456286dd151102652ef3166ede5d1c1e81bec6dbdd9b7b2f893d5567303  tools/一键改区工具/App/Config/SCRTMenuToolbar.ini
94ca771b694153fe44d05eec42cb202f70d967264cb60bc8f1219fb60664a0de  tools/一键改区工具/App/Config/Sessions/Default.ini
6e75db5c253a66d0a035f2ecb98dd8c2f731f7d1efeaaed0e406c56dca9f3776  docs/使用说明 第一步.png
2bb6f6274d75354015c1ae823383b368ebbb32f5cdcc1f4c095e05fbbde1ce69  docs/使用说明 第二步.png
11af6db1415da3bb3b4fcfb46128b739c516abeb773842e73431fb5c859b0b27  docs/支持型号.png
294bd65d6359f4e540c250a91ccc650102365c3dccf1f03f909f7b897e0f1137  docs/改区后方案变更.png
1fd30e418d099bafc898078769b1de0c43242dca551832f79f738fb7b09d08cc  docs/工具主界面.png
```

## 使用顺序

1. 浏览器打开 `http://192.168.1.1:8080/cgi-bin/telnetenable.cgi?telnetenable=1&key=<MAC>`，端口不能省。
2. Telnet 登录（`telnetadmin` 或 `telecom`），`su` 提权到 `#`。
3. `load_cli factory` → `show admin_name` / `show admin_pwd`。
4. 改地区：用 `tools/一键改区工具`，按界面五步走，执行后网关自动重启。
5. 改完 Telnet 账号会变成 `telnetadmin`，密码走内置方案。

## 免责声明

工具与截图均来自公开维修资料，仅供自有设备维修与学习使用。改地区、改设备标识有断网和变砖风险，恢复出厂会清空业务配置。仓库不含任何真实设备的配置备份。
