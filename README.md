# alistrode 项目索引

[alistrode](https://github.com/alistrode) 各项目的用途、分发包、来源和使用注意事项。更新日期：2026-10-30。

本索引以项目地图为线索，再核对公开仓库的文件、说明和 Releases。**有包不等于所有功能已经验收，也不等于完全不需要外部服务。** 下表的“是”表示已有包含应用及对应语言运行时的分发包；Ollama、模型、虚拟机、账号授权等额外条件会单独列出。“否”表示当前公开仓库没有符合该条件的包，或只有依赖原机器的部署快照。没有足够证据的上游来源明确标为待确认。

## 项目地图

```text
alistrode/
├── clipboard             本地纯文本剪贴板历史
├── project-manager       桌面项目清单、分组与会话索引
├── researchdesk          多来源检索与本机模型研究报告
├── promptlab             本地提示词候选生成与评测
├── agenthub              本地多角色协作与人工审核
├── workdesk              上述工具及设备工具的统一入口
├── omnidispatch          多平台内容发布与任务管理
├── file-bridge           浏览器文字、图片和文件互传
├── devspace-vm           带 Owner 认证的开发工具 MCP 服务
├── vm-unified-gui        Ubuntu 多容器应用与桌面统一界面
├── elixir-sqlite-chunker Elixir 函数分块、SQLite 与图谱接口
├── ssh-relay-3.0         公网 SSH 中继与 MCP
├── ssh-relay-5.7         SSH Relay Pro 桌面及云端版本
├── ssh-relay-5.8         当前仍含 5.7 标识和运行包的仓库
├── open-deploy           装机项目入口；公开内容尚未迁移完整
└── -                     空仓库，暂无项目内容
```

## 分发包速查

| 项目仓库 | 是否有自包含分发包 | 平台、入口与额外条件 |
| --- | --- | --- |
| [clipboard](https://github.com/alistrode/clipboard) | **是** | Windows / Linux x64，包在 `deliverables/`，分卷需先合并；含 Electron。Linux 仍需桌面系统库。 |
| [project-manager](https://github.com/alistrode/project-manager) | **是** | Windows x64，`release/windows-x64/START.cmd`；含 Python 与 Tcl/Tk。 |
| [researchdesk](https://github.com/alistrode/researchdesk) | **是** | Windows x64，[Releases](https://github.com/alistrode/researchdesk/releases)；含 .NET，另需本机 Ollama、模型和联网搜索。 |
| [promptlab](https://github.com/alistrode/promptlab) | **是** | Windows x64，[Releases](https://github.com/alistrode/promptlab/releases)；含 .NET，另需本机 Ollama 和模型。 |
| [agenthub](https://github.com/alistrode/agenthub) | **是** | Windows x64，[Releases](https://github.com/alistrode/agenthub/releases)；含 .NET，另需本机 Ollama 和模型。 |
| [workdesk](https://github.com/alistrode/workdesk) | **否（整套功能）** | 有自包含启动器与核心服务的 Release，但子模块和 GuIO 依赖原机器固定绝对路径，整套不能直接移到一个新文件夹运行。 |
| [omnidispatch](https://github.com/alistrode/omnidispatch) | **是（管理端）** | Windows 包在 `packages/`，含 Python 和生产依赖；发布引擎、ffprobe、平台账号与授权需按通道另配。 |
| [file-bridge](https://github.com/alistrode/file-bridge) | **是（候选包）** | `release/` 有 Windows x64 3.1.1 包，含 Node.js 与 cloudflared；最终兼容验收仍有未完成项。 |
| [devspace-vm](https://github.com/alistrode/devspace-vm) | **是（候选包）** | Windows x64，`release/` 分卷及 `Extract.cmd`；包含运行时和工具。现有构建早于最后源码修改，尚未完成启动和 MCP 验收。 |
| [vm-unified-gui](https://github.com/alistrode/vm-unified-gui) | **否** | 有工程快照、分卷归档与部分运行时；不含 Ubuntu 虚拟磁盘或 Docker 镜像，依赖原有虚拟机环境。 |
| [elixir-sqlite-chunker](https://github.com/alistrode/elixir-sqlite-chunker) | **否** | 交付源码；需 Python，导入器另需 Elixir。 |
| [ssh-relay-3.0](https://github.com/alistrode/ssh-relay-3.0) | **是** | `release/` 有 Windows x64 ZIP 与 Linux x64 tar.gz；保留完整解压目录。 |
| [ssh-relay-5.7](https://github.com/alistrode/ssh-relay-5.7) | **是** | `packages/5.7/` 有 Windows x64 桌面包与 Linux x64 Cloud 包。 |
| [ssh-relay-5.8](https://github.com/alistrode/ssh-relay-5.8) | **是（现存为 5.7 包）** | 当前 README 与 `packages/5.7/` 仍标 5.7；尚不能认定为独立可用的 5.8 发行版。 |
| [open-deploy](https://github.com/alistrode/open-deploy) | **否（当前公开仓库）** | 当前默认分支只有迁移工作流，无公开可用应用包；项目地图中的内部 Windows 完整包不等于已经迁移到此仓库，也不包含通用安装所需的全部镜像与现场配置。 |
| [-](https://github.com/alistrode/-) | **否** | 空仓库。 |

## 项目简述、来源与风险

### Clipboard Local

本地保存纯文本剪贴板历史，支持搜索、快捷键和 Windows 原位置粘贴。基于 Electron / SQLite 实现；现有说明未确认它是某个第三方剪贴板项目的修改版，不能仅凭依赖推断上游。

**注意：**复制过的密码、令牌、私人文本可能被保存到本地历史，建议及时删除敏感记录。Windows 会在运行期间接管指定快捷键，可能与其他软件冲突；Linux Wayland 的后台剪贴板与快捷键能力取决于桌面环境。包结构核对不代表每个系统上的最新包都已实机验收。

### 桌面项目管理器

管理项目清单、分组、依赖树、置顶和 Codex 会话索引，并可由明确点击触发 SSH 资料交付。来自已有本地项目管理器源码，使用 Python/Tk；目前未确认第三方原始开源仓库。

**注意：**项目清单和会话索引可能包含私人路径与资料；删除或调整数据前保留备份。资料交付前确认远端目标和文件范围，避免发错主机。迁移时检查数据目录配置，不要直接沿用旧机器的绝对路径。

### ResearchDesk

跨 GitHub、学术来源、网页及社媒公开索引检索，保留来源链接后交给本机 Ollama 总结。**独立实现，参考设计而非修改原代码**：包括 [STORM](https://github.com/stanford-oval/storm)、[Open Deep Research](https://github.com/langchain-ai/open_deep_research)、[last30days-skill](https://github.com/mvanhorn/last30days-skill)；SearXNG 是可选搜索服务。

**注意：**检索覆盖不完整，模型总结也可能误读来源，重要结论应打开原链接核对。搜索词会发送给所用搜索服务，不宜直接查询机密内容；付费搜索 API 可能消耗额度。免费通道可能限流或变化。

### PromptLab

用本机模型生成提示词候选、对比原版与回归样例，并由用户手动采纳。**独立实现，仅参考设计**：[agent_learning](https://github.com/Haozhe-Xing/agent_learning)、[buzz](https://github.com/block/buzz)、[OpenMinis](https://github.com/OpenMinis/OpenMinis)、[bento](https://github.com/nyblnet/bento)，未复制这些项目代码。

**注意：**模型打分是辅助信号，少量样例得分提高不代表所有场景都更好。保留原提示词，增加有代表性的独立回归样例，再人工检查重要输出。提示词和用例会保存在本地，导出时留意敏感内容。

### AgentHub

把目标拆成有负责人和验收标准的工作项，由规划、分析、执行、审查等角色串行处理，支持检查点与人工通过/退回。**独立 .NET 实现，仅参考 CrewAI、LangGraph、OpenHands 的架构模式**，没有引入这些运行时。

**注意：**多个角色使用同一本地模型，不等于多位独立专家；可能共同遗漏问题。当前主要产出分析和方案，不直接写项目文件或执行 shell，不能把方案输出当作任务已经实际完成。

### WorkDesk

将 ResearchDesk、PromptLab、AgentHub 和 GuIO 汇入统一工作台，支持共享材料流转。来源是这些已有本地模块的集成；GuIO 本次未取得源码，未确认其原始开源来源。

**注意：**当前安装依赖固定路径，换机器或移动目录后部分页面可能打不开。关闭工作台窗口不会停止子模块中的任务。研究材料与设置可能含私人信息；设备操作需在 GuIO 内确认，协作方案不会自动变成真实设备操作。

### OmniDispatch

多平台内容发布中枢，管理账号、任务账本、授权、审计和发布引擎。管理端为自有实现，**集成外部引擎而非将它们全部改写**；候选或适配来源包括 [social-auto-upload](https://github.com/dreammis/social-auto-upload)、[xiaohongshu-mcp](https://github.com/xpzouying/xiaohongshu-mcp)、youtubeuploader、biliup 等。候选通道不等于已授权或已验收，具体以仓库通道说明为准。

**注意：**错误账号、素材或定时设置可能导致误发布；先用测试账号和少量内容确认。平台风控、API 配额及规则变化可能使任务失败或账号受限。提交结果未知时先核对平台实际作品，避免重复发布。妥善保管令牌与本地状态；商业使用前核对各引擎许可。当前不能宣称五平台真实发布全部通过。

### File Bridge

一台主机提供网站和 Cloudflare 隧道，手机与电脑通过浏览器互传文字、图片和文件。来源记录指向已有 Codex-Mini 本地目录中的 File Bridge；**原始作者、准确开源仓库和许可尚未确认**。cloudflared 是第三方隧道组件，不等于应用本身的上游。

**注意：**完整网址带访问凭据，拿到网址的人能查看和发送共享内容，不要公开传播。来源名称只是浏览器标签，不是身份认证或权限隔离。主机关机、磁盘满或隧道异常会影响服务；临时网址变化和清除浏览器存储会影响未完成上传。重要文件确认接收完成后再删除原件。

### DevSpace VM 修改版

带 Owner 密码认证的 MCP 开发工具服务。**明确修改自 [Waishnav/devspace](https://github.com/Waishnav/devspace)**，来源提交为 `8cd2fba227454514f3ce8ef4848012753103e773`，保留 MIT 许可。当前归档包含本地未提交修改及原有较早构建。

**注意：**开发工具能读写文件、运行命令，授权给 AI 前确认工作目录与权限，先用于可恢复的项目副本。保管 Owner 密码和令牌，不随意开放公网入口。现有包不是最后源码重新构建的产物，需留意源码与运行行为可能不同。

### VM Unified GUI

在现有 Ubuntu 虚拟机中，将多个容器应用和 Xfce 桌面集中显示在浏览器。自有控制/整合代码配合 **修改过的 [Xpra](https://github.com/Xpra-org/xpra) 与 [xpra-html5](https://github.com/Xpra-org/xpra-html5)**，另依赖 Docker、Xorg、nginx 等组件；不是一个完整的新操作系统镜像。

**注意：**部署快照绑定原机器路径、服务和显示环境，不要直接覆盖到另一台正常使用的系统。安装与模式切换可能重启项目桌面或应用，先保存工作并为虚拟机留快照。浏览器输入、剪贴板和模式切换仍有未完成验收项。再分发修改组件时保留相应开源许可。

### Elixir SQLite Chunker

按 Elixir AST 提取函数块，存入 SQLite，并提供块所有权及图谱调用接口。扩展自已有本地 `elixir-sqlite-chunker` 工程；**准确的第三方原始开源仓库尚未确认**，不能将 Python、Elixir 或 SQLite 依赖当作应用来源。

**注意：**导入时只收录支持的函数块，不包含模块全部代码，不能拿块库代替完整源码备份。首次打开旧数据库可能执行结构迁移，先复制数据库；覆写、删除和所有权登记会影响后续读取。接口默认只监听本机，节点编号不能直接当作公网用户认证。

### SSH Relay 3.0 / 5.7 / 当前名为 5.8 的仓库

通过公网中继提供 SSH、文件传输和 MCP 远程操作。MCP 工具目录和部分辅助代码源自 **MCP SSH Manager（MIT）**，来源记录见 3.0 的 `source/docs/MCP-SOURCE-PROVENANCE.json`；中继与后续适配另行实现。现有资料尚不足以给出原项目唯一可信的上游仓库 URL。

**注意：**配对后可按远端账号权限执行命令、传文件，配对码、私钥和运行状态只交给可信的人或 AI。远程删除、部署等操作前确认目标与备份；网络中断后先查询原任务结果，避免重复执行。公网中继可用性与网络有关，不保证永不断线。3.0 与 5.7 应使用各自匹配的程序和配置；当前 `ssh-relay-5.8` 仍有 5.7 标识与包，不能按名字假定已升级或兼容。

### OpenDeploy / PXVIRT 装机项目

制作安装介质并推进 PXVIRT 安装、虚拟机及恢复流程。项目地图有内部源码与 Windows 工具包，但**当前公开仓库尚只有迁移工作流**，未形成可供公众直接使用的完整交付。现有资料表明它围绕 PXVIRT、GRUB、VirtualBox 等组件组织流程；尚未确认 OpenDeploy 应用修改自哪个第三方仓库，不能把这些组件笼统写成它的原始源码来源。

**注意：装机属于会改变磁盘和启动环境的操作。** 选错盘、写盘中断、介质故障、驱动或引导不兼容，可能导致数据丢失，或安装到一半后原系统和新系统都暂时打不开。先把重要数据备份到不参与安装的设备，确认目标盘，准备可靠的 U 盘及原系统恢复材料。**最好同时备有两台电脑**：一台安装出问题时，另一台仍能下载镜像、查资料、重新写 U 盘，再重装或恢复。只有一台时，至少提前准备好备用安装介质。虚拟机流程成功不代表实体硬件安装已经通过。

### 空仓库 `-`

当前无项目文件、运行包或可核对的上游，暂不作为软件使用入口。

## 核对依据与维护

本页是文档索引，没有启动装机、发布内容或执行各软件的功能验收。优先采用各仓库当前文件和公开 Releases；项目地图中的历史交付不自动算作对应公开仓库已经拥有。

- 分发包：各项目 `release/`、`packages/`、`deliverables/` 及 Releases。
- 依赖边界：ResearchDesk、PromptLab、AgentHub、WorkDesk、OmniDispatch 的 `DEPENDENCIES.md`。
- 来源及状态：DevSpace 的 `SOURCE-MANIFEST.json` / `HANDOFF.md`；File Bridge 的 `docs/SOURCE-MANIFEST.json` / `docs/HANDOFF.md`；VM Unified GUI 的 README；SSH Relay 的来源记录与包说明。
- 包名、平台或来源变动时，同时更新速查表和项目说明。来源待确认的项目，应有实际代码来源记录后再补上游链接，不能凭相似功能猜测。

第三方依赖遵循各自许可证。此文档的“有包”只描述交付形态，不作无故障、商业适用或全部功能通过的承诺。
