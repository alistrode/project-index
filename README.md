# alistrode 项目索引 · Project Index

本页介绍 alistrode 各项目的定位、主要功能、分发包与代码来源。更新日期：2026-10-30。

## 项目地图

- [随手剪贴板（Clipboard Local）](#clipboard) — 可自定义交互的本地剪贴板历史管理工具。
- [项目总管（Project Manager）](#project-manager) — 跨目录与主机的项目资料及 AI 会话索引管理工具。
- [资料调研助手（ResearchDesk）](#researchdesk) — 多来源公开资料检索与本地 AI 研究报告工具。
- [提示词调优助手（PromptLab）](#promptlab) — 基于样例评测与人工采纳的本地提示词优化工具。
- [AI 分工协作台（AgentHub）](#agenthub) — 支持角色分工、阶段恢复与人工审核的本地 AI 协作工具。
- [一体工作台（WorkDesk）](#workdesk) — 整合调研、提示词优化、AI 协作与设备工具的桌面工作入口。
- [多平台发布管家（OmniDispatch）](#omnidispatch) — 多平台账号、素材与定时发布任务管理系统。
- [跨设备文件桥（File Bridge）](#file-bridge) — 基于统一网页入口的跨设备文字、图片及文件传输工具。
- [网页 GPT 本机工具站（DevSpace VM）](#devspace-vm) — 通过授权 MCP 接口连接 ChatGPT 与本机开发环境的工具服务。
- [虚拟机多桌面工作台（VM Unified GUI）](#vm-unified-gui) — 面向 Ubuntu 虚拟机的多容器图形应用与桌面整合环境。
- [代码图谱分块库（Elixir SQLite Chunker）](#elixir-sqlite-chunker) — 连接 Elixir 函数块、SQLite 存储与图谱节点的代码管理服务。
- [远程电脑连接器 3.0（SSH Relay 3.0）](#ssh-relay-3.0) — 集成 MCP 工具的公网 SSH 中继与远程操作程序。
- [远程电脑连接器 5.7（SSH Relay Pro 5.7）](#ssh-relay-5.7) — 支持设备配对、任务恢复与云端运行的远程电脑操作程序。
- [远程电脑连接器 5.8（SSH Relay Pro 5.8）](#ssh-relay-5.8) — SSH Relay 系列的后续远程连接版本。
- [系统装机助手（OpenDeploy）](#open-deploy) — 面向 PXVIRT 虚拟化系统的安装介质制作与部署恢复工具。
- [待整理项目（Pending Project）](#pending) — 尚待补充项目资料的仓库入口。

## 项目对照表

“有包”表示已有包含应用及对应语言运行时的分发包，额外运行条件见正文。“没包”与“没传完”分别表示分发形态和上传进度，两者独立。

| 项目 | 自包含分发包 | 上传进度 | 来源 | 主要特点 |
| --- | --- | --- | --- | --- |
| [随手剪贴板（Clipboard Local）](#clipboard) | 有包：Windows / Linux | — | 独立实现；Electron、SQLite 为依赖 | 不设历史条数、保留天数和单条字数的人为上限；全文检索；原输入位置粘贴；自定义快捷键与浏览状态 |
| [项目总管（Project Manager）](#project-manager) | 有包：Windows | — | 已有本地 ProjectManager 工程；第三方上游未确认 | 主机与性质分组、项目依赖树、置顶排序、Codex 会话索引、向已连接云端 AI 交付项目资料 |
| [资料调研助手（ResearchDesk）](#researchdesk) | 有包：Windows | — | 独立实现；参考 STORM、Open Deep Research、last30days-skill | 网页、论文、GitHub 与社媒公开索引检索；时间窗筛选、去重、来源追溯；本机模型归纳 |
| [提示词调优助手（PromptLab）](#promptlab) | 有包：Windows | — | 独立实现；参考 agent_learning、buzz、OpenMinis、bento | 原版基线、候选生成、盲评、独立回归集；只有达到提升门槛才开放采纳 |
| [AI 分工协作台（AgentHub）](#agenthub) | 有包：Windows | — | 独立实现；参考 CrewAI、LangGraph、OpenHands | 规划、分析、执行方案、审查和协调分工；阶段检查点；角色独立上下文；串行运行适配低显存 |
| [一体工作台（WorkDesk）](#workdesk) | 没包：整套独立运行包；有核心程序包 | — | 整合 ResearchDesk、PromptLab、AgentHub 与 GuIO；GuIO 上游未确认 | 统一入口、模块按需启动、结果收集与跨模块材料交接、材料版本历史 |
| [多平台发布管家（OmniDispatch）](#omnidispatch) | 有包：Windows 管理端 | — | 自有管理端；集成 social-auto-upload、xiaohongshu-mcp 等外部引擎 | 定时发布、分块续传、持久任务账本；提交结果未知时暂停核验，避免盲目重发；凭证加密 |
| [跨设备文件桥（File Bridge）](#file-bridge) | 有包：Windows | — | 已有 File Bridge 工程；原作者与上游仓库未确认 | 浏览器免装客户端；最大 1 GB 文件；断点续传、分块校验、来源筛选与长期归档 |
| [网页 GPT 本机工具站（DevSpace VM）](#devspace-vm) | 有包：Windows 候选包 | — | 修改自 Waishnav/devspace（MIT） | 对接 ChatGPT 官方自定义 MCP 连接入口；Owner 密码授权；文件读写、代码修改、终端命令及 Git 差异查看 |
| [虚拟机多桌面工作台（VM Unified GUI）](#vm-unified-gui) | 没包：有部署快照，非自包含环境 | 部分资料补传中 | 自有整合代码；修改 Xpra 与 xpra-html5 | 三个独立原生桌面同屏；统一桌面集中显示容器应用；共用一套宿主桌面依赖 |
| [代码图谱分块库（Elixir SQLite Chunker）](#elixir-sqlite-chunker) | 没包：源码交付 | — | 已有 elixir-sqlite-chunker 工程；第三方上游未确认 | 按函数语法结构切块；节点所有权校验；逐块读写结果；块引用回写图谱，正文与密钥不进入图谱 |
| [远程电脑连接器 3.0（SSH Relay 3.0）](#ssh-relay-3.0) | 有包：Windows / Linux | — | MCP SSH Manager（MIT）部分代码与工具定义；中继另行实现 | 公网中继、远程命令、文件传输、持久会话，以及供 AI 调用的 MCP 工具 |
| [远程电脑连接器 5.7（SSH Relay Pro 5.7）](#ssh-relay-5.7) | 有包：Windows / Linux Cloud | — | SSH Relay 系列延续开发；继承 MCP SSH Manager 部分代码 | 已记住设备重连、持久任务查询与取消；修复心跳过期误停后台；桌面版与无桌面云端版 |
| [远程电脑连接器 5.8（SSH Relay Pro 5.8）](#ssh-relay-5.8) | 没包：5.8 对应包 | 没传完 | SSH Relay 系列延续开发 | 设备连接与远程操作；本版本新增功能待上传完整后补充 |
| [系统装机助手（OpenDeploy）](#open-deploy) | 有包：Windows 工具包 | 没传完 | OpenDeploy 工程；使用 PXVIRT、GRUB、VirtualBox 等组件；应用上游未确认 | 启动介质制作、指定目标盘安装、分阶段作业与恢复、VirtualBox 克隆机部署入口 |
| [待整理项目（Pending Project）](#pending) | 没包 | 没传完 | 待补充 | 项目名称、功能与来源待补充 |

## 项目介绍

<a id="clipboard"></a>

### 随手剪贴板（Clipboard Local） · [项目仓库 ↗](https://github.com/alistrode/clipboard)

面向长期积累文本、反复检索与粘贴的使用场景，提供独立于 Windows 系统历史机制的本地剪贴板记录与交互界面。

- **长期保存：**不设历史条数、保留天数及单条字数的人为上限，不按时间自动清理记录；SQLite 逐条事务写入，支持程序重启后继续检索。
- **自定义剪贴板体验：**支持自定义快捷键、托盘运行和开机自启；可选择每次打开显示最新记录，或恢复上次搜索、选中项和滚动位置。
- **原位置粘贴：**Windows 小窗口保留原输入框的焦点与选区，选择历史后在原位置粘贴；无法确认输入目标时保留复制结果，避免向不确定窗口输入。
- **检索与管理：**支持中文子串及长文本全文检索、查看全文、选择删除；相同原文去重并置顶。

**分发与适用范围：**Windows / Linux x64 包位于 [deliverables](https://github.com/alistrode/clipboard/tree/main/deliverables)，需按说明合并分卷。包含 Electron；Linux 仍依赖桌面系统库。Windows 支持 Win+V 接管，Linux 的快捷键能力随桌面环境而异。

**保存说明：**历史不主动过期，不等于任何情况下都“永不丢失”。记录捕获限于程序运行期间，极快速连续复制可能漏过中间状态；存储容量仍受磁盘与数据库约束。

**来源：**独立应用实现，使用 Electron 与 SQLite，未确认第三方剪贴板应用上游。

[返回项目地图](#项目地图)

<a id="project-manager"></a>

### 项目总管（Project Manager） · [项目仓库 ↗](https://github.com/alistrode/project-manager)

为分散在不同目录、电脑和 AI 会话中的项目建立统一索引，集中展示项目概述、位置、关系和历史讨论。

- **项目组织：**按主机或性质分组，支持主次关系与依赖树、置顶、登记时间及最近活动排序。
- **会话关联：**展开项目查看 Codex 会话，复制单个或全部会话 ID，打开已有会话和项目目录。
- **资料交接：**明确点击项目入口后，将项目资料交付给已连接的云端 AI；同时提供本机只读查询接口。

**分发：**[Windows 单文件夹运行包](https://github.com/alistrode/project-manager/tree/main/release/windows-x64) 包含 Python 与 Tcl/Tk，使用 `START.cmd` 启动。

**来源：**由已有本地 ProjectManager 工程继续整理，尚未确认第三方原始开源仓库。

[返回项目地图](#项目地图)

<a id="researchdesk"></a>

### 资料调研助手（ResearchDesk） · [项目仓库 ↗](https://github.com/alistrode/researchdesk)

围绕一个研究问题检索公开资料，以来源链接和摘录组织证据，再由本机模型生成研究简报。

- **多来源搜索：**覆盖 GitHub、arXiv、Crossref、网页与社媒公开索引，并支持 YouTube 数据通道。
- **结果整理：**按时间窗、相关性和新近程度筛选，规范化链接去重；保留候选被筛除的原因。
- **证据报告：**总结共识、分歧、趋势和待核实事项，保留原始链接以便复核，支持导入人工补充材料。
- **本地模型：**报告归纳使用本机 Ollama；搜索通道支持免费服务与可选的 SearXNG、Brave、Tavily 等配置。

**分发：**[Windows 运行包](https://github.com/alistrode/researchdesk/releases) 包含 .NET，另需本机 Ollama 与模型；检索需要联网。公开索引覆盖和模型总结质量随来源与模型变化。

**来源：**独立实现，参考 [STORM](https://github.com/stanford-oval/storm)、[Open Deep Research](https://github.com/langchain-ai/open_deep_research) 与 [last30days-skill](https://github.com/mvanhorn/last30days-skill) 的研究流程，未复制这些项目代码。

[返回项目地图](#项目地图)

<a id="promptlab"></a>

### 提示词调优助手（PromptLab） · [项目仓库 ↗](https://github.com/alistrode/promptlab)

围绕真实任务样例改进提示词，将候选生成、效果对比和人工决定保存在同一条评测记录中。

- **基线对比：**先执行原提示词，再生成候选并按相同样例评测。
- **独立回归：**调优集用于改写反馈，回归集只参与最终评分，减少只对训练样例有效的改写。
- **采纳门槛：**候选总分必须高于原版且回归不退步，才开放采纳；最终由用户确认。
- **可追溯记录：**支持最多 12 条样例、1–3 轮调优，工作包和评测报告可导入、导出为 JSON。

**分发：**[Windows 自包含包](https://github.com/alistrode/promptlab/releases) 另需本机 Ollama 与模型。评分是模型辅助评价，产品保留人工采纳步骤。

**来源：**独立实现，参考 [agent_learning](https://github.com/Haozhe-Xing/agent_learning)、[buzz](https://github.com/block/buzz)、[OpenMinis](https://github.com/OpenMinis/OpenMinis)、[bento](https://github.com/nyblnet/bento) 的设计思路，未复制其代码。

[返回项目地图](#项目地图)

<a id="agenthub"></a>

### AI 分工协作台（AgentHub） · [项目仓库 ↗](https://github.com/alistrode/agenthub)

将一个目标组织为有负责人和验收标准的工作项，由不同 AI 角色依次处理，并在最终结果提交前保留人工审核。

- **角色分工：**规划师拆解任务，分析师补充依据，执行专家形成方案，审查员复核，协调员汇总待解决项。
- **阶段恢复：**每个角色完成后保存检查点，中断后从原会话的最后阶段继续。
- **独立上下文：**各角色保留各自的讨论上下文，支持指定角色继续追问。
- **本地运行：**使用同一本机 Ollama 模型串行处理，面向低显存设备；支持人工通过或退回修改。

**分发：**[Windows 自包含包](https://github.com/alistrode/agenthub/releases)，另需 Ollama 与已安装模型。当前提供分析和方案，不包含直接修改项目或执行终端命令的工具。

**来源：**独立 .NET 实现，参考 CrewAI、LangGraph 与 OpenHands 的协作、持久化和人工审核设计，未采用其运行时。

[返回项目地图](#项目地图)

<a id="workdesk"></a>

### 一体工作台（WorkDesk） · [项目仓库 ↗](https://github.com/alistrode/workdesk)

将资料调研、提示词调优、AI 协作与设备工具整合进一个工作入口，支持跨模块传递已整理的结果。

- **统一窗口：**模块按需启动，切换时保留页面，已有服务可继续复用。
- **共享材料：**收集当前结果，编辑后发送到研究问题、提示词草稿或新的协作目标。
- **版本记录：**材料支持 JSON 导入、导出，保存新版本时保留历史。
- **设备入口：**显示 GuIO 设备信息，并打开其原生操作面板。

**分发：**[Releases](https://github.com/alistrode/workdesk/releases) 有自包含核心服务与启动器；完整模块仍依赖原机器的固定路径，因此没有整套可独立迁移的单文件夹包。

**来源：**整合 ResearchDesk、PromptLab、AgentHub 与既有 GuIO；GuIO 的原始开源来源尚未确认。

[返回项目地图](#项目地图)

<a id="omnidispatch"></a>

### 多平台发布管家（OmniDispatch） · [项目仓库 ↗](https://github.com/alistrode/omnidispatch)

以统一后台管理多个平台的账号、素材、定时任务和发布结果，将上传、执行和核验状态持续保存在任务账本中。

- **发布任务：**支持定时执行、同账号串行、分块上传与跨刷新续传。
- **结果保护：**提交过程中断时标记待核验，核验前不自动重发，减少重复发布。
- **账号安全：**凭证加密、管理员双因素认证、会话撤销及操作审计。
- **引擎管理：**外部发布引擎固定版本运行，更新包经签名验证与灰度条件后切换。

**分发：**[Windows 管理端包](https://github.com/alistrode/omnidispatch/tree/main/packages) 含 Python 与生产依赖；发布引擎、账号授权及部分媒体工具另配。候选通道不代表已启用，真实平台发布验收仍待完成。

**来源：**管理端为自有实现，集成 [social-auto-upload](https://github.com/dreammis/social-auto-upload)、[xiaohongshu-mcp](https://github.com/xpzouying/xiaohongshu-mcp)、youtubeuploader 等外部引擎，具体以通道清单为准。

**使用注意：**正式发布前确认账号、素材和时间；结果不明时先核对平台作品。平台规则与各引擎许可分别适用。

[返回项目地图](#项目地图)

<a id="file-bridge"></a>

### 跨设备文件桥（File Bridge） · [项目仓库 ↗](https://github.com/alistrode/file-bridge)

由一台主机提供统一网站，手机和其他电脑通过浏览器上传、查看与下载文字、图片及文件，无需安装接收客户端。

- **统一传输：**多设备使用同一个完整网址，支持最大 1 GB 文件。
- **可恢复上传：**浏览器保存待发送任务，文件分块落盘并校验，中断后复用已有分块。
- **来源筛选：**每条内容标注浏览器来源名称与编号，支持按来源查看。
- **内容保存：**最近内容保留 24 小时，归档长期保存在接收主机；下载支持续传。

**分发：**[Windows 3.1.1 候选包](https://github.com/alistrode/file-bridge/tree/main/release) 含 Node.js 与 cloudflared。主机需开机联网，最终兼容验收仍有未完成项。

**来源：**扩展自既有 File Bridge 工程，来源记录见 `docs/SOURCE-MANIFEST.json`；原作者、准确上游仓库及许可尚未确认。

**使用注意：**完整访问网址包含凭据，持有者可访问共享内容；来源筛选不是权限隔离。临时隧道换网址后，浏览器中原网址的待发任务不会自动跨域迁移。

[返回项目地图](#项目地图)

<a id="devspace-vm"></a>

### 网页 GPT 本机工具站（DevSpace VM） · [项目仓库 ↗](https://github.com/alistrode/devspace-vm)

面向网页端 ChatGPT 与本机项目之间的工具连接：通过 ChatGPT 官方支持的自定义 MCP 连接入口，在授权后调用本机文件与终端工具。需要账号及客户端支持相应连接能力；本项目是第三方工具服务。

- **本机文件操作：**读取、创建、覆写文件，精确替换代码，应用文件变更。
- **项目检索：**目录浏览、文件名匹配与内容搜索，定位项目资料。
- **终端执行：**在服务当前工作目录运行命令，并返回执行结果。
- **变更查看：**提供 Git 差异，后续调用可与上一次变更快照比较。
- **授权连接：**Owner 密码确认，使用授权码、令牌与 MCP 接口建立连接；公网启动入口提供隧道地址。

**分发：**[Windows 候选包](https://github.com/alistrode/devspace-vm/tree/main/release) 包含运行时与开发工具，分卷合并后从 `Start-Local.cmd` 初始化。原有构建早于最后源码修改，尚未完成该包的启动与 MCP 验收。

**来源：**修改自 [Waishnav/devspace](https://github.com/Waishnav/devspace)，保留 MIT 许可。

**使用注意：**授权工具具备真实文件写入和命令执行能力，操作范围取决于服务进程权限；连接前确认项目目录并保管 Owner 密码与令牌。当前终端接口不保留交互进程会话。

[返回项目地图](#项目地图)

<a id="vm-unified-gui"></a>

### 虚拟机多桌面工作台（VM Unified GUI） · [项目仓库 ↗](https://github.com/alistrode/vm-unified-gui)

在一台 Ubuntu 虚拟机内整合多个容器的图形应用，提供独立桌面同屏与统一桌面两种工作模式。

- **三桌面同屏：**三个原生 Xfce 会话各自保留面板、窗口管理、工作区与设置，在同一网页中显示。
- **统一桌面：**同一桌面集中展示来自不同容器的应用窗口。
- **共享基础环境：**桌面会话运行在容器外，共用宿主的一套桌面依赖；容器保留应用及其必需库。
- **后台保留：**切换模式不关闭已有桌面与应用；两个模式中的窗口不是同一个窗口迁移，文档编辑状态不会自动同步。

**分发：**[工程归档](https://github.com/alistrode/vm-unified-gui/tree/main/release) 是既有环境的部署快照，不含 Ubuntu 虚拟磁盘与 Docker 镜像，没有自包含整套运行包；部分资料仍在补传。浏览器输入、剪贴板和模式切换的完整链路尚待最终验收。

**来源：**自有控制与整合代码，配合修改后的 [Xpra](https://github.com/Xpra-org/xpra) 和 [xpra-html5](https://github.com/Xpra-org/xpra-html5)。

[返回项目地图](#项目地图)

<a id="elixir-sqlite-chunker"></a>

### 代码图谱分块库（Elixir SQLite Chunker） · [项目仓库 ↗](https://github.com/alistrode/elixir-sqlite-chunker)

为代码知识图谱提供可独立存取的函数块：解析 Elixir 源文件，把函数内容存入 SQLite，再由图谱节点发起块级操作。

- **语法切块：**按函数、宏及守卫定义拆分，关联紧邻注释和文档标记。
- **块级管理：**支持创建、读取、改写和删除，按节点所有权校验访问关系。
- **图谱联动：**逐块返回操作结果，把成功项的块引用、顺序和行范围写回图谱；正文与密钥不进入图谱。
- **同步反馈：**区分块操作结果与图谱写回结果，支持部分成功反馈，避免把整次请求简单视为全部成功。

**分发：**当前提供 [源码](https://github.com/alistrode/elixir-sqlite-chunker/tree/main/source)，没有自包含包。接口使用 Python 标准库，导入器另需 Elixir。

**来源：**扩展自已有 elixir-sqlite-chunker 工程，未确认第三方原始开源仓库。

**数据说明：**改写代码块不会自动修改原始 Elixir 文件，也不会重建函数调用关系；块操作与图谱写回不是同一个事务。

[返回项目地图](#项目地图)

<a id="ssh-relay-3.0"></a>

### 远程电脑连接器 3.0（SSH Relay 3.0） · [项目仓库 ↗](https://github.com/alistrode/ssh-relay-3.0)

通过公网中继将 SSH 远程操作接入 MCP，使 AI 工具可以在已授权电脑上执行命令、传输文件与管理会话。

- **远程执行：**返回命令输出、错误输出与退出状态。
- **文件与会话：**支持 SFTP、持久终端会话及相关管理工具。
- **中继连接：**通过公网中继传送 SSH 数据，并固定校验远端主机身份。

**分发：**[Windows / Linux x64 包](https://github.com/alistrode/ssh-relay-3.0/tree/main/release)。Windows 现有记录主要为包结构核对，Linux 有真实中继与 MCP 调用记录。

**来源：**部分工具定义和辅助代码源自 MCP SSH Manager（MIT），中继与适配另行实现；来源清单见 `source/docs/MCP-SOURCE-PROVENANCE.json`。

**使用注意：**配对及连接资料只交给可信使用者；执行删除、部署等操作前确认远端目标。

[返回项目地图](#项目地图)

<a id="ssh-relay-5.7"></a>

### 远程电脑连接器 5.7（SSH Relay Pro 5.7） · [项目仓库 ↗](https://github.com/alistrode/ssh-relay-5.7)

以桌面客户端或无桌面云端程序管理远端设备连接，支持已配对设备恢复连接，并保留持续执行任务的状态与操作标识。

- **设备与任务：**设备记忆、重连、持久任务查询和取消，以及文件上传下载。
- **运行修复：**避免单纯因心跳过期误停仍存活的后台；服务失败时显示明确状态和恢复入口。
- **诊断改进：**保留较完整的错误堆栈与嵌套原因，便于排查连接及运行问题。
- **双运行形态：**Windows 桌面版与 Linux Cloud 版分别提供客户端联动和无图形界面运行方式。

**分发：**[5.7 Windows / Linux Cloud 包](https://github.com/alistrode/ssh-relay-5.7/tree/main/packages/5.7)。启动延迟与更广泛的性能改进仍有后续工作。

**来源：**SSH Relay 系列持续开发，继承 MCP SSH Manager 的部分工具定义与辅助代码。

**使用注意：**中断后先查询原任务结果再决定后续操作，避免重复执行有副作用的命令。

[返回项目地图](#项目地图)

<a id="ssh-relay-5.8"></a>

### 远程电脑连接器 5.8（SSH Relay Pro 5.8） · [项目仓库 ↗](https://github.com/alistrode/ssh-relay-5.8)

SSH Relay 系列后续版本，定位为设备配对、远程命令和文件传输工具。

**上传进度：**没传完。当前尚无可明确归属于 5.8 的自包含分发包；仓库中的旧版包不计为本版包。新增功能与本版运行入口待上传完整后补充，不从旧说明推断升级内容。

**来源：**SSH Relay 系列延续开发。

[返回项目地图](#项目地图)

<a id="open-deploy"></a>

### 系统装机助手（OpenDeploy） · [项目仓库 ↗](https://github.com/alistrode/open-deploy)

围绕 PXVIRT 虚拟化系统安装提供从介质制作到部署恢复的工具流程，并为后续虚拟机部署保留衔接入口。

- **安装介质：**从给定镜像制作启动介质，使用明确的目标盘和介质盘身份参数。
- **分阶段作业：**保存作业状态，提供安装、日志与恢复材料入口。
- **虚拟机路线：**提供 VirtualBox 克隆机内的部署入口，将模拟安装与实体机配置区分。

**分发与进度：**已有 Windows 工具包，组织仓库没传完，公开下载入口和配套材料待补齐。工具包不等于包含全部系统镜像及现场配置。

**来源：**OpenDeploy 工程结合 PXVIRT、GRUB、VirtualBox 等组件，尚未确认应用的第三方原始开源仓库。

**装机注意：**选错盘、介质故障或安装中断可能导致数据丢失，或安装到一半后系统无法启动。安装前备份重要数据并准备可靠的恢复介质；最好同时备有两台电脑，安装电脑故障时，可用另一台下载镜像、重新制作 U 盘，再重装或恢复。虚拟机流程成功不代表实体硬件安装已经通过。

[返回项目地图](#项目地图)

<a id="pending"></a>

### 待整理项目（Pending Project） · [项目仓库 ↗](https://github.com/alistrode/-)

仓库资料尚未上传完整，项目名称、定位、功能和来源待补充。当前无自包含分发包。

[返回项目地图](#项目地图)

---

本索引依据项目功能说明、来源清单、运行包和相关实现整理。“参考设计”“修改自上游”“使用第三方依赖”分别标注；未确认的来源不推定为原创或指定项目的分支。项目运行和交付状态以各仓库后续更新为准。
