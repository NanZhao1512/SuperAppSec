## 超级应用安全相关研究论文与工具汇总

### 基本工具
- 微信小程序解包工具：https://github.com/NanZhao1512/-wxappUnpacker-?tab=readme-ov-file
- 微信小程序反编译工具：https://github.com/Cherrison/CrackMinApp

### 爬虫工具
- 微信小程序爬虫工具**MiniCrawler**: https://github.com/OSUSecLab/MiniCrawler

### 测试工具
- ICSE'22软件所-小程序缺陷检测工具**WeBug**: https://github.com/tao2years/WeBug
- 复旦-MiniBot:轻量级小程序动态测试输入生成框架：https://github.com/realvegechick/MiniBot (使用frida,UIAutomotor)

### 微信相关模糊测试器
- **WeChat API Fuzzer**：https://github.com/haseeburrehmanfaheem/WeChat-Api-Fuzzer/tree/main
  - **目标**：该仓库包含用于分析和动态调用微信小程序API的工具，从而评估小程序API调用的安卓框架API，以便在它们之间建立映射关系。
  - **概述**：主要代码位于Evalulate-WeChat文件夹中。利用微信的开发工具通过 Chrome 调试协议动态执行小程序 API。具体而言，该代码对微信调试协议进行逆向工程和定制，以在目标平台上调用 API。
    - Evalulate-WeChat：实现逆向微信调试协议的核心文件，允许通过调试协议中的evaluate函数直接评估JS语言的小程序API
      - evaluateParameters.js：实现通过微信调试协议动态调用小程序 API 的功能。
      - evaluateImproved.js、evaluateNew.js：用于实验的评估脚本变体。
      - invariantApis.csv：通过静态分析微信 APK 提取的 API 列表。
      - undoc.json：包含未记录 API 的 JSON 文件（通过静态分析提取但未在文档中提到的 API）。
    - Eval-Output：存储API响应情况，显示哪些API运行成功，哪些产生错误
      - accessdenied.csv：拒绝访问
      - catch.csv：捕获错误
      - df_other.csv
      - other.csv
    - Fill-Parameters：包含根据 API 的静态分析填充小程序 API 所需参数的脚本。采用基于模板的方法进行填充。
  - **使用方法**
    - 评估参数：Evalulate-WeChat 文件夹中的 evaluateParameters.js 文件是主要的入口点。它将 JavaScript 代码输入到微信调试协议中并记录输出。
    - 填充参数：Fill-Parameters 文件夹中的脚本获取微信 API 及其所需参数（来自 CSV 文件），并使用默认参数进行填充，采用模板化的方法。
    - API评估：在动态调用 API 后，结果存储在 Eval-Output 文件夹中。CSV 文件记录成功调用和执行过程中遇到的错误。
- [**BasicWXAMFuzzer**](https://signal-labs.com/fuzzing-wechats-wxam-parser/)：https://github.com/Signal-Labs/BasicWXAMFuzzer
  对微信wxam解析器的模糊测试
  
### 恶意小程序检测

#### 权限提升恶意小程序检测

- CCS'20小程序提权行为检测工具**Apiant**: https://sites.google.com/view/appinapp/ 【调通了前面的测试用例生成部分，后面的动态分析部分未调通】
- ASE'24西交-小程序中滥用数据权限请求检测工具**MiniChecker**: https://github.com/xjtu-intsoft/MiniChecker 【可以用[coddfuse-query](https://github.com/codefuse-ai/CodeFuse-Query/tree/main)生成函数调用图,使用gdl查询执行错误】
- 电子科技大学团队针对小程序中提权漏洞整理（真实CVE）：https://github.com/BESTICSP/Vulnerabilities-Related-to-Mini-Programs-Permissions ，(对应CCS saTs'23论文 Systematic Analysis of Security and Vulnerabilities in Miniapps)

#### 隐私泄露恶意小程序检测
- TOSEM24-小程序中自动UI检索以及隐私不一致检测**MiniScope**: https://github.com/security-pride/MiniScope【混合分析工具】】
- ICSE'21-小程序污点分析检测**TaintMini**：https://github.com/OSUSecLab/TaintMini 【已复现成功，主机虚拟机中（该工具只能在Linux系统下使用）】
- TSE'23西交-小程序隐私不一致检测**MiniDetector**:https://github.com/xjtu-intsoft/MiniDetector 【自定义微信小程序爬虫，静态分析】
- TIFS'24复旦-小程序违规开发行为检测工具**MiniAppSecurity**：https://github.com/seclab-fudan/MiniAppSecurity 【使用WALA静态分析框架，暂未调通】
- 复旦-小程序隐私过度收集行为检测**SPOChecker**：https://github.com/ppflower/XPOScope 【需要xposed模块进行动态分析】
- TDSC'23复旦-小程序中隐私泄露检测**MiniTracker**：https://github.com/flyboss/MiniTracker 【静态污点分析，提供了百度小程序解包工具，和CodeQL以及TaintMini进行对比】】【已复现成功，主机代码盘中（Windows系统中可用）】
- ASE'23北邮-小程序中APP Secert泄露检测**WeMint**: https://anonymous.4open.science/r/WEMINT 【已复现成功，位于实验ubuntun虚拟机中】

### 小程序漏洞
-CVE-2024-40433：webview中cookie泄露 https://github.com/yikaikkk/CookieShareInWebView/tree/master

### 其他安全工具（待分类）
- NDSS'25-复旦-小程序中证书泄密大规模分析研究：https://github.com/KeyMagnetProject2025/KeyMagnet 【动态分析部分缺少相关文件无法运行】
- ICSE'23-超级应用中不一致API检测工具**APIDiff**：https://github.com/OSUSecLab/APIDiff
- CCS'24-跨站请求伪造分析工具**MiniCAT**: https://github.com/kee1ongz/MiniCAT
- CCS'20-跨小程序伪造工具**CMRFScanner**：https://github.com/OSUSecLab/CMRFScanner 【已复现成功，主机虚拟机中（只能Linux系统使用）】

### 其他平台恶意软件检测工具
- 安卓中代码动态加载恶意组件间通信行为检测工具DINA：https://github.com/Mohannadcse/DINA
- ExtAnalysis 浏览器插件安全检测工具： https://github.com/Tuhinshubhra/ExtAnalysis
- 使用机器学习进行恶意软件分类：https://github.com/trucanh21/android-malware-detection-using-machine-learning
- AndroPyTool从apk文件中提取静态和动态特征: https://github.com/alexMyG/AndroPyTool
