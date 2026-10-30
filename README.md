# alistrode 项目索引

[alistrode](https://github.com/alistrode) 各项目的用途、分发包、来源和使用注意事项。更新日期：2026-10-30。

这里按“能帮你做什么”介绍各个项目，并列出运行包、来源和使用时需要注意的事。**有没有自包含分发包，与仓库有没有上传完，是两回事，下面分开列出。**

## 项目地图

```text
alistrode/
├── clipboard — 随手剪贴板
│   自动记住复制过的文字，按快捷键搜索旧记录，选中后再次粘贴，省去来回找原文。
├── project-manager — 项目总管
│   把散落在不同目录和电脑上的项目整理成清单，查看分组、依赖关系和相关 AI 会话。
├── researchdesk — 资料调研助手
│   输入一个问题，搜索网页、论文、GitHub 和社媒公开资料，再用本机 AI 整理带来源的报告。
├── promptlab — 提示词调优助手
│   输入原提示词、目标和样例，让本机 AI 尝试改写并比较效果，由你决定是否采用。
├── agenthub — AI 分工协作台
│   给出一个目标，让本机 AI 分别扮演规划、分析、执行和审查角色，分步形成可审核的方案。
├── workdesk — 一体工作台
│   在同一个窗口使用调研、提示词调优和 AI 协作，把一个工具的结果交给另一个工具继续处理。
├── omnidispatch — 多平台发布管家
│   集中管理多个平台的账号、素材和定时发布任务，查看发布进度，减少反复切换平台的操作。
├── file-bridge — 跨设备文件桥
│   一台电脑开着服务，手机和其他电脑打开同一个网址，就能互传文字、图片和文件。
├── devspace-vm — AI 编程工具站
│   把电脑上的文件读写、代码修改和终端命令提供给获授权的 AI，让 AI 直接在这台电脑上处理项目。
├── vm-unified-gui — 虚拟机多桌面工作台
│   在浏览器里集中查看、操作 Ubuntu 虚拟机中的多个桌面和容器应用，少开一堆独立窗口。
├── elixir-sqlite-chunker — 代码分块资料库
│   把 Elixir 源码按函数拆开存进数据库，让其他程序按编号或图谱节点读取、修改和管理代码块。
├── ssh-relay-3.0 — 远程电脑连接器 3.0
│   通过公网中继连接另一台电脑，让 AI 或工具远程执行命令、传文件和管理任务。
├── ssh-relay-5.7 — 远程电脑连接器 5.7
│   用桌面客户端或云端程序配对远端电脑，记住设备后继续连接，供 AI 远程操作。
├── ssh-relay-5.8 — 远程电脑连接器 5.8
│   同系列的后续版本仓库，用于连接和操作远端电脑；本版本内容尚未上传完整。
├── open-deploy — 系统装机助手
│   制作启动 U 盘、安装 PXVIRT 虚拟化系统，并衔接后续虚拟机部署与故障恢复；尚未上传完整。
└── - — 待整理入口
    尚未上传完整，项目名称和用途待补充。
```

## 运行包怎么看

“有包”表示已有包含应用及对应语言运行时的分发包；需要另装模型、外部服务或依赖固定路径的情况另作说明。“没包”表示没有符合要求的自包含包。上传中的项目另外标“没传完”，不把两种状态混为一谈。

| 项目仓库 | 自包含分发包 | 上传进度 | 平台、入口与额外条件 |
| --- | --- | --- | --- | --- |
| [随手剪贴板（clipboard）](https://github.com/alistrode/clipboard) | **有包**  | 上传完成情况未单独核实 | Windows / Linux x64，包在 `deliverables/`，分卷需先合并；含 Electron。Linux 仍需桌面系统库。 |
| [项目总管（project-manager）](https://github.com/alistrode/project-manager) | **有包**  | 上传完成情况未单独核实 | Windows x64，`release/windows-x64/START.cmd`；含 Python 与 Tcl/Tk。 |
| [资料调研助手（researchdesk）](https://github.com/alistrode/researchdesk) | **有包**  | 上传完成情况未单独核实 | Windows x64，[Releases](https://github.com/alistrode/researchdesk/releases)；含 .NET，另需本机 Ollama、模型和联网搜索。 |
| [提示词调优助手（promptlab）](https://github.com/alistrode/promptlab) | **有包**  | 上传完成情况未单独核实 | Windows x64，[Releases](https://github.com/alistrode/promptlab/releases)；含 .NET，另需本机 Ollama 和模型。 |
| [AI 分工协作台（agenthub）](https://github.com/alistrode/agenthub) | **有包**  | 上传完成情况未单独核实 | Windows x64，[Releases](https://github.com/alistrode/agenthub/releases)；含 .NET，另需本机 Ollama 和模型。 |
| [一体工作台（workdesk）](https://github.com/alistrode/workdesk) | **没包（整套功能）**  | 上传完成情况未单独核实 | 有自包含启动器与核心服务的 Release，但子模块和 GuIO 依赖原机器固定绝对路径，整套不能直接移到一个新文件夹运行。 |
| [多平台发布管家（omnidispatch）](https://github.com/alistrode/omnidispatch) | **有包（管理端）**  | 上传完成情况未单独核实 | Windows 包在 `packages/`，含 Python 和生产依赖；发布引擎、ffprobe、平台账号与授权需按通道另配。 |
| [跨设备文件桥（file-bridge）](https://github.com/alistrode/file-bridge) | **有包（候选包）**  | 上传完成情况未单独核实 | `release/` 有 Windows x64 3.1.1 包，含 Node.js 与 cloudflared；最终兼容验收仍有未完成项。 |
| [AI 编程工具站（devspace-vm）](https://github.com/alistrode/devspace-vm) | **有包（候选包）**  | 上传完成情况未单独核实 | Windows x64，`release/` 分卷及 `Extract.cmd`；包含运行时和工具。现有构建早于最后源码修改，尚未完成启动和 MCP 验收。 |
| [虚拟机多桌面工作台（vm-unified-gui）](https://github.com/alistrode/vm-unified-gui) | **没包**  | 上传完成情况未单独核实 | 有工程快照、分卷归档与部分运行时；不含 Ubuntu 虚拟磁盘或 Docker 镜像，依赖原有虚拟机环境。 |
| [代码分块资料库（elixir-sqlite-chunker）](https://github.com/alistrode/elixir-sqlite-chunker) | **没包**  | 上传完成情况未单独核实 | 交付源码；需 Python，导入器另需 Elixir。 |
| [远程电脑连接器 3.0（ssh-relay-3.0）](https://github.com/alistrode/ssh-relay-3.0) | **有包**  | 上传完成情况未单独核实 | `release/` 有 Windows x64 ZIP 与 Linux x64 tar.gz；保留完整解压目录。 |
| [远程电脑连接器 5.7（ssh-relay-5.7）](https://github.com/alistrode/ssh-relay-5.7) | **有包**  | 上传完成情况未单独核实 | `packages/5.7/` 有 Windows x64 桌面包与 Linux x64 Cloud 包。 |
| [远程电脑连接器 5.8（ssh-relay-5.8）](https://github.com/alistrode/ssh-relay-5.8) | **没包（5.8 对应包）**  | 没传完 | 已有 5.7 包不算 5.8 对应分发包；5.8 内容正在上传。 |
| [系统装机助手（open-deploy）](https://github.com/alistrode/open-deploy) | **有包（Windows 工具包）**  | 没传完 | 项目已有 Windows 工具包，正在向组织仓库上传；下载入口和配套材料待补齐。 |
| [待整理入口（-）](https://github.com/alistrode/-) | **没包**  | 没传完 | 名称、用途和交付内容待补充。 |


## 项目简述、来源与风险

### 随手剪贴板（Clipboard Local）

本地保存纯文本剪贴板历史，支持搜索、快捷键和 Windows 原位置粘贴。基于 Electron / SQLite 实现；现有说明未确认它是某个第三方剪贴板项目的修改版，不能仅凭依赖推断上游。

**注意：**复制过的密码、令牌、私人文本可能被保存到本地历史，建议及时删除敏感记录。Windows 会在运行期间接管指定快捷键，可能与其他软件冲突；Linux Wayland 的后台剪贴板与快捷键能力取决于桌面环境。包结构核对不代表每个系统上的最新包都已实机验收。

### 项目总管（Project Manager）

管理项目清单、分组、依赖树、置顶和 Codex 会话索引，并可由明确点击触发 SSH 资料交付。来自已有本地项目管理器源码，使用 Python/Tk；目前未确认第三方原始开源仓库。

**注意：**项目清单和会话索引可能包含私人路径与资料；删除或调整数据前保留备份。资料交付前确认远端目标和文件范围，避免发错主机。迁移时检查数据目录配置，不要直接沿用旧机器的绝对路径。

### 资料调研助手（ResearchDesk）

跨 GitHub、学术来源、网页及社媒公开索引检索，保留来源链接后交给本机 Ollama 总结。**独立实现，参考设计而非修改原代码**：包括 [STORM](https://github.com/stanford-oval/storm)、[Open Deep Research](https://github.com/langchain-ai/open_deep_research)、[last30days-skill](https://github.com/mvanhorn/last30days-skill)；SearXNG 是可选搜索服务。

**注意：**检索覆盖不完整，模型总结也可能误读来源，重要结论应打开原链接核对。搜索词会发送给所用搜索服务，不宜直接查询机密内容；付费搜索 API 可能消耗额度。免费通道可能限流或变化。

### 提示词调优助手（PromptLab）

用本机模型生成提示词候选、对比原版与回归样例，并由用户手动采纳。**独立实现，仅参考设计**：[agent_learning](https://github.com/Haozhe-Xing/agent_learning)、[buzz](https://github.com/block/buzz)、[OpenMinis](https://github.com/OpenMinis/OpenMinis)、[bento](https://github.com/nyblnet/bento)，未复制这些项目代码。

**注意：**模型打分是辅助信号，少量样例得分提高不代表所有场景都更好。保留原提示词，增加有代表性的独立回归样例，再人工检查重要输出。提示词和用例会保存在本地，导出时留意敏感内容。

### AI 分工协作台（AgentHub）

把目标拆成有负责人和验收标准的工作项，由规划、分析、执行、审查等角色串行处理，支持检查点与人工通过/退回。**独立 .NET 实现，仅参考 CrewAI、LangGraph、OpenHands 的架构模式**，没有引入这些运行时。

**注意：**多个角色使用同一本地模型，不等于多位独立专家；可能共同遗漏问题。当前主要产出分析和方案，不直接写项目文件或执行 shell，不能把方案输出当作任务已经实际完成。

### 一体工作台（WorkDesk）

把资料调研、提示词调优、AI 分工协作和设备工具放进同一个窗口。例如先调研一个主题，把报告交给 AI 协作台制定方案，再把需要改进的提示词送去调优，减少复制和切换窗口。来源是这些已有本地模块的集成；GuIO 本次未取得源码，未确认其原始开源来源。

**注意：**当前安装依赖固定路径，换机器或移动目录后部分页面可能打不开。关闭工作台窗口不会停止子模块中的任务。研究材料与设置可能含私人信息；设备操作需在 GuIO 内确认，协作方案不会自动变成真实设备操作。

### 多平台发布管家（OmniDispatch）

把多个平台的账号、图片视频素材和发布计划放在一个后台管理：创建任务、安排发布时间、查看结果，失败或结果不明时跟进处理。管理端为自有实现，**集成外部引擎而非将它们全部改写**；候选或适配来源包括 [social-auto-upload](https://github.com/dreammis/social-auto-upload)、[xiaohongshu-mcp](https://github.com/xpzouying/xiaohongshu-mcp)、youtubeuploader、biliup 等。候选通道不等于已授权或已验收，具体以仓库通道说明为准。

**注意：**错误账号、素材或定时设置可能导致误发布；先用测试账号和少量内容确认。平台风控、API 配额及规则变化可能使任务失败或账号受限。提交结果未知时先核对平台实际作品，避免重复发布。妥善保管令牌与本地状态；商业使用前核对各引擎许可。当前不能宣称五平台真实发布全部通过。

### 跨设备文件桥（File Bridge）

一台主机提供网站和 Cloudflare 隧道，手机与电脑通过浏览器互传文字、图片和文件。来源记录指向已有 Codex-Mini 本地目录中的 File Bridge；**原始作者、准确开源仓库和许可尚未确认**。cloudflared 是第三方隧道组件，不等于应用本身的上游。

**注意：**完整网址带访问凭据，拿到网址的人能查看和发送共享内容，不要公开传播。来源名称只是浏览器标签，不是身份认证或权限隔离。主机关机、磁盘满或隧道异常会影响服务；临时网址变化和清除浏览器存储会影响未完成上传。重要文件确认接收完成后再删除原件。

### AI 编程工具站（DevSpace VM）

让获授权的 AI 在指定电脑上查看和修改项目文件、运行终端命令。电脑端启动服务后，通过 Owner 密码授权连接；MCP 是它向 AI 提供这些工具的接口。**明确修改自 [Waishnav/devspace](https://github.com/Waishnav/devspace)**，来源提交为 `8cd2fba227454514f3ce8ef4848012753103e773`，保留 MIT 许可。当前归档包含本地未提交修改及原有较早构建。

**注意：**开发工具能读写文件、运行命令，授权给 AI 前确认工作目录与权限，先用于可恢复的项目副本。保管 Owner 密码和令牌，不随意开放公网入口。现有包不是最后源码重新构建的产物，需留意源码与运行行为可能不同。

### 虚拟机多桌面工作台（VM Unified GUI）

在现有 Ubuntu 虚拟机中，将多个容器应用和 Xfce 桌面集中显示在浏览器。自有控制/整合代码配合 **修改过的 [Xpra](https://github.com/Xpra-org/xpra) 与 [xpra-html5](https://github.com/Xpra-org/xpra-html5)**，另依赖 Docker、Xorg、nginx 等组件；不是一个完整的新操作系统镜像。

**注意：**部署快照绑定原机器路径、服务和显示环境，不要直接覆盖到另一台正常使用的系统。安装与模式切换可能重启项目桌面或应用，先保存工作并为虚拟机留快照。浏览器输入、剪贴板和模式切换仍有未完成验收项。再分发修改组件时保留相应开源许可。

### 代码分块资料库（Elixir SQLite Chunker）

给需要管理代码片段的开发者使用：把 Elixir 文件按函数拆开，每块存进 SQLite 数据库，再让其他程序按块编号或图谱节点查找、读取、改写和删除；同时记录哪些节点拥有这些代码块的访问关系。扩展自已有本地 `elixir-sqlite-chunker` 工程；**准确的第三方原始开源仓库尚未确认**，不能将 Python、Elixir 或 SQLite 依赖当作应用来源。

**注意：**导入时只收录支持的函数块，不包含模块全部代码，不能拿块库代替完整源码备份。首次打开旧数据库可能执行结构迁移，先复制数据库；覆写、删除和所有权登记会影响后续读取。接口默认只监听本机，节点编号不能直接当作公网用户认证。

### 远程电脑连接器（SSH Relay 3.0 / 5.7 / 5.8）

通过公网中继提供 SSH、文件传输和 MCP 远程操作。MCP 工具目录和部分辅助代码源自 **MCP SSH Manager（MIT）**，来源记录见 3.0 的 `source/docs/MCP-SOURCE-PROVENANCE.json`；中继与后续适配另行实现。现有资料尚不足以给出原项目唯一可信的上游仓库 URL。

**注意：**配对后可按远端账号权限执行命令、传文件，配对码、私钥和运行状态只交给可信的人或 AI。远程删除、部署等操作前确认目标与备份；网络中断后先查询原任务结果，避免重复执行。公网中继可用性与网络有关，不保证永不断线。3.0 与 5.7 应使用各自匹配的程序和配置；5.8 内容尚未上传完整，使用时等对应版本说明和包上传齐全，勿混用其他版本配置。

### 系统装机助手（OpenDeploy）

帮助把电脑装成可运行虚拟机的 PXVIRT 主机：先制作启动 U 盘，再安装系统，之后衔接虚拟机部署和故障恢复。**源码和 Windows 工具包正在上传，组织仓库尚未上传完整。**现有资料表明它围绕 PXVIRT、GRUB、VirtualBox 等组件组织流程；尚未确认 OpenDeploy 应用修改自哪个第三方仓库，不能把这些组件笼统写成它的原始源码来源。

**注意：装机属于会改变磁盘和启动环境的操作。** 选错盘、写盘中断、介质故障、驱动或引导不兼容，可能导致数据丢失，或安装到一半后原系统和新系统都暂时打不开。先把重要数据备份到不参与安装的设备，确认目标盘，准备可靠的 U 盘及原系统恢复材料。**最好同时备有两台电脑**：一台安装出问题时，另一台仍能下载镜像、查资料、重新写 U 盘，再重装或恢复。只有一台时，至少提前准备好备用安装介质。虚拟机流程成功不代表实体硬件安装已经通过。

### 待整理入口（`-`）

尚未上传完整，后续补充项目中文名、用途、运行包及来源。

## 核对依据与维护

本页结合项目地图、仓库说明及 Releases 整理。上传期间，仓库里的暂缺文件和旧说明不能代表项目最终交付情况；相关项目标为“尚未上传完整”，待上传完成后更新。

- 分发包：各项目 `release/`、`packages/`、`deliverables/` 及 Releases。
- 依赖边界：ResearchDesk、PromptLab、AgentHub、WorkDesk、OmniDispatch 的 `DEPENDENCIES.md`。
- 来源及状态：DevSpace 的 `SOURCE-MANIFEST.json` / `HANDOFF.md`；File Bridge 的 `docs/SOURCE-MANIFEST.json` / `docs/HANDOFF.md`；VM Unified GUI 的 README；SSH Relay 的来源记录与包说明。
- 包名、平台或来源变动时，同时更新速查表和项目说明。来源待确认的项目，应有实际代码来源记录后再补上游链接，不能凭相似功能猜测。

第三方依赖遵循各自许可证。此文档的“有包”只描述交付形态，不作无故障、商业适用或全部功能通过的承诺。
