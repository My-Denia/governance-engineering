简体中文 | [English](README.en.md)

# Governance engineering(治理工程)

Harness engineering 装备一次运行;loop engineering 驱动多次运行;
governance engineering 让这些循环保持诚实:状态权威、言行对账、规则生命周期。

本仓库是 governance engineering 作为一套已建成系统的披露包——一个面向自主
LLM agent 的执行治理层,于 2026 年 5 月至 7 月间私下构建并实际使用。它记录
了设计思考(essays/)、机制规格(specs/)与一份可核验的开发年表
(CHRONOLOGY.md)。实现代码有意不予公开(分级方式见 DISCLOSURE-MAP.md)。

## 问题层次

Prompt engineering 塑造了模型被问到什么。Context engineering 塑造了它在作
答时知道什么。Harness engineering 塑造了 agent 借以行动的机械。Loop
engineering 塑造了长时间运行的工作如何跨轮次延续。在这一切之上,还有一个
尚未被塑造的层次:**自主运行凭什么可信**——不是 agent 能不能完成这项工
作,而是它对这项工作的陈述是否为真、它的计划是否经受住了与现实的接触,
以及治理它的那些规则本身是否也受治理。

本包记录了一个做出来的答案——它是作为一套运行中的系统建成的,而不是一份
提案:

- **两道阻塞式审计门**——计划在执行前由一个隔离上下文的审计者审核;执行
  在被允许标记为“完成”之前先接受审计(specs/gates.md)。由运行时钩子强制
  执行,而不是靠口头约定。
- **言行对账**——六项机器检查,比对运行状态所声称的与其工件所显示的
  (specs/say-do-checks.md)。
- **四格偏差分类法**——每个检查点都可以对计划遭遇了什么作出分类:按计划
  (on-plan)、绕行(detour)、硬啃(grind)或上报(escalate)——分类依据
  是该偏差许可何种响应(specs/four-cell-taxonomy.md)。
- **证据分级状态**——主张携带其锚点质量(弱/中/强);收工需要中级或更好
  的证据(specs/run-state.md)。
- **自征税的规则生命周期**——每条规则与机制都必须付租;晋级需要 owner 打
  勾,存疑的机器进入缓刑,死掉的规则被退休(specs/rule-lifecycle.md)。

## 年表为什么是这个样子

本包的价值完全取决于其主张的可信度,因此 CHRONOLOGY.md 给自己定下了一个并
不舒服的标准:每个日期都是“不晚于某日”的表述,每条主张都携带分级引用,每
个锚点的等级都在其被使用之处标明(四条主张携带外部持有的 S 级锚点;其余均
为本地证据,并且如实标注),而只有 owner 才能作证的主张被隔离在专门的一节
里。NEEDS-OWNER.md 列出了能把其余部分升级的证据。

## 许可

文稿部分(essays、年表、specs、本 README):CC BY-SA 4.0——见
[docs/LICENSE-DOCS.md](docs/LICENSE-DOCS.md)。代码与技能文件(首次发布时
两者均未收录;实现层按 [DISCLOSURE-MAP.md](DISCLOSURE-MAP.md) 扣留):
AGPL-3.0-or-later——见 [LICENSE](LICENSE)。

## 状态

名称(governance engineering)与许可证均为已定的 owner 裁决;扣留的实现层
如需公开,仍为逐项 owner 决定。首次发布已经发生(release v1.0,
2026-07-08;见 CHRONOLOGY.md)。本仓库尚未记载发布之后的贡献政策。
