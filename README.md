## 超级应用安全相关研究论文与工具汇总

### 基本工具
- 小程序解包工具：https://github.com/NanZhao1512/-wxappUnpacker-?tab=readme-ov-file
- 小程序爬虫工具**MiniCrawler**: https://github.com/OSUSecLab/MiniCrawler
- ICSE'22软件所-小程序缺陷检测工具**WeBug**: https://github.com/tao2years/WeBug
  
### 恶意小程序检测

#### 权限提升恶意小程序检测

- CCS'20小程序提权行为检测工具**Apiant**: https://sites.google.com/view/appinapp/ 【调通了前面的测试用例生成部分，后面的动态分析部分未调通】
- ASE'24西交-小程序中滥用数据权限请求检测工具**MiniChecker**: https://github.com/xjtu-intsoft/MiniChecker 【可以用[coddfuse-query](https://github.com/codefuse-ai/CodeFuse-Query/tree/main)生成函数调用图,使用gdl查询执行错误】
- 电子科技大学团队针对小程序中提权漏洞整理（真实CVE）：https://github.com/BESTICSP/Vulnerabilities-Related-to-Mini-Programs-Permissions ，(对应CCS saTs'23论文 Systematic Analysis of Security and Vulnerabilities in Miniapps)

#### 隐私泄露恶意小程序检测
- ICSE'21-小程序污点分析检测**TaintMini**：https://github.com/OSUSecLab/TaintMini 【已复现成功，主机虚拟机中（该工具只能在Linux系统下使用）】
- TIFS'24复旦-小程序违规开发行为检测工具**MiniAppSecurity**：https://github.com/seclab-fudan/MiniAppSecurity 【使用WALA静态分析框架，暂未调通】
- 复旦-小程序隐私过度收集行为检测**SPOChecker**：https://github.com/ppflower/XPOScope 【需要xposed模块进行动态分析】
- TDSC'23复旦-小程序中隐私泄露检测**MiniTracker**：https://github.com/flyboss/MiniTracker 【已复现成功，主机代码盘中（Windows系统中可用）】

### 其他安全工具（待分类）
- NDSS'25-小程序中证书泄密大规模分析研究：https://github.com/KeyMagnetProject2025/KeyMagnet【动态分析部分缺少相关文件无法运行】
- ICSE'23-超级应用中不一致API检测工具**APIDiff**：https://github.com/OSUSecLab/APIDiff
- CCS'24-跨站请求伪造分析工具**MiniCAT**: https://github.com/kee1ongz/MiniCAT
- CCS'20-跨小程序伪造工具**CMRFScanner**：https://github.com/OSUSecLab/CMRFScanner 【已复现成功，主机虚拟机中（只能Linux系统使用）】

### 其他平台恶意软件检测工具

- ExtAnalysis 浏览器插件安全检测工具： https://github.com/Tuhinshubhra/ExtAnalysis
- 使用机器学习进行恶意软件分类：https://github.com/trucanh21/android-malware-detection-using-machine-learning
- AndroPyTool从apk文件中提取静态和动态特征: https://github.com/alexMyG/AndroPyTool
