# 🌟 Doubao Skills Collection | 字节跳动豆包 & 飞书 AI 智能体技能库全集

[![GitHub release](https://img.shields.io/badge/Release-v1.0.0-blue.svg)](https://github.com/RayMorTwinkle/doubao-skills/releases)
[![Skills Count](https://img.shields.io/badge/Skills-103%20Top--Level%20(131%20Total)-brightgreen.svg)](#-技能分类全景目录)
[![Lark Ecosystem](https://img.shields.io/badge/Lark-17%20Integrated%20Skills-00D6B9.svg)](#1-飞书--lark-深度协同套件-17)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-lightgrey.svg)](LICENSE)

> [!IMPORTANT]
> ### ⚠️ 免责声明与项目说明（Disclaimer & Notices）
> 1. **公开来源说明**：本项目收录的全部 Skills 技能规范文件，**主要从豆包云电脑（Doubao Cloud PC）的公开运行环境中提取**。此内容为**任何人正常访问与调用豆包云电脑均可直接获取的公开资料**。
> 2. **仅供学习参考**：本项目仅用于个人学习研究、技术交流以及 AI Agent / Prompt 工程的架构参考，**严禁用于任何商业牟利或商业运营行为**。
> 3. **免责声明**：作者与整理者仅作资料技术归档，不对内容的准确性、完整性、可用性或由此引发的任何风险承担任何责任，**本人不负任何责任**。
> 4. **侵权联系删除**：技能内涉及之商标、产品名称及版权均归其原始权利人（北京字跳网络技术有限公司等）所有。**如有任何侵权问题，请随时通过 Issue 或邮件联系作者，确认后将第一时间配合删除相关内容**。

> 本仓库完整收录了字节跳动旗下 **豆包（Doubao / 豆包办公 / 豆包专业版）** 与 **飞书（Lark）** AI 智能体生态中运行的 **103 个顶级生产级 Skill（包含 131 个 SKILL.md 技能定义）**。

这套技能体系不仅是单纯的 Prompt 提示词，而是融合了**标准执行协议（Protocol）、上下文约束、输入验证、确定性质检工具（Verifier Hub）、离线渲染预览（Artifact Preview）以及底层大模型/多媒体引擎直连**的工业级 Agent 工作流规范。

---

## 📖 目录
- [🌟 核心技术亮点](#-核心技术亮点)
- [🗂️ 技能分类全景目录](#-技能分类全景目录)
  - [飞书 / Lark 深度协同套件 (17)](#1-飞书--lark-深度协同套件-17)
  - [通用办公文档与交付质检 (7)](#2-通用办公文档与交付质检-7)
  - [学术科研与论文写作 (8 顶级 / 16 细分模块)](#3-学术科研与论文写作-8-顶级--16-细分模块)
  - [医疗健康与循证医学 (7)](#4-医疗健康与循证医学-7)
  - [金融投资与商业/证券分析 (11)](#5-金融投资与商业证券分析-11)
  - [法律合规与知识产权 (7)](#6-法律合规与知识产权-7)
  - [电商运营、营销增长与广告投放 (13)](#7-电商运营、营销增长与广告投放-13)
  - [多媒体创作与 AIGC 视觉/音视频生产 (16)](#8-多媒体创作与-aigc-视觉音视频生产-16)
  - [产品设计、软件工程与技术运维 (11)](#9-产品设计、软件工程与技术运维-11)
  - [生活实用与系统服务 (6)](#10-生活实用与系统服务-6)
- [🛠️ 架构与设计规范](#-架构与设计规范)
- [🚀 如何在你的 Agent 中使用](#-如何在你的-agent-中使用)
- [📄 许可证与免责声明](#-许可证与免责声明)

---

## 🌟 核心技术亮点

1. **从“单次问答”走向“端到端确定性交付（Agentic Workflow）”**
   每个 Skill 均配有完备的执行蓝图（SOP）。例如学术论文、专利申请、商业合同等任务，必须按照“立项调研 → 结构蓝图 → 分段起草 → 证据链校核 → 格式终审”阶段性推进，杜绝大模型盲目输出不可控长文。

2. **全方位打通飞书企业办公底座（Lark Workspace Native）**
   内置 17 个飞书原生 API 技能，涵盖文档（Docx）、多维表格（Base）、知识库（Wiki）、即时通讯（IM）、视频会议（Meeting/妙记）、审批（Approval）与任务（Task），支持智能体在企业协同环境中闭环作业。

3. **字节自研生成式模型直连**
   直接挂载字节跳动最新多模态大模型入口：
   - **Seed-Audio**：声音场景与角色音色生成
   - **Seedance 2.5**：高一致性视频生成
   - **Seedream 5.0 / 5.0 Flash**：旗舰级文生图与重绘
   - **ByteDance MediaKit**：音频人声分离、视频精彩高光拆条与智能画质修复

4. **工业级质量保证与防幻觉双保险**
   - **`verifier-hub`**：内置 58 个确定性命令行工具，交付前自动针对 Word、Excel、PPT、PDF 校验公式正确性、空单元格、文字截断、签名占位符。
   - **`artifact-preview`**：将生成工件渲染为离线截图，通过多模态自检解决排版重叠与字体乱码。
   - **真实证据链（Evidence-Driven）**：在医疗与学术领域内置文献真实性审查机制，坚决拒绝虚构引用。

5. **告别机械腔调：`doubao-human-signal` 去 AI 味**
   专门提炼了消除“AI 腔调”的语言规则库，让文案重获人情味、自然呼吸感与真情实感。

---

## 🗂️ 技能分类全景目录

### 1. 飞书 / Lark 深度协同套件 (17)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/lark-doc`](.skills/lark-doc/SKILL.md) | **`lark-doc`** | 飞书/豆包在线云文档（Docx/Wiki）的阅读、新建、批量修改与高级排版。 |
| [`.skills/lark-base`](.skills/lark-base/SKILL.md) | **`lark-base`** | 飞书多维表格（Base）自动化：记录增删改查、字段架构设计与视图管理。 |
| [`.skills/lark-wiki`](.skills/lark-wiki/SKILL.md) | **`lark-wiki`** | 飞书企业知识库：知识空间创建、目录层级管理、成员权限与文档节点组织。 |
| [`.skills/lark-im`](.skills/lark-im/SKILL.md) | **`lark-im`** | 飞书即时通讯：群聊管理、消息智能收发、图文文件互传与交互式卡片消息发送。 |
| [`.skills/lark-mail`](.skills/lark-mail/SKILL.md) | **`lark-mail`** | 飞书企业邮箱：邮件全文搜索、草稿起草、智能收发与邮件标签管理。 |
| [`.skills/lark-calendar`](.skills/lark-calendar/SKILL.md) | **`lark-calendar`** | 飞书日历与日程管理：会议排程、冲突检测、忙闲状态分析与跨组织日程协调。 |
| [`.skills/lark-meeting`](.skills/lark-meeting/SKILL.md) | **`lark-meeting`** | 飞书视频会议：会议预定、会议纪要与“妙记”录音转写文字稿深度提取分析。 |
| [`.skills/lark-task`](.skills/lark-task/SKILL.md) | **`lark-task`** | 飞书任务待办：任务创建、分步骤拆解、清单组织与协作成员自动派发。 |
| [`.skills/lark-approval`](.skills/lark-approval/SKILL.md) | **`lark-approval`** | 飞书审批流转：企业审批单据发起、流程进度跟踪、审批明细调取。 |
| [`.skills/lark-attendance`](.skills/lark-attendance/SKILL.md) | **`lark-attendance`** | 飞书考勤管理：员工打卡记录核算、异常出勤统计、排班与考勤数据导出。 |
| [`.skills/lark-contact`](.skills/lark-contact/SKILL.md) | **`lark-contact`** | 飞书企业通讯录：组织架构树遍历、部门人员检索与员工信息卡片获取。 |
| [`.skills/lark-drive`](.skills/lark-drive/SKILL.md) | **`lark-drive`** | 飞书云空间（云盘）：文件与文件夹上传、权限粒度配置、密级设置与链接共享。 |
| [`.skills/lark-okr`](.skills/lark-okr/SKILL.md) | **`lark-okr`** | 飞书 OKR 目标管理：目标（Objective）与关键结果（Key Results）对齐与进度追踪。 |
| [`.skills/lark-whiteboard`](.skills/lark-whiteboard/SKILL.md) | **`lark-whiteboard`** | 飞书画板/白板：图形结构导出、思维导图与架构流程图在线编辑。 |
| [`.skills/lark-markdown`](.skills/lark-markdown/SKILL.md) | **`lark-markdown`** | 飞书 Markdown：原生 Markdown 文件与云端文档双向导入、编辑与差异比对。 |
| [`.skills/lark-openapi-explorer`](.skills/lark-openapi-explorer/SKILL.md) | **`lark-openapi-explorer`** | 飞书 OpenAPI 探索器：动态挖掘并调用官方未经封装的原生底层 API 接口。 |
| [`.skills/lark-workflow-standup-report`](.skills/lark-workflow-standup-report/SKILL.md) | **`lark-workflow-standup-report`** | 自动化工作流：整合日历日程与未完成待办，一键生成每日晨会/站会摘要。 |

### 2. 通用办公文档与交付质检 (7)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/word`](.skills/word/SKILL.md) | **`word`** | Microsoft Word 文档智能读写、党政公文标准规范排版、商务合同模板生成。 |
| [`.skills/sheet`](.skills/sheet/SKILL.md) | **`sheet`** | Excel/CSV 本地与在线表格全场景处理：公式计算、财务建模、透视分析与美化。 |
| [`.skills/ppt`](.skills/ppt/SKILL.md) | **`ppt`** | 幻灯片演示文稿设计：页面版式设计、要点提炼、章节排版与图文生成。 |
| [`.skills/pdf`](.skills/pdf/SKILL.md) | **`pdf`** | PDF 全能工具箱：内容解析提取、扫描件 OCR、表单自动填写、Word/云文档格式转换。 |
| [`.skills/html`](.skills/html/SKILL.md) | **`html`** | 单文件交互式 HTML/H5 报告、可视化看板与动态前端页面构建。 |
| [`.skills/verifier-hub`](.skills/verifier-hub/SKILL.md) | **`verifier-hub`** | 【核心质检 CLI】58 项确定性检查子命令，交付前严查 Word/Excel/PDF/PPT 格式、公式、字数、签名与空值。 |
| [`.skills/artifact-preview`](.skills/artifact-preview/SKILL.md) | **`artifact-preview`** | 【视觉自检】将生成交付物离线渲染为高清快照与排版缩略图，杜绝断页、字体乱码与文本截断。 |

### 3. 学术科研与论文写作 (8 顶级 / 16 细分模块)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-academic-researcher`](.skills/doubao-academic-researcher/SKILL.md) | **`doubao-academic-researcher`**<br/>*包含 4 个子模块: `document-delivery`, `literature-scout`, `research-synthesis`, `review-writing`* | 系统化文献调研：包含前沿文献雷达 (literature-scout)、多源观点综合 (research-synthesis)、综述写作 (review-writing)。 |
| [`.skills/doubao-academic-polish`](.skills/doubao-academic-polish/SKILL.md) | **`doubao-academic-polish`**<br/>*包含 10 个子模块: `paper-shape`, `paper-write-en`, `paper-write-zh`, `paper-write-zh-evidence...` | 学术正文写作与精修主入口：涵盖提纲架构 (paper-shape)、中英双语起草，内置人文社科 (hss)、理工科 (stem) 与证据链 (evidence-driven) 范式。 |
| [`.skills/doubao-academic-evaluator`](.skills/doubao-academic-evaluator/SKILL.md) | **`doubao-academic-evaluator`**<br/>*包含 2 个子模块: `idea-evaluate`, `submission-review`* | 同行评审“只诊不改”：研究选题价值评估 (idea-evaluate) 与投稿前致命硬伤审稿 (submission-review)。 |
| [`.skills/doubao-research-proposal`](.skills/doubao-research-proposal/SKILL.md) | **`doubao-research-proposal`** | 科研项目开题报告、国家社科/自科基金申报书、立项调研方案起草。 |
| [`.skills/doubao-paper-close-reading`](.skills/doubao-paper-close-reading/SKILL.md) | **`doubao-paper-close-reading`** | 顶会/顶刊论文逐段精读拆解、研究方法学复现推导与实验对比分析。 |
| [`.skills/doubao-critical-reading-companion`](.skills/doubao-critical-reading-companion/SKILL.md) | **`doubao-critical-reading-companion`** | 长难学术专著与理论文献批判性研读伴读助手。 |
| [`.skills/doubao-reference-audit`](.skills/doubao-reference-audit/SKILL.md) | **`doubao-reference-audit`** | 参考文献真实性与格式严审：核验知网/DOI/Crossref，杜绝大模型编造假文献。 |
| [`.skills/doubao-journal-format`](.skills/doubao-journal-format/SKILL.md) | **`doubao-journal-format`** | 期刊/会议格式标准化：适配 Nature、IEEE、ACM、国标 GB/T 7714 样式规范。 |

### 4. 医疗健康与循证医学 (7)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-answer-with-medical-evidence`](.skills/doubao-answer-with-medical-evidence/SKILL.md) | **`doubao-answer-with-medical-evidence`** | 面向患者/家属的健康循证咨询，结合最新权威医学指南与临床文献提供关怀与科普解答。 |
| [`.skills/doubao-clinical-decision-support`](.skills/doubao-clinical-decision-support/SKILL.md) | **`doubao-clinical-decision-support`** | 面向临床医生的辅助决策支持：复杂病例病情分析、鉴别诊断推导与循证诊疗策略推荐。 |
| [`.skills/doubao-medical-report`](.skills/doubao-medical-report/SKILL.md) | **`doubao-medical-report`** | 临床生化检验单、超声、CT、MRI 影像学检查报告关键指标专业拆解与解读。 |
| [`.skills/doubao-medical-literature-search`](.skills/doubao-medical-literature-search/SKILL.md) | **`doubao-medical-literature-search`** | PubMed、Cochrane、知网医学专业数据库高质量检索式构建与文献初筛。 |
| [`.skills/doubao-medical-literature-interpretation`](.skills/doubao-medical-literature-interpretation/SKILL.md) | **`doubao-medical-literature-interpretation`** | 重磅临床研究论文深度解读：RCT 临床终点、统计学效力、偏倚风险剖析。 |
| [`.skills/doubao-medical-literature-monitoring`](.skills/doubao-medical-literature-monitoring/SKILL.md) | **`doubao-medical-literature-monitoring`** | 前沿疾病治疗与靶向药物最新医学文献动态监控。 |
| [`.skills/doubao-medical-literature-translation`](.skills/doubao-medical-literature-translation/SKILL.md) | **`doubao-medical-literature-translation`** | 医学学术文献精准汉化与英文翻译，保证术语与上下文严谨统一。 |

### 5. 金融投资与商业/证券分析 (11)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-announcement-analysis`](.skills/doubao-announcement-analysis/SKILL.md) | **`doubao-announcement-analysis`** | 上市公司公告深度解读与监控：覆盖 A股（沪深北）、港股（HKEX）、美股（SEC EDGAR）。 |
| [`.skills/doubao-earnings-analysis`](.skills/doubao-earnings-analysis/SKILL.md) | **`doubao-earnings-analysis`** | 财报季核心数据拆解：季报/半年报/年报深度拆解与业绩电话会超预期亮点分析。 |
| [`.skills/doubao-public-company-analysis`](.skills/doubao-public-company-analysis/SKILL.md) | **`doubao-public-company-analysis`** | 上市公司全景深度研究：商业模式、竞争壁垒、核心业务拆解与历史财务剖析。 |
| [`.skills/doubao-private-company`](.skills/doubao-private-company/SKILL.md) | **`doubao-private-company`** | 非上市公司/独角兽企业商业尽职调查与业务模式投前分析。 |
| [`.skills/doubao-finance-model-builder`](.skills/doubao-finance-model-builder/SKILL.md) | **`doubao-finance-model-builder`** | 自动化构建估值与财务预测模型：DCF 现金流折现、三张表联动 Excel 模板输出。 |
| [`.skills/multi-stock-comparison`](.skills/multi-stock-comparison/SKILL.md) | **`multi-stock-comparison`** | 多股横向对比与配对交易研究：估值溢价、基本面弹性、A/H 股相对价值。 |
| [`.skills/doubao-daily-stock`](.skills/doubao-daily-stock/SKILL.md) | **`doubao-daily-stock`** | 个股日常盘面跟踪与舆情异动简报。 |
| [`.skills/doubao-stock-screening`](.skills/doubao-stock-screening/SKILL.md) | **`doubao-stock-screening`** | 量化与基本面多因子智能选股模型。 |
| [`.skills/doubao-industry-analysis`](.skills/doubao-industry-analysis/SKILL.md) | **`doubao-industry-analysis`** | 宏观与行业深度研究报告：全产业链图谱梳理、市场规模测算与竞争格局演变。 |
| [`.skills/doubao-market-hotspot`](.skills/doubao-market-hotspot/SKILL.md) | **`doubao-market-hotspot`** | 盘中盘后资金流向拆解、题材轮动成因与市场情绪复盘。 |
| [`.skills/doubao-wealth-planning`](.skills/doubao-wealth-planning/SKILL.md) | **`doubao-wealth-planning`** | 个人与家庭资产配置、现金流规划与财富管理方案。 |

### 6. 法律合规与知识产权 (7)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-contract-drafting`](.skills/doubao-contract-drafting/SKILL.md) | **`doubao-contract-drafting`** | 专业商业合同标准文本起草，生成无批注格式规范的正式 Word 文档。 |
| [`.skills/doubao-contract-reviewer`](.skills/doubao-contract-reviewer/SKILL.md) | **`doubao-contract-reviewer`** | 合同风险条款严审：违约责任、争议管辖、责任限制等法律红线排查与修订。 |
| [`.skills/doubao-contract-amendment`](.skills/doubao-contract-amendment/SKILL.md) | **`doubao-contract-amendment`** | 既有合同变更协议、补充协议、终止与解除协议起草。 |
| [`.skills/doubao-compliance-assessment-public`](.skills/doubao-compliance-assessment-public/SKILL.md) | **`doubao-compliance-assessment-public`** | 业务合规评估：针对新产品 PRD、商业模式进行监管红线审查并生成合规审查报告。 |
| [`.skills/doubao-dpa-drafter`](.skills/doubao-dpa-drafter/SKILL.md) | **`doubao-dpa-drafter`** | 数据处理协议 (Data Processing Agreement, DPA) 与数据跨境合规条款拟定。 |
| [`.skills/doubao-personal-info-audit`](.skills/doubao-personal-info-audit/SKILL.md) | **`doubao-personal-info-audit`** | 个人信息保护合规性审计：用户隐私政策条款合规对齐与风险提示。 |
| [`.skills/doubao-patent-drafting`](.skills/doubao-patent-drafting/SKILL.md) | **`doubao-patent-drafting`**<br/>*包含 3 个子模块: `claims`, `intake-audit`, `specification`* | 专利申请文书撰写全流程：交底书挖掘 (intake-audit)、权利要求书布局 (claims)、说明书 (specification) 编写。 |

### 7. 电商运营、营销增长与广告投放 (13)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-product-selection`](.skills/doubao-product-selection/SKILL.md) | **`doubao-product-selection`** | 电商爆款选品分析：市场需求容量评估、竞争激烈度与蓝海机会挖掘。 |
| [`.skills/doubao-product-analysis`](.skills/doubao-product-analysis/SKILL.md) | **`doubao-product-analysis`** | 商品竞品深度测评、消费者评价痛点与购买决策要素归因分析。 |
| [`.skills/doubao-product-content`](.skills/doubao-product-content/SKILL.md) | **`doubao-product-content`** | 电商高转化详情页策划：五点描述、核心卖点梳理与种草图文。 |
| [`.skills/doubao-listing-localization`](.skills/doubao-listing-localization/SKILL.md) | **`doubao-listing-localization`** | 跨境电商海外 Listing 语境本地化：亚马逊等多语言商品标题、搜索关键词优化。 |
| [`.skills/doubao-cross-border-growth-content`](.skills/doubao-cross-border-growth-content/SKILL.md) | **`doubao-cross-border-growth-content`** | 跨境社媒增长内容矩阵生成：TikTok、Instagram 等海外传播爆款文案。 |
| [`.skills/doubao-ecommerce-compliance-tax-logistics`](.skills/doubao-ecommerce-compliance-tax-logistics/SKILL.md) | **`doubao-ecommerce-compliance-tax-logistics`** | 跨境合规与物流税务咨询：VAT、关税合规、退换货与跨国物流路线规划。 |
| [`.skills/doubao-ecommerce-proposal`](.skills/doubao-ecommerce-proposal/SKILL.md) | **`doubao-ecommerce-proposal`** | 电商年度大促、品牌联合营销与商业运营提案。 |
| [`.skills/doubao-oceanengine-adops-agent`](.skills/doubao-oceanengine-adops-agent/SKILL.md) | **`doubao-oceanengine-adops-agent`** | 巨量引擎广告投放运营助手：巨量广告计划搭建策略、人群包洞察与素材消耗排查。 |
| [`.skills/doubao-marketing-plan`](.skills/doubao-marketing-plan/SKILL.md) | **`doubao-marketing-plan`** | 全域整合营销策划案 (IMC)：市场定位、传播节奏与执行排期。 |
| [`.skills/doubao-headlines-calendar`](.skills/doubao-headlines-calendar/SKILL.md) | **`doubao-headlines-calendar`** | 多平台爆款标题生成（支持 A/B 测试）与周度/月度选题内容日历排期。 |
| [`.skills/doubao-marketing-material-review`](.skills/doubao-marketing-material-review/SKILL.md) | **`doubao-marketing-material-review`** | 广告营销物料合规审核：排查《广告法》极限词、绝对化用语及敏感宣称。 |
| [`.skills/doubao-sentiment-tracker`](.skills/doubao-sentiment-tracker/SKILL.md) | **`doubao-sentiment-tracker`** | 品牌声誉与全网舆情监控追踪。 |
| [`.skills/doubao-customer-service`](.skills/doubao-customer-service/SKILL.md) | **`doubao-customer-service`** | 智能客服应对工作流与复杂客诉安抚高情商话术库。 |

### 8. 多媒体创作与 AIGC 视觉/音视频生产 (16)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/byted-mediakit-shared`](.skills/byted-mediakit-shared/SKILL.md) | **`byted-mediakit-shared`** | 【字节 MediaKit 引擎】多媒体底层工具集调度中枢，协调音视频图像处理管线。 |
| [`.skills/byted-mediakit-audio`](.skills/byted-mediakit-audio/SKILL.md) | **`byted-mediakit-audio`** | 专业音频工程：人声/背景声分离、音频端点检测、转码与封装适配。 |
| [`.skills/byted-mediakit-editing`](.skills/byted-mediakit-editing/SKILL.md) | **`byted-mediakit-editing`** | 成片剪辑合成：时间线拼接裁剪、转场特效、运镜滤镜、字幕压制与音视频合流。 |
| [`.skills/byted-mediakit-image`](.skills/byted-mediakit-image/SKILL.md) | **`byted-mediakit-image`** | 智能图像处理：高质量压缩减容、背景擦除/抠图、超清画质修复、OCR 识别。 |
| [`.skills/byted-mediakit-video`](.skills/byted-mediakit-video/SKILL.md) | **`byted-mediakit-video`** | 视频理解与增强：高光拆条分析、剧情结构化、场景语义切分、智能抠像。 |
| [`.skills/seed-audio`](.skills/seed-audio/SKILL.md) | **`seed-audio`** | 【字节 Seed-Audio 模型】自然语言声音场景生成，支持角色音色定制与多角色台词合成。 |
| [`.skills/seedance-25`](.skills/seedance-25/SKILL.md) | **`seedance-25`** | 【字节 Seedance 2.5 模型】专业级视频生成大模型接入，通过分步确认生成高质量动态镜头。 |
| [`.skills/seedream-50`](.skills/seedream-50/SKILL.md) | **`seedream-50`** | 【字节 Seedream 5.0 模型】旗舰级图像生成大模型接入，支持文生图、图像重绘与扩展。 |
| [`.skills/doubao-book-writer`](.skills/doubao-book-writer/SKILL.md) | **`doubao-book-writer`**<br/>*包含 5 个子模块: `doubao-document-delivery`, `manuscript-writing`, `outline-planning`, `project-intake...` | 【长篇书稿工作台】涵盖立项调研、全书大纲、正文长文书写、去AI味与多格式交付。 |
| [`.skills/doubao-novel-writing`](.skills/doubao-novel-writing/SKILL.md) | **`doubao-novel-writing`** | 网络小说创作助手：世界观设定、人物小传、剧情冲突设计与连续章节起草。 |
| [`.skills/doubao-creative-drama`](.skills/doubao-creative-drama/SKILL.md) | **`doubao-creative-drama`** | 微短剧全案创作：剧本分集、情绪转折钩子设计与竖屏短剧台本。 |
| [`.skills/doubao-creative-video`](.skills/doubao-creative-video/SKILL.md) | **`doubao-creative-video`** | 短视频脚本策划：爆款开篇抓手、分镜提示词与口播台词。 |
| [`.skills/doubao-creative-design`](.skills/doubao-creative-design/SKILL.md) | **`doubao-creative-design`** | 视觉设计创意方案：构图比例、色彩搭配、排版指引与生图提示词。 |
| [`.skills/doubao-video-extract`](.skills/doubao-video-extract/SKILL.md) | **`doubao-video-extract`** | 视频核心内容提取：音视频逐字稿提炼、要点摘要与传播金句抽取。 |
| [`.skills/doubao-newmedia-writing`](.skills/doubao-newmedia-writing/SKILL.md) | **`doubao-newmedia-writing`** | 主流新媒体（公众号/小红书/知乎）爆款推文定制撰写。 |
| [`.skills/doubao-multiplatform-rewrite`](.skills/doubao-multiplatform-rewrite/SKILL.md) | **`doubao-multiplatform-rewrite`** | 跨平台多风格内容一键分发重构。 |

### 9. 产品设计、软件工程与技术运维 (11)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-app-builder`](.skills/doubao-app-builder/SKILL.md) | **`doubao-app-builder`** | 【字节“妙搭”全栈平台】应用级与工程级产品构建：支持全栈多文件项目、前端界面、后端 API、数据库绑定。 |
| [`.skills/doubao-product-manager`](.skills/doubao-product-manager/SKILL.md) | **`doubao-product-manager`** | 资深产品经理助理：撰写结构化 PRD、绘制业务流程图、拆解产品功能路线图。 |
| [`.skills/doubao-product-qa`](.skills/doubao-product-qa/SKILL.md) | **`doubao-product-qa`** | 软件测试质量保证：编写测试用例、边界异常排查与体验验收。 |
| [`.skills/doubao-game-designer`](.skills/doubao-game-designer/SKILL.md) | **`doubao-game-designer`** | 游戏策划核心机制设计、数值平衡推演与关卡玩法策划。 |
| [`.skills/doubao-data-analysis`](.skills/doubao-data-analysis/SKILL.md) | **`doubao-data-analysis`** | 数据统计分析与探索：数据清洗、相关性分析与关键驱动因素提取。 |
| [`.skills/doubao-visualization`](.skills/doubao-visualization/SKILL.md) | **`doubao-visualization`** | 高级数据可视化：ECharts、D3、Mermaid 与 Matplotlib 高保真图表代码生成。 |
| [`.skills/doubao-questionnaire-designer`](.skills/doubao-questionnaire-designer/SKILL.md) | **`doubao-questionnaire-designer`** | 专业问卷调研量表设计：信效度校验、问题跳转逻辑设计与样本配额规划。 |
| [`.skills/doubao-enterprise-search`](.skills/doubao-enterprise-search/SKILL.md) | **`doubao-enterprise-search`** | 跨系统企业级内网知识智能检索与整合解答。 |
| [`.skills/browser-task`](.skills/browser-task/SKILL.md) | **`browser-task`** | 真实浏览器 GUI 自动化操控：处理小红书/微博/电商平台的登录与复杂交互。 |
| [`.skills/doubao-cron-scheduler`](.skills/doubao-cron-scheduler/SKILL.md) | **`doubao-cron-scheduler`** | 定时任务触发器与周期性脚本自动化调度。 |
| [`.skills/skill-creator-for-work`](.skills/skill-creator-for-work/SKILL.md) | **`skill-creator-for-work`** | AI 技能开发者指南：如何创建与维护高水准的 Agent Skill 规范。 |

### 10. 生活实用与系统服务 (6)

| 技能目录 | 名称与功能概述 | 核心价值 / 场景 |
| :--- | :--- | :--- |
| [`.skills/doubao-human-signal`](.skills/doubao-human-signal/SKILL.md) | **`doubao-human-signal`** | 【文本去 AI 味神器】消除生硬机械的 AI 痕迹，赋予文案自然的人情味、情绪表达与真实语感。 |
| [`.skills/doubao-ultimate-guide`](.skills/doubao-ultimate-guide/SKILL.md) | **`doubao-ultimate-guide`**<br/>*包含 4 个子模块: `cooking-tutorial`, `fitness-planner-pro`, `game-guide`, `travel-planner-pro`* | 【生活万能攻略指南】下设做饭烹饪 (cooking-tutorial)、专业健身规划 (fitness-planner-pro)、游戏攻略 (game-guide)、定制旅游路书 (travel-planner-pro)。 |
| [`.skills/doubao-pc-optimizer`](.skills/doubao-pc-optimizer/SKILL.md) | **`doubao-pc-optimizer`** | 电脑性能调优与磁盘瘦身：快速定位系统垃圾（C盘空间释放）、解决卡顿、输出调优脚本。 |
| [`.skills/doubao-record`](.skills/doubao-record/SKILL.md) | **`doubao-record`** | 一键启动会话录音与随行语音文字转记。 |
| [`.skills/doubao-identity`](.skills/doubao-identity/SKILL.md) | **`doubao-identity`** | 豆包平台官方服务与规则权威答疑：会员权益、记忆管理、隐私条款口径对齐。 |
| [`.skills/gift-card-redemption`](.skills/gift-card-redemption/SKILL.md) | **`gift-card-redemption`** | 豆包会员订阅礼品卡可兑换状态查询与在线兑换。 |

---

## 🛠️ 架构与设计规范

仓库中每个 Skill 遵循统一的 Agent Skill 规范标准：

```text
.skills/<skill-name>/
├── SKILL.md            # 核心指令文件（包含 YAML Frontmatter 描述、触发条件与 SOP）
├── references/         # 垂直领域专家知识库、行业规范、法律模型与排版标准
├── scripts/            # 自动化 Python/Bash 工具脚本（数据校验、格式转换等）
├── assets/             # 预置模板（简历、公文模版）、字体库、指标索引等
└── sub-skills/         # （可选）复杂任务拆解后的子工作流智能体
```

### YAML Frontmatter 示例
```yaml
---
name: doubao-academic-polish
description: 学术论文正文写作、结构设计与语言润色总入口...
---
```

---

## 🚀 如何在你的 Agent 中使用

### 方式 1：用于支持 `.skills` 规范的 Agent（如 Claude Code, Antigravity, OpenCode 等）
直接将本仓库克隆到你的工作区根目录下，或将所需技能复制到你的 `.skills/` 目录中：
```bash
git clone https://github.com/RayMorTwinkle/doubao-skills.git
# 复制特定技能到当前项目的技能目录
cp -r doubao-skills/.skills/verifier-hub .skills/
```

### 方式 2：作为系统提示词（System Prompt）引用
阅读任意技能目录下的 `SKILL.md`，提取其中的角色设定（Role）、执行协议（Protocols）和质量标准（Rubric），作为大模型的上下文提示词使用。

---

## 📄 许可证与免责声明

- **开源许可证**：本项目采用 [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE) 许可证，**仅限非商业性学习与技术交流使用**。
- **资料来源**：本项目整理自豆包云电脑公开运行环境，为任何人调用豆包云电脑均可获取的公开参考信息。
- **免责条款**：整理者不对本仓库任何内容的完整性、适用性及衍生后果负责，**本人不负任何法律或连带责任**。
- **版权与侵权删除**：豆包、飞书、Lark、巨量引擎、Seedance、Seedream 等商标与资产版权归北京字跳网络技术有限公司所有。**若权利方认为内容不妥或存在侵权，请通过 GitHub Issue 联系，我们将立即核实并执行下架/删除**。
